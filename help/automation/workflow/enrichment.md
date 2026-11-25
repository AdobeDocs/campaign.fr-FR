---
product: campaign
title: Enrichissement
description: En savoir plus sur l’activité de workflow d’enrichissement
feature: Workflows, Enrichment Activity, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 23bfabac-62cc-4f86-a739-a34a0e183c31
TQID: 'https://experienceleague.adobe.com/f5zQLS5AXT8OcK4BVB0oH6qShvjmZfTgUS6uchiEsZ8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: a643fca8-db7d-5178-8513-7b8f51dfd239
    internal-label: Enrichment Activity
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '1859'
ht-degree: 76%
---
# Enrichissement{#enrichment}



L’activité **[!UICONTROL Enrichissement]** permet d’ajouter des informations à une liste de profils et des liens vers une table existante (créer une nouvelle jointure). Des critères de réconciliation avec les profils de la base de données peuvent également être définis.

![Diagramme de workflow avec des activités d’enrichissement, telles que 3 newsletters et le service d’étiquettes, alimentant une activité Top 1000.](assets/enrichment_design.png)

## Définitions {#definitions}

Pour utiliser l’activité d’enrichissement, il est important de connaître les différentes possibilités offertes lors de l’ajout de données.

![Activité d&#39;enrichissement Ajout d&#39;un lien de données ouvrant l&#39;assistant Données additionnelles avec les cinq types de données à ajouter.](assets/enrichment_edit.png)

L&#39;option **[!UICONTROL Données liées à la dimension de filtrage]** vous donne accès aux :

* Données de la dimension de filtrage : accès aux données de la table de travail.
* Données liées à la dimension de filtrage : accès aux données liées à la table de travail.

![Sélectionnez les champs pour ajouter une page avec les données de la dimension de filtrage et les données liées aux options de la dimension de filtrage.](assets/wf_enrich_linkoptions.png)

L&#39;option **[!UICONTROL Un lien]** permet de créer une jointure sur n&#39;importe quelle table de la base de données.

![Page de définition du lien répertoriant les quatre types de liens, avec l&#39;option Définir une collection sélectionnée, et la section Cible du lien.](assets/wf_enrich_linkstype.png)

Il existe quatre types de liens :

* **[!UICONTROL Définir une collection]** : permet de définir un lien avec une cardinalité 1-N entre les tables.
* **[!UICONTROL Définir un lien dont la cible est toujours présente]** : permet de définir un lien avec une cardinalité 1-1 entre les tables. Les conditions de jointure doivent être définies par un seul enregistrement dans la table cible.
* **[!UICONTROL Définir un lien dont la cible peut ne pas exister dans la base]** : permet de définir un lien avec une cardinalité 0-1 entre les tables. La condition de jointure doit être définie par 0 ou 1 (max.) enregistrement dans la table cible.

  Cette option est configurée dans l&#39;onglet **[!UICONTROL Jointure Simple]**, accessible par le lien **[!UICONTROL Editer les données additionnelles]** de l&#39;activité **[!UICONTROL Enrichissement]**.

* **[!UICONTROL Définir un lien à travers la recherche d’une référence entre plusieurs options]** : ce type de lien définit une réconciliation vers un enregistrement unique. Adobe Campaign crée un lien vers une table cible en ajoutant une clé étrangère permettant de stocker une référence vers l’enregistrement unique.

  Cette option est configurée dans l&#39;onglet **[!UICONTROL Réconciliation &amp; déduplication]**, accessible par le lien **[!UICONTROL Editer les données additionnelles]** de l&#39;activité **[!UICONTROL Enrichissement]**.

Les cas d’utilisation détaillant le fonctionnement des activités d’enrichissement dans leur contexte sont également disponibles dans les sections suivantes :

* [Enrichissement des emails avec des champs de date personnalisés](email-enrichment-with-custom-date-fields.md).
* [Enrichir des données](enrich-data.md)
* [Créer une liste récapitulative](create-a-summary-list.md)

## Ajouter des informations {#adding-information}

Utilisez l&#39;activité **[!UICONTROL Enrichissement]** pour ajouter des données additionnelles à la table de travail du workflow : cette activité peut être utilisée en complément d&#39;une activité de requête.

Le paramétrage des colonnes additionnelles est présenté dans la section [Ajouter des données](query.md#adding-data).

Le champ **[!UICONTROL Ensemble principal]** permet de sélectionner la transition entrante : ce sont les données de la table de travail de cette activité qui seront enrichies.

Cliquez sur le lien **[!UICONTROL Ajouter des données]** et sélectionnez le type de données à ajouter. La liste des types de données proposés dépend des modules et options installés sur votre plateforme. Dans une configuration minimale, vous pouvez toujours ajouter des données liées à la dimension de filtrage et un lien.

![Activité d&#39;enrichissement Ajout d&#39;un lien de données ouvrant l&#39;assistant Données additionnelles avec les cinq types de données à ajouter.](assets/enrichment_edit.png)

Dans l&#39;exemple ci-dessous, la transition sortante sera enrichie avec les informations relatives à l&#39;âge des profils ciblés.

![Données à ajouter à la page avec le champ Âge sélectionné sous la dimension Ciblage et répertorié dans les colonnes Sortie.](assets/enrichment_add_data.png)

Cliquez avec le bouton droit sur la transition entrante de l’activité d’enrichissement pour visualiser les données avant l’étape d’enrichissement.

![Menu contextuel sur la transition après Union 2 avec l&#39;option Afficher la cible mise en surbrillance.](assets/enrichment_content_before.png)

La table de travail contient les données suivantes et le schéma associé :

![Affichez la population avec les données de la table de travail avant l&#39;enrichissement et son schéma avec la clé de Principal et la dimension de ciblage.](assets/enrichment_content_before_a.png)

Renouvelez cette opération en sortie de l&#39;étape d&#39;enrichissement.

![Menu contextuel sur la transition après l&#39;activité Enrichissement 3 avec l&#39;option Afficher la cible mise en surbrillance.](assets/enrichment_content_after.png)

Vous pouvez constater que les données relatives à l&#39;âge des profils ont été ajoutées :

![Affichez la population avec la colonne Âge ajoutée et le schéma enrichi avec l&#39;Âge, la clé de Principal et la dimension de ciblage.](assets/enrichment_content_after_a.png)

Le schéma correspondant a également été enrichi.

## Gérer les données additionnelles {#managing-additional-data}

Désélectionnez l’option **[!UICONTROL Conserver toutes les données additionnelles de l’ensemble principal]** si vous ne souhaitez pas conserver les données additionnelles définies précédemment. Dans ce cas, seules les colonnes supplémentaires sélectionnées dans l’activité d’enrichissement seront ajoutées à la table de travail sortante. Les informations supplémentaires ajoutées aux activités en amont ne seront pas enregistrées.

![Onglet Enrichissement avec Conserver toutes les données supplémentaires de l’ensemble principal effacées et uniquement l’Âge (dimension de ciblage) répertorié.](assets/enrichment_edit_without_additional.png)

Les données et le schéma en sortie de l&#39;étape d&#39;enrichissement seront alors les suivants :

![Affichez la fenêtre de population avec la colonne Âge et son schéma après l&#39;enrichissement sans le jeu principal de données supplémentaires.](assets/enrichment_content_after_without_additional.png)

## Créer un lien {#creating-a-link}

Vous pouvez utiliser l’activité d’enrichissement pour créer un lien entre les données de travail et les données de la base Adobe Campaign : il s’agira d’un lien local au workflow entre les données entrantes.

Par exemple, si vous chargez les données d&#39;un fichier contenant le numéro de compte, le pays et l&#39;email des destinataires, vous devez créer un lien vers la table des pays afin de mettre à jour cette information dans leur profil.

Pour cela, les étapes sont les suivantes :

1. Collectez et chargez un fichier de type :

   ```
   Account number;Country;Email
   18D65;FRANCE;agnes@gmail.com
   243PP;RUSSIA;paul@gmail.com
   55H87;CROATIA;dave@gmail.com
   56U81;USA;susan@gmail.com
   853PI;ITALY;anna@gmail.com
   890LP;FRANCE;robert@gmail.com
   83TY2;SWITZERLAND;mike@gmail.com
   ```

1. Modifiez l’activité d’enrichissement et cliquez sur le lien **Ajouter des données…** pour créer une jointure avec la table des Pays.

   ![Workflow avec collecteur de fichiers, chargement (fichier) et enrichissement des données, avec le lien Ajouter des données de l’activité d’enrichissement.](assets/enrichment_edit_after_file_box.png)

1. Sélectionnez l’option **[!UICONTROL Définition du lien]** et cliquez sur le bouton **[!UICONTROL Suivant]**. Spécifiez le type de lien à créer. Dans cet exemple, nous allons réconcilier le pays de la personne destinataire du fichier avec un pays dans la liste des pays disponibles de la table dédiée de la base de données. Vous devez donc choisir l&#39;option **[!UICONTROL Définir un lien en recherchant une référence parmi plusieurs possibilités]**. Sélectionnez la table des pays dans le champ **[!UICONTROL Schéma cible]**.

   ![Définition d&#39;un lien avec Définissez un lien en recherchant une référence parmi plusieurs options et la cible Pays (nms).](assets/enrichment_add_a_link_select_option4.png)

1. Sélectionnez enfin le ou les champs qui permettront d&#39;associer les valeurs du fichier source avec celles de la base de données.

   ![Conditions de jointure de la définition de lien mappant le pays source au champ Libellé anglais du schéma Pays.](assets/enrichment_add_a_link_select_join.png)

En sortie de cette activité d’enrichissement, le schéma temporaire contiendra le lien vers la table des pays :

![Onglet Schéma de la fenêtre de résultats affichant la structure générée avec la clé étrangère et le lien Pays et ses champs.](assets/enrichment_external_link_schema.png)

## Réconciliation des données {#data-reconciliation}

L’activité d’enrichissement peut être utilisée pour paramétrer la réconciliation des données, notamment suite au chargement de données dans la base. Dans ce cas, l’onglet **[!UICONTROL Réconciliation]** permet de définir le lien entre les données de la base Adobe Campaign et les données de la table de travail.

Sélectionnez l&#39;option **[!UICONTROL Identifier le document de ciblage à partir des données de travail]** et indiquez le schéma vers lequel vous souhaitez faire le lien et indiquez les conditions de jointure : pour cela, sélectionnez les champs à réconcilier dans les données de travail (**[!UICONTROL Expression source]**) et dans la dimension de ciblage (**[!UICONTROL Expression destination]**).

Vous pouvez utiliser un ou plusieurs critères de réconciliation.

![Onglet Réconciliation avec Identifier le document à partir des données de travail et des expressions source et de destination.](assets/enrichment_reconciliations_tab_01.png)

Si plusieurs conditions de jointure sont indiquées, elles doivent TOUTES être vérifiées pour que le lien entre les données puisse se faire.

## Insérer une proposition d&#39;offre {#inserting-an-offer-proposition}

L’activité d’enrichissement vous permet d’ajouter des offres ou des liens vers des offres pour les destinataires d’une diffusion.

Pour plus d’informations sur l’activité d’enrichissement, consultez cette [section](enrichment.md).

Vous pouvez par exemple enrichir les données d&#39;une requête sur les destinataires, avant une diffusion.

![Workflow avec une activité Requête , une activité Enrichissement et une activité Diffusion Courrier connectées en séquence.](assets/int_enrichment_offer1.png)

Après avoir paramétré votre requête (voir cette [section](query.md)) :

1. Placez et ouvrez une activité d’enrichissement.
1. Dans l&#39;onglet **[!UICONTROL Enrichissement]**, sélectionnez **[!UICONTROL Ajouter des données]**.
1. Sélectionnez **[!UICONTROL Une proposition d&#39;offre]** dans les types de données à ajouter.

   ![Sélectionnez le type de données à ajouter à la page avec une proposition d&#39;offre sélectionnée.](assets/int_enrichment_offer2.png)

1. Indiquez un identifiant ainsi qu&#39;un libellé pour la proposition qui sera ajoutée.
1. Définissez la sélection de l’offre. Deux options sont possibles :

   * **[!UICONTROL Rechercher la meilleure offre dans une catégorie]** : cochez cette option et définissez les paramètres de l’appel au moteur d’offres (emplacement, catégorie ou thématique, date de contact, nombre d’offres à conserver). Le moteur calculera automatiquement la ou les offres à ajouter en fonction de ces paramètres. Nous vous recommandons de renseigner soit le champ **[!UICONTROL Catégorie]**, soit le champ le **[!UICONTROL Thème]**, plutôt que les deux à la fois.

     ![Page de proposition d&#39;offre avec les champs Identifiant, Libellé, Emplacement, Catégorie d&#39;offres et Date de contact pour la meilleure recherche d&#39;offres.](assets/int_enrichment_offer3.png)

   * **[!UICONTROL Une offre prédéfinie]** : cochez cette option et définissez un emplacement, une offre précise, ainsi qu&#39;une date de contact afin de directement paramétrer l&#39;offre que vous souhaitez ajouter, sans appeler le moteur d&#39;offres.

     ![Page de proposition d&#39;offre avec identifiant, libellé, emplacement, une offre spécifique et date de contact pour une offre prédéfinie.](assets/int_enrichment_offer4.png)

1. Paramétrez ensuite une activité de diffusion correspondant au canal de votre choix. Pour plus d&#39;informations, consultez la section [Diffusions cross-canal](cross-channel-deliveries.md).

   Le nombre de propositions disponibles pour la prévisualisation dépend du paramétrage réalisé dans l’activité d’enrichissement et non d’un éventuel paramétrage directement dans la diffusion.

Pour spécifier des propositions d’offres, vous pouvez également choisir de référencer un lien vers une offre. Voir à ce sujet la section [Référencer un lien vers une offre](#referencing-a-link-to-an-offer).

## En référençant un lien vers une offre {#referencing-a-link-to-an-offer}

Vous avez également la possibilité de référencer un lien vers une offre dans une activité d’enrichissement.

Pour cela :

1. Dans l&#39;onglet **[!UICONTROL Enrichissement]** de l&#39;activité, sélectionnez **[!UICONTROL Ajouter des données]**.
1. Dans la fenêtre de sélection du type de données à ajouter, choisissez **[!UICONTROL Un lien]**.
1. Sélectionnez le type du lien que vous souhaitez établir ainsi que sa cible. Dans ce cas, la cible est le schéma de l’offre.

   ![Page de définition du lien avec un lien dont la cible est toujours disponible et Offres marketing (nms) comme schéma cible.](assets/int_enrichment_link1.png)

1. Définissez la jointure entre les données de la table entrante dans l’activité d’enrichissement (ici la table de destinataire) et la table d’offre. Vous pouvez, par exemple, lier un code d’offre à une personne destinataire.

   ![Conditions de jointure de la définition du lien liant l&#39;ID chiffré source au code de l&#39;offre, avec l&#39;offre Identifier.](assets/int_enrichment_link2.png)

1. Paramétrez ensuite une activité de diffusion correspondant au canal de votre choix. Pour plus d&#39;informations, consultez la section [Diffusions cross-canal](cross-channel-deliveries.md).

   >[!NOTE]
   >
   >Le nombre de propositions disponibles pour la prévisualisation dépend du paramétrage réalisé dans la diffusion.

## Stocker le rang et le poids des offres {#storing-offer-rankings-and-weights}

Par défaut, lorsque l&#39;activité d&#39;**enrichissement** est utilisée pour diffuser des offres, leur rang ainsi que leur poids ne sont pas stockés dans la table des propositions.

L&#39;activité **[!UICONTROL Moteur d&#39;offres]** stocke bien ces informations par défaut.

Cependant, il est possible de stocker ces informations de la manière suivante :

1. Créez un appel au moteur d’offre dans une activité d’enrichissement placée après une requête et avant une activité de diffusion.
1. Dans la fenêtre principale de l&#39;activité, sélectionnez **[!UICONTROL Editer les données additionnelles]**.

   ![Onglet Enrichissement répertoriant les colonnes de la proposition d&#39;offre, avec le lien Modifier les données additionnelles en surbrillance.](assets/ita_enrichment_rankweight_1.png)

1. Ajoutez les colonnes **[!UICONTROL @rank]** pour le rang et **[!UICONTROL @weight]** pour le poids des offres.

   ![Sélectionnez une fenêtre de colonnes supplémentaires avec des colonnes Poids et Classement ajoutées à la proposition à l&#39;aide de l&#39;option Ajouter un sous-élément.](assets/ita_enrichment_rankweight_2.png)

1. Validez votre ajout et enregistrez votre workflow.

La diffusion stocke automatiquement le rang et le poids des offres. Ces informations sont visibles dans l’onglet **[!UICONTROL Offres]** de la diffusion.
