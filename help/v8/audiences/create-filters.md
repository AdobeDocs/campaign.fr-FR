---
title: Créer des filtres dans Adobe Campaign
description: Découvrez comment filtrer vos données et enregistrer des filtres dans Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1768'
ht-degree: 100%

---

# Créer et gérer des filtres{#create-filters}

Le filtrage des données est le processus de sélection d&#39;une petite partie de votre jeu de données, composée uniquement des enregistrements qui correspondent à certains critères, et d&#39;utilisation de ce sous-ensemble pour des actions spécifiques (mises à jour, création d&#39;audiences) ou des analyses.

Lors de la navigation dans Campaign à partir de l&#39;**[!UICONTROL explorateur]**, les données sont affichées dans des listes. Vous pouvez utiliser des filtres intégrés existants pour accéder à un sous-ensemble spécifique de ces données : adresses en quarantaine, destinataires non ciblés, tranche d&#39;âge spécifique ou date de création, par exemple.

Vous pouvez également créer vos propres filtres, les enregistrer pour une utilisation ultérieure ou les partager avec d&#39;autres utilisateurs de Campaign.

La configuration des filtres permet de sélectionner des données dans une liste **[!UICONTROL de manière dynamique]** : lorsque les données sont modifiées, les données filtrées sont mises à jour.

>[!NOTE]
>
>Les paramètres de configuration de l&#39;interface utilisateur sont définis localement pour le périphérique. Il peut parfois être nécessaire de nettoyer ces données, en particulier si des problèmes surviennent lors de leur actualisation. Pour ce faire, utilisez le menu **[!UICONTROL Fichier > Vider le cache local]**.

Les types de filtres suivants sont disponibles dans Adobe Campaign :

## Filtres prédéfinis{#predefined-filters}

Les filtres prédéfinis sont disponibles à partir du bouton **Filtres** au-dessus de chaque liste.

Par exemple, pour les profils, les filtres intégrés suivants sont disponibles :

![](assets/built-in-filters.png)

Vous pouvez accéder aux détails des filtres dans le nœud **[!UICONTROL Profils et cibles > Filtres prédéfinis]** de l&#39;explorateur.

>[!NOTE]
>
>Pour toutes les autres listes de données, les filtres prédéfinis sont stockés dans le nœud **[!UICONTROL Administration > Configuration > Filtres prédéfinis]**.

Sélectionnez un filtre pour afficher sa définition.

![](assets/predefined-filter-list.png)

Utilisez le dernier onglet pour prévisualiser les données filtrées.

![](assets/built-in-filter-preview.png)


Les filtres prédéfinis intégrés sont les suivants :

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>Requête</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Ayant ouvert<br /> </td> 
   <td> Sélection des destinataires qui ont ouvert une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ayant ouvert mais pas cliqué<br /> </td> 
   <td> Sélection des destinataires qui ont ouvert une diffusion mais n'ont pas cliqué sur un lien.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinataires inactifs<br /> </td> 
   <td> Sélection des destinataires qui n'ont pas ouvert une diffusion depuis X mois.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dernière activité par type d'appareil<br /> </td> 
   <td> Sélection des destinataires qui ont cliqué ou ouvert une diffusion Y depuis un appareil de type X dans les Z derniers jours.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dernière activité par type d'appareil (Tracking)<br /> </td> 
   <td> Sélection des destinataires qui ont cliqué ou ouvert une diffusion Y depuis un appareil de type X dans les Z derniers jours.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinataires non ciblés<br /> </td> 
   <td> Sélection des destinataires qui n'ont jamais été ciblés sur un canal Y depuis X mois.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinataires très actifs<br /> </td> 
   <td> Sélection des destinataires qui ont cliqué dans une diffusion au moins X fois dans les Y derniers mois.<br /> </td> 
  </tr> 
  <tr> 
 <td> Adresse email sur liste bloquée<br /> </td> 
    <td> Sélectionne les destinataires dont l'adresse email se trouve sur la liste bloquée.<br/> </td>
  </tr> 
  <tr> 
   <td> Email en quarantaine<br /> </td> 
   <td> Sélection des destinataires dont l'email est en quarantaine.<br /> </td> 
  </tr> 
  <tr> 
   <td> Emails dupliqués dans le dossier<br /> </td> 
   <td> Sélection des destinataires dont l'email est dupliqué dans le dossier.<br /> </td> 
  </tr> 
  <tr> 
   <td> N'ayant ni ouvert ni cliqué<br /> </td> 
   <td> Sélection des destinataires qui n'ont ni ouvert une diffusion, ni cliqué dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nouveaux destinataires (jours)<br /> </td> 
   <td> Sélection des destinataires qui ont été créés dans les X derniers jours.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nouveaux destinataires (minutes)<br /> </td> 
   <td> Sélection des destinataires qui ont été créés dans les X dernières minutes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nouveaux destinataires (mois)<br /> </td> 
   <td> Sélection des destinataires qui ont été créés dans les X derniers mois.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par abonnement<br /> </td> 
   <td> Sélection des destinataires par abonnements.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par clic sur une URL spécifique<br /> </td> 
   <td> Sélection des destinataires qui ont cliqué sur une URL particulière dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par comportement après une diffusion<br /> </td> 
   <td> Sélection des destinataires en fonction de leur comportement après la réception d'une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par date de création<br /> </td> 
   <td> Sélection des destinataires par date de création, sur une période entre X mois (date courante moins n mois) et Y mois (date courante moins n mois).<br /> </td> 
  </tr> 
  <tr> 
   <td> Par liste<br /> </td> 
   <td> Sélection des destinataires par liste.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par nombre de clics<br /> </td> 
   <td> Sélection des destinataires qui ont cliqué dans une diffusion dans les X derniers mois.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par nombre de messages reçus<br /> </td> 
   <td> Sélection des destinataires en fonction du nombre de messages qu'ils ont reçus.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par nombre d'ouvertures<br /> </td> 
   <td> Sélection des destinataires qui ont ouvert entre X et Y diffusions dans une période de temps Z.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par nom ou email<br /> </td> 
   <td> Sélection des destinataires en fonction de leur nom ou de leur email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Par tranche d'âge<br /> </td> 
   <td> Sélection des destinataires en fonction de leur âge.<br /> </td> 
  </tr> 
 </tbody> 
</table>


### Filtres par défaut{#default-filters}

Les champs situés au-dessus de chaque liste permettent d&#39;utiliser le **filtre par défaut prédéfini** pour cette liste. Pour la liste des destinataires, vous pouvez par défaut filtrer par nom et adresse e-mail.

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>Le caractère **%** remplace n&#39;importe quelle chaîne de caractères. Par exemple, saisissez `%@gmail.com` dans le champ E-mail pour afficher tous les profils ayant une adresse Gmail. Saisissez `%@L` dans le champ Nom pour afficher tous les profils dont le nom contient un L.

Pour modifier le filtre par défaut d&#39;une liste de destinataires, accédez au nœud **[!UICONTROL Profils et cibles > Filtres prédéfinis]**.

Pour tout autre type de données, configurez le filtre par défaut à partir du noeud **[!UICONTROL Administration > Paramétrage > Filtres prédéfinis]**.

Les étapes sont les suivantes :

1. Dans la liste des filtres, sélectionnez le filtre que vous souhaitez voir proposé par défaut.
1. Cliquez sur l&#39;onglet **[!UICONTROL Paramètres]** et cochez l&#39;option **[!UICONTROL Filtre par défaut pour le type de document associé]**.

   ![](assets/change-default-filter.png)

1. Décochez cette même option pour le filtre prédéfini par défaut actuel.
1. Cliquez sur le bouton **[!UICONTROL Enregistrer]** pour appliquer ce filtre.
1. Accédez au dossier Destinataire et cliquez sur l&#39;icône **[!UICONTROL Supprimer ce filtre]** à droite du filtre actuel : le nouveau filtre par défaut est disponible.
   ![](assets/updated-default-filter.png)


## Filtres rapides{#quick-filters}

Utilisez et combinez les **Filtres rapides** pour définir des filtres sur des champs spécifiques.

Une fois ajoutés, les champs de filtre rapide s&#39;affichent au-dessus de la liste de données, les uns après les autres. Ils peuvent être supprimés indépendamment les uns des autres.

Les filtres rapides sont spécifiques à chaque opérateur et sont réinitialisés à chaque fois que l&#39;opérateur vide le cache de la console cliente.

Si vous devez réutiliser un filtre, créez un **filtre avancé** et enregistrez-le. [En savoir plus](#advanced-filters).

Pour créer un **filtre rapide**, procédez comme suit :

1. Cliquez avec le bouton droit sur le champ sur lequel vous souhaitez filtrer les données et choisissez **[!UICONTROL Filtrer sur ce champ]**.

   ![](assets/quick-filter-on-this-field.png)

   Les champs de filtrage par défaut s&#39;affichent au-dessus de la liste.

   ![](assets/quick-filter-above-list.png)

1. Sélectionnez les options de filtrage.
1. Si nécessaire, utilisez l&#39;icône grise sur le côté droit d&#39;un filtre pour le supprimer.
1. Vous pouvez combiner des filtres pour affiner votre filtrage.

   ![](assets/add-filter-above-the-list.png)


Si vous devez appliquer un filtre sur un champ qui n&#39;est pas disponible dans le formulaire, il doit figurer dans les colonnes et être filtré sur cette colonne. Pour ce faire :

1. Cliquez sur l&#39;icône **[!UICONTROL Configurer la liste]**.

   ![](assets/configure-list.png)

1. Sélectionnez la colonne à afficher, par exemple l&#39;âge des destinataires, puis cliquez sur **OK**.

   ![](assets/add-age-column.png)

1. Cliquez ensuite avec le bouton droit dans la liste des destinataires, dans la colonne **Age**, et choisissez **[!UICONTROL Filtrer sur cette colonne]**.

   ![](assets/age-filter-on-this-column.png)

   Vous pouvez alors sélectionner les options de filtrage sur l&#39;âge. Ajoutez un autre filtre sur l&#39;âge pour définir une plage.

   ![](assets/filter-on-age.png)

## Filtres avancés{#advanced-filters}

Combinez des critères complexes dans **Filtres avancés**. Utilisez ces filtres pour créer une requête complexe ou une combinaison de requêtes sur vos données. Ces filtres peuvent être enregistrés et partagés avec d&#39;autres utilisateurs de Campaign.

### Créer un filtre avancé{#create-adv-filters}

Pour créer un **filtre avancé**, cliquez sur le bouton **[!UICONTROL Filtres]** et sélectionnez **[!UICONTROL Filtre avancé...]**.

![](assets/adv-filter.png)

Vous pouvez également cliquer avec le bouton droit dans la liste de données et sélectionner **[!UICONTROL Filtre avancé...]**.

Définissez les conditions de filtrage. Dans l&#39;exemple ci-dessous, vous allez filtrer les destinataires dont le numéro de compte ne commence pas par NL et qui résident à Paris ou Los Angeles.

1. Cliquez sur l&#39;icône **[!UICONTROL Modifier l&#39;expression]** de la colonne **[!UICONTROL Expression]**.

   ![](assets/edit-exp.png)

1. Sélectionnez le champ sur lequel appliquer le filtre.
1. Sélectionnez l&#39;opérateur à appliquer dans la liste déroulante.

   ![](assets/select-operator.png)

1. Sélectionnez une valeur attendue dans la colonne **[!UICONTROL Valeur]**. Vous pouvez combiner plusieurs filtres pour affiner votre requête. Pour ajouter un critère de filtrage, cliquez sur le bouton **[!UICONTROL Ajouter]**.

   ![](assets/add-an-exp.png)

   >[!NOTE]
   >
   >Vous pouvez hiérarchiser les expressions ou modifier l&#39;ordre des expressions de la requête en utilisant les flèches de la barre d&#39;outils.

1. Trois opérateurs sont disponibles pour combiner des expressions :  **Et**, **Ou**, **Sauf**. Cliquez sur la flèche pour passer à **Ou**.

   ![](assets/select-or-operator.png)

1. Cliquez sur **[!UICONTROL OK]** pour créer le filtre et l&#39;appliquer à la liste actuelle.

Le filtre appliqué est affiché au-dessus de la liste.

![](assets/adv-filter-link.png)

Pour éditer ou modifier ce filtre, cliquez sur son lien de description en bleu, au-dessus de la liste.


### Enregistrer un filtre avancé{#save-adv-filters}

Vous pouvez enregistrer un filtre avancé en tant que [filtre prédéfini](#predefined-filters), afin de pouvoir le réutiliser et le partager avec les autres utilisateurs de Campaign.

Pour enregistrer un filtre avancé, procédez comme suit :

1. Cliquez sur la description du filtre pour le modifier.
1. Cliquez sur l&#39;icône **[!UICONTROL Enregistrer en tant que filtre]** dans la section supérieure droite de la fenêtre.

   ![](assets/save-as-filter.png)

1. Saisissez le nom de ce filtre et enregistrez-le.

   ![](assets/application-filter-save.png)

Le filtre est ajouté aux [filtres prédéfinis](#predefined-filters). Il peut être mis à jour à partir de ce nœud.

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>Vous pouvez ajouter un raccourci pour votre filtre afin de l&#39;activer à partir du clavier.



Ce filtre est également disponible dans les filtres prédéfinis de la liste des destinataires.

![](assets/access-to-new-predefined-filter.png)



### Utiliser un filtre pour définir un segment {#filter-as-segment}

Vous pouvez utiliser et combiner des filtres pour créer un segment de population cible.

Une fois enregistrés, des filtres avancés sont disponibles lors de la sélection de la population cible d&#39;un message, dans la section **[!UICONTROL Filtres utilisateur]**.

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>Utilisez la variable **[!UICONTROL Exclure les destinataires correspondant à ce segment]** pour cibler uniquement les contacts qui ne correspondent pas aux critères de filtre.


### Utiliser des fonctions pour créer des filtres avancés{#use-functions-adv-filters}

Pour effectuer des fonctionnalités de filtre avancé, utilisez des fonctions pour définir le contenu du filtre. L&#39;éditeur de filtres avancés exploite toutes les fonctionnalités du requêteur de Campaign.

Découvrez comment créer des requêtes avancées dans la documentation d&#39;Adobe Campaign Classic v7. Par exemple :

* Découvrez comment cibler des attributs de destinataires simples dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=fr#example--targeting-on-simple-recipient-attributes){target=&quot;_blank&quot;}.
* Découvrez comment filtrer les destinataires non contactés au cours des 7 derniers jours dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html?lang=fr){target=&quot;_blank&quot;}.
* Découvrez comment la liste des opérateurs peut être filtrée par comptes actifs dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/creating-a-filter.html?lang=fr){target=&quot;_blank&quot;}.
* Découvrez comment créer une audience e-mail d&#39;anniversaire dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=fr#identifying-recipients-whose-birthday-it-is){target=&quot;_blank&quot;}.


### Paramètres avancés des filtres prédéfinis {#param-for-data-filters}

Des paramètres avancés sont disponibles pour les filtres prédéfinis. Pour y accéder, accédez à l&#39;onglet **[!UICONTROL Paramètres]** du filtre.

* Pour afficher le filtre par défaut pour toutes les listes basées sur ce type de document, sélectionnez l&#39;option **[!UICONTROL Filtre par défaut pour le type de document associé]**.

   Par exemple, le filtre **[!UICONTROL Par nom ou nom d&#39;utilisateur]** est appliqué aux opérateurs. Cette option est sélectionnée afin que le filtre soit systématiquement proposé sur toutes les listes d&#39;opérateurs.

* Pour mettre un filtre à disposition de tous les opérateurs Campaign, sélectionnez l&#39;option **[!UICONTROL Filtre partagé avec les autres opérateurs]**.

* Pour définir un formulaire de sélection des critères de filtrage, sélectionnez l&#39;option **[!UICONTROL Utiliser le formulaire de saisie des paramètres]**. Ce formulaire doit être saisi au format XML dans l&#39;onglet **[!UICONTROL Formulaire]**. Par exemple, le filtre prédéfini intégré **[!UICONTROL Destinataires ayant ouvert]**, disponible dans la liste des destinataires, affiche un champ de filtre qui permet de sélectionner la diffusion à laquelle s&#39;applique le filtre.

![](assets/predefined-filters-parameters.png)


* Le lien **[!UICONTROL Paramètres avancés]** permet de définir des paramètres supplémentaires.

   * Vous pouvez associer une table SQL au filtre pour qu&#39;elle soit commune à tous les éditeurs qui la partagent.
   * Pour empêcher un utilisateur de remplacer le filtre, sélectionnez l&#39;option **[!UICONTROL Ne pas restreindre le filtre]**. Par exemple, cette option est active pour les filtres « Destinataires d&#39;une diffusion » et « Destinataires des diffusions appartenant à un dossier » disponibles dans l&#39;assistant de diffusion. Ces filtres ne peuvent pas être surchargés.
