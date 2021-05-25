---
solution: Campaign v8
product: Adobe Campaign
title: Création d’un nouveau schéma dans Campaign
description: Découvrez comment créer un nouveau schéma dans Campaign
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 37%

---

# Créer un nouveau schéma {#create-new-schema}

Pour éditer, créer et paramétrer les schémas, cliquez sur le nœud **[!UICONTROL Administration > Paramétrage > Schémas de données]** de la console cliente Adobe Campaign.

>[!NOTE]
>
>Les schémas de données intégrés ne peuvent être supprimés que par un administrateur de votre console Adobe Campaign Classic.

![](assets/schema_navtree.png)

L&#39;onglet **[!UICONTROL Edition]** affiche le contenu XML d&#39;un schéma :

![](assets/schema_edition.png)

>[!NOTE]
>
>Le contrôle d&#39;édition &quot;Nom&quot; permet de saisir la clé du schéma, composée du nom et de l&#39;espace de noms. Les attributs &quot;name&quot; et &quot;namespace&quot; de l&#39;élément racine du schéma sont automatiquement mis à jour dans la zone d&#39;édition XML du schéma. Notez que certains espaces de noms sont internes uniquement. [En savoir plus](schemas.md#reserved-namespaces).

L&#39;onglet **[!UICONTROL Aperçu]** génère automatiquement le schéma étendu :

![](assets/schema_edition2.png)

>[!NOTE]
>
>La sauvegarde du schéma source va automatiquement lancer la génération du schéma étendu.

Si vous devez vérifier la structure complète d&#39;un schéma, vous pouvez utiliser l&#39;onglet **[!UICONTROL Aperçu]**. Si le schéma a été étendu, vous pourrez visualiser toutes ses extensions. En complément, l’onglet **[!UICONTROL Documentation]** affiche tous les attributs et éléments du schéma, ainsi que leurs propriétés (champ SQL, type/longueur, libellé, description). L’onglet **[!UICONTROL Documentation]** s’applique uniquement aux schémas générés.

## Cas pratique : créer une table des contrats {#example--creating-a-contract-table}

Dans l&#39;exemple suivant, vous créez une table pour **contrats** dans la base de données. Cette table permet de stocker, pour chaque contrat, les prénoms et noms ainsi que les adresses email des titulaires et co-titulaires.

Pour cela, vous devez créer le schéma de la table et mettre à jour la structure de la base de données afin de générer la table correspondante. Les étapes détaillées sont répertoriées ci-dessous.

1. Editez le nœud **[!UICONTROL Administration > Paramétrage > Schémas de données]** de l&#39;arborescence Adobe Campaign et cliquez sur l&#39;icône **[!UICONTROL Nouveau]**.
1. Choisissez l&#39;option **[!UICONTROL Créer une nouvelle table dans le modèle de données]** et cliquez sur **[!UICONTROL Suivant]** .

   ![](assets/create_new_schema.png)

1. Indiquez le nom de la table et son espace de noms.

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >Par défaut, les schémas créés par les utilisateurs sont stockés dans l’espace de noms « cus ». Voir à ce propos la section [Identification d&#39;un schéma](extend-schema.md#identification-of-a-schema).

1. Créez le contenu du tableau. Nous vous recommandons d’utiliser l’assistant dédié pour vous assurer qu’aucun paramètre n’est manquant. Pour cela, cliquez sur le bouton **[!UICONTROL Insérer]** et choisissez le type de paramètre à ajouter.

   ![](assets/create_new_content.png)

1. Définissez les paramètres de la table des contrats :

   ```
   <srcSchema created="YYYY-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" lastModified="YYYY-MM-DD HH:MM:SS.TZ"
           mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

   Ajoutez le type d&#39;énumération de contrat.

   ```
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png" label="Contracts" labelSingular="Contract" AA-MM-DD HH:MM:SS.TZ"mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <enumeration basetype="byte" name="typeContract">
         <value label="Home" name="home" value="0"/>
         <value label="Car" name="car" value="1"/>
         <value label="Health" name="health" value="2"/>
         <value label="Pension fund" name="pension fund" value="2"/>
      </enumeration>
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

1. Enregistrez le schéma et cliquez sur l&#39;onglet **[!UICONTROL Structure]** pour générer la structure :

   ![](assets/configuration_structure.png)

1. Mettez à jour la structure de la base de données pour créer la table à laquelle le schéma sera lié. Pour plus d’informations à ce sujet, consultez [cette section](update-database-structure.md).

