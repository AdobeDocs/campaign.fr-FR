---
title: Création d'un schéma dans Campaign
description: Découvrez comment créer un schéma dans Campaign
feature: Schema Extension, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 796af848-b537-4b8d-a601-fe0628a1fc83
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 100%

---

# Création d&#39;un schéma {#create-new-schema}

Pour modifier, créer et paramétrer les schémas, cliquez sur le nœud **[!UICONTROL Administration > Configuration > Schémas de données]** de la console cliente Adobe Campaign.

>[!NOTE]
>
>Les schémas de données natifs peuvent uniquement être supprimés par un administrateur ou une administratrice de votre console Adobe Campaign 

![](assets/schema_navtree.png)

L&#39;onglet **[!UICONTROL Édition]** affiche le contenu XML d&#39;un schéma :

![](assets/schema_edition.png)

>[!NOTE]
>
>Le contrôle de modification &quot;Nom&quot; permet de saisir la clé du schéma, composée du nom et de l&#39;espace de noms. Les attributs &quot;name&quot; et &quot;namespace&quot; de l&#39;élément racine du schéma sont automatiquement mis à jour dans la zone d&#39;édition XML du schéma. Notez que certains espaces de noms sont internes uniquement. [En savoir plus](schemas.md#reserved-namespaces)

L&#39;onglet **[!UICONTROL Aperçu]** génère automatiquement le schéma étendu :

![](assets/schema_edition2.png)

>[!NOTE]
>
>L&#39;enregistrement du schéma source lance automatiquement la génération du schéma étendu.

Si vous devez vérifier la structure complète d’un schéma, vous pouvez utiliser l’onglet **[!UICONTROL Aperçu]**. Si le schéma a été étendu, vous pourrez visualiser toutes ses extensions. En complément, l’onglet **[!UICONTROL Documentation]** affiche tous les attributs et éléments du schéma, ainsi que ses propriétés (champ SQL, type/longueur, libellé, description). L’onglet **[!UICONTROL Documentation]** s’applique uniquement aux schémas générés.

## Cas d&#39;utilisation : créer une table des contrats {#example--creating-a-contract-table}

L&#39;exemple suivant montre la création d&#39;une table pour les **contrats** dans la base de données. Cette table vous permet de stocker les noms, prénoms et adresses e-mail des titulaires et co-titulaires pour chaque contrat.

Pour cela, vous devez créer le schéma de la table puis procéder à la mise à jour de la structure de la base pour générer la table correspondante. Les étapes détaillées sont répertoriées ci-dessous.

1. Modifiez le nœud **[!UICONTROL Administration > Paramétrage > Schémas de données]** de l&#39;arborescence Adobe Campaign et cliquez sur l&#39;icône **[!UICONTROL Nouveau]**.
1. Sélectionnez l&#39;option **[!UICONTROL Créer une nouvelle table dans le modèle de données de la base]** et cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/create_new_schema.png)

1. Indiquez le nom de la table et son espace de noms.

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >Par défaut, les schémas créés par les utilisateurs sont stockés dans l&#39;espace de noms « cus ». Pour plus d&#39;informations, consultez la section [Identification d&#39;un schéma](extend-schema.md#identification-of-a-schema).

1. Créez le contenu de la table. Nous vous recommandons d&#39;utiliser l&#39;assistant dédié pour vous assurer qu&#39;aucun paramètre n&#39;est manquant. Pour ce faire, cliquez sur le bouton **[!UICONTROL Insérer]** et sélectionnez le type de paramètre à ajouter.

   ![](assets/create_new_content.png)

1. Définissez les paramètres de la table des contrats.

   Il est recommandé de créer la table dans la base de données cloud en ajoutant l&#39;attribut `dataSource="nms:extAccount:ffda"`. Cet attribut est ajouté par défaut lors de la création d&#39;une nouvelle table.

   ```xml
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

   ```xml
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

1. Enregistrez le schéma et cliquez sur l&#39;onglet **[!UICONTROL Structure]** pour générer la structure :

   ![](assets/configuration_structure.png)

1. Mettez à jour la structure de la base de données pour créer la table à laquelle le schéma sera lié. Pour plus d&#39;informations à ce sujet, consultez [cette section](update-database-structure.md).
