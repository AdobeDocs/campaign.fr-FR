---
title: Limitation de l'affichage des PI
description: Découvrez comment limiter l'affichage des PI
feature: PI, Privacy, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 96%

---

# Limitation de l&#39;affichage des PI{#restricting-pii-view}

## Vue d&#39;ensemble {#overview}

Si vous avez besoin que les utilisateurs marketing puissent accéder aux enregistrements de données, mais ne souhaitez pas qu&#39;ils visualisent les informations personnelles (PI) des destinataires telles que le prénom, le nom ou l&#39;adresse e-mail, suivez les instructions ci-dessous afin de protéger la confidentialité et d&#39;empêcher toute utilisation abusive des données par des opérateurs standard de Campaign.

## Mise en œuvre {#implementation}

Un attribut spécifique pouvant être appliqué à n’importe quel élément ou attribut a été ajouté aux schémas. Il complète l’attribut existant **[!UICONTROL visibleIf]**. Cet attribut est : **[!UICONTROL accessibleIf]**. Lorsque vous incluez une expression XTK liée au contexte d’utilisation actuel, elle peut utiliser **[!UICONTROL HasNamedRight]** ou **[!UICONTROL $(login)]**, par exemple.

Vous trouverez ci-dessous un exemple d&#39;extension de schéma de destinataire qui illustre cette utilisation :

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

Les principales propriétés sont les suivantes :

* **[!UICONTROL visibleIf]** : cache les champs des métadonnées. Ils ne sont donc pas accessibles dans la vue d&#39;un schéma, la sélection de colonnes ou l&#39;édition d&#39;expressions. Cette propriété ne masque toutefois aucune donnée. Si le nom du champ est saisi manuellement dans une expression, la valeur s&#39;affiche.
* **[!UICONTROL accessibleIf]** : masque les données (en les remplaçant par des valeurs vides) de la requête obtenue. Si visibleIf est vide, il obtient la même expression que **[!UICONTROL accessibleIf]**.

Les conséquences de l&#39;utilisation de cet attribut dans Adobe Campaign sont les suivantes :

* Les données ne sont pas affichées dans le requêteur générique de la console.
* Les données ne sont pas visibles dans les listes d&#39;aperçu et la liste des enregistrements (console).
* Les données sont en lecture seule dans la vue détaillée.
* Les données ne peuvent être utilisées que dans des filtres (ce qui signifie qu&#39;il est toujours possible de deviner les valeurs à l&#39;aide de stratégies de dichotomie).
* Les expressions qui sont construites à l&#39;aide d&#39;un champ restreint sont aussi restreintes : lower(@email) devient autant accessible que @email.
* Dans un workflow, vous pouvez ajouter la colonne restreinte à la population ciblée en tant que colonne supplémentaire de la transition, mais elle reste inaccessible aux utilisateurs d&#39;Adobe Campaign.
* Lors du stockage de la population ciblée dans un groupe (liste), les caractéristiques des champs stockés sont identiques à celles de la source de données.
* Par défaut, les données ne sont pas accessibles par les codes JavaScript.

## Recommandations {#recommendations}

Dans chaque diffusion, les adresses e-mail sont copiées dans les tables de **[!UICONTROL broadLog]** et de **[!UICONTROL forecastLog]** : ces champs doivent donc également être protégés.

Vous trouverez ci-dessous un exemple d&#39;extension de table de logs pour implémenter cela :

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>Cette restriction s&#39;applique uniquement aux utilisateurs non techniques et n&#39;isole pas les données. Un utilisateur technique disposant des autorisations associées peut ainsi récupérer les données.
