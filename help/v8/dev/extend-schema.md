---
solution: Campaign v8
product: Adobe Campaign
title: Extension des schémas Campaign
description: Découvrez comment étendre les schémas Campaign
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Étendre un schéma{#extend-schemas}

En tant qu&#39;utilisateur technique, vous pouvez personnaliser le modèle de données de Campaign pour répondre aux besoins de votre implémentation : ajouter des éléments à un schéma existant, modifier un élément dans un schéma ou supprimer des éléments.

Les étapes clés de personnalisation du modèle de données de Campaign sont les suivantes :

1. Création d’un schéma d’extension
1. Mise à jour de la base de données Campaign
1. Adapter le formulaire de saisie

>[!CAUTION]
>Le schéma intégré ne doit pas être modifié directement. Si vous devez adapter un schéma intégré, vous devez l’étendre.

:bulb: Pour une meilleure compréhension des tables natives de Campaign et de leur interaction, reportez-vous à [cette page](datamodel.md).

Pour étendre un schéma, procédez comme suit :

1. Accédez au dossier **[!UICONTROL Administration > Configuration > Schémas de données]** dans l’Explorateur.
1. Cliquez sur le bouton **New** et sélectionnez **[!UICONTROL Étendre les données d&#39;une table à l&#39;aide d&#39;un schéma d&#39;extension]**.

   ![](assets/extend-schema-option.png)

1. Identifiez le schéma intégré à étendre et sélectionnez-le.

   ![](assets/extend-schema-select.png)

   Par convention, nommez le schéma d’extension de la même manière que le schéma intégré et utilisez un espace de noms personnalisé.  Notez que certains espaces de noms sont internes uniquement. [En savoir plus](schemas.md#reserved-namespaces).

   ![](assets/extend-schema-validate.png)

1. Une fois dans l’éditeur de schéma, ajoutez les éléments dont vous avez besoin à l’aide du menu contextuel, puis enregistrez.

   ![](assets/extend-schema-edit.png)

   Dans l’exemple ci-dessous, nous ajoutons l’attribut MembershipYear , appliquons une limite de longueur pour le nom (cette limite va remplacer la valeur par défaut) et supprimons la date de naissance du schéma intégré.

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. Déconnectez-vous de Campaign et reconnectez-vous pour vérifier la mise à jour de la structure du schéma dans l&#39;onglet **[!UICONTROL Structure]** .

   ![](assets/extend-schema-structure.png)

1. Mettez à jour la structure de la base de données pour appliquer vos modifications. [En savoir plus](update-database-structure.md)

1. Une fois les modifications implémentées dans la base de données, vous pouvez adapter le formulaire de saisie des destinataires pour rendre vos modifications visibles. [En savoir plus](forms.md)
