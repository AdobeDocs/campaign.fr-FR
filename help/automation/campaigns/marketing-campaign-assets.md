---
product: campaign
title: Ressources de campagne marketing, documents et compositions de diffusion
description: En savoir plus sur les compositions de diffusions et sur les documents des campagnes marketing
feature: Campaigns
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
TQID: https://experienceleague.adobe.com/snshYvtbT3wG1N5-A4VHjl1bylxlXObi-97yVwuKAXk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 717
ht-degree: 69%

---

# Gérer les ressources et les documents {#manage-assets-documents}

Vous pouvez associer différents documents à une opération : rapports, photos, pages web, diagrammes, etc. Ces documents peuvent avoir n’importe quel format.

Dans une campagne, vous pouvez également faire référence à d’autres articles, tels que des coupons promotionnels, des offres spéciales liées à une marque ou à un magasin spécifique, etc. Lorsque ces éléments sont inclus dans une composition, ils peuvent être associés à une diffusion courrier. [En savoir plus](#associating-and-structuring-resources-linked-via-a-delivery-outline).


>[!CAUTION]
>
>Cette fonctionnalité est conçue pour les petites ressources et documents.

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## Ajout de documents {#add-documents}

Des documents peuvent être associés au niveau de l&#39;opération (documents contextuels) ou au niveau du programme (documents généraux).

Pour une opération, l&#39;onglet **[!UICONTROL Documents]** contient :

* La liste de tous les documents requis pour le contenu (modèle, images, etc.) qui peuvent être téléchargés localement par les opérateurs Adobe Campaign disposant des droits adéquats,
* les documents contenant des informations destinées au routeur, s&#39;ils existent.

Les documents sont rattachés au programme ou à l&#39;opération via leur onglet **[!UICONTROL Edition > Documents]**.

![](assets/op_add_document.png)

Vous pouvez également ajouter un document dans une opération via le lien dédié de son tableau de bord.

![](assets/add_a_document_in_op.png)

Cliquez sur l&#39;icône **[!UICONTROL Détails...]** pour afficher le contenu d&#39;un fichier et y ajouter des informations complémentaires :

![](assets/add_document_details.png)

Au niveau du tableau de bord, les documents associés à l&#39;opération sont regroupés dans la section **[!UICONTROL Document(s)]**, comme dans l&#39;exemple ci-dessous :

![](assets/edit_documents.png)

Ils peuvent également être édités et modifiés depuis cette vue.

## Utiliser les compositions de diffusion {#delivery-outlines}

Une composition de diffusion est un ensemble structuré d&#39;éléments (documents, magasins, coupons promotionnels, etc.) créé par la société et pour une opération particulière. Elle est utilisée dans le cadre de diffusions par publipostage direct.

Ces éléments sont regroupés au sein de compositions de diffusions, chacune associée à une diffusion. La composition de diffusion sera référencée dans le fichier d’extraction envoyé au **fournisseur** afin d’être jointe à la diffusion. Par exemple, vous pouvez créer une composition de diffusion faisant référence à une unité et aux brochures marketing qu&#39;elle utilise.

Les compositions de diffusions permettent, au niveau de l&#39;opération, de structurer des éléments externes qui seront associés à la diffusion en fonction de certains critères : entité de rattachement, offre promotionnelle accordée, invitation à un événement local, etc.

>[!CAUTION]
>
>Les compositions de diffusion sont limitées aux campagnes par publipostage direct.

### Créer une composition de diffusion {#create-an-outline}

Pour créer une composition de diffusion, cliquez sur le sous-onglet **[!UICONTROL Compositions de diffusion]** proposé sous l&#39;onglet **[!UICONTROL Modifier > Documents]** de l&#39;opération concernée.

![](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>Si cet onglet n&#39;est pas visible, cette fonctionnalité n&#39;est pas disponible pour cette opération ou alors la diffusion par publipostage direct n&#39;est pas activée dans votre instance. Reportez-vous à la section [configuration du modèle de campagne](marketing-campaign-templates.md#campaign-templates) ou référez-vous à votre contrat de licence.

Cliquez ensuite sur **[!UICONTROL Ajouter une composition de diffusion]** et créez l&#39;arborescence des compositions pour l&#39;opération :

1. Cliquez avec le bouton droit sur la racine de l&#39;arborescence et choisissez **[!UICONTROL Nouveau > Compositions de diffusion]**.
1. Cliquez avec le bouton droit de la souris sur la composition que vous venez de créer et choisissez **[!UICONTROL Nouveau > Article]** ou **[!UICONTROL Nouveau > Champs de personnalisation]**.

![](assets/del-outline-add-new-item.png)

Une composition peut contenir des articles, des champs de personnalisation et des offres :

* Les articles sont par exemple des documents physiques qui sont ici référencés et décrits, et seront joints à la diffusion.
* Les champs de personnalisation permettent de créer des éléments de personnalisation relatifs aux diffusions et non aux destinataires. Il est ainsi possible de créer des valeurs qui seront utilisées dans les diffusions pour une cible spécifique (offre de bienvenue, remise, etc.) Ils sont créés dans Adobe Campaign et importés dans la composition via le lien **[!UICONTROL Importer des champs de personnalisation...]** .

  ![](assets/del-outline-perso-field.png)

  Ils peuvent également être créés directement dans la composition, en cliquant sur l&#39;icône **[!UICONTROL Ajouter]** située à droite de la zone de liste.

  ![](assets/add-del-outline-button.png)


### Sélection d’une composition {#select-an-outline}

Pour chaque diffusion, vous pouvez sélectionner la composition à associer à partir de la section réservée à la configuration de l&#39;extraction, comme dans l&#39;exemple ci-dessous :

![](assets/select-delivery-outline.png)

La composition sélectionnée est alors affichée dans la section inférieure de la fenêtre. Elle peut être modifiée à l’aide de l’icône située à droite du champ ou dans la liste déroulante :

![](assets/delivery-outline-selected.png)

L&#39;onglet **[!UICONTROL Résumé]** de la diffusion affiche également cette information :

![](assets/delivery-outline-in-dashboard.png)

### Résultat de l&#39;extraction {#extraction-result}

Dans le fichier extrait et transmis au prestataire, le nom de la composition et le cas échéant ses caractéristiques (coût, description, etc.) sont ajoutées au contenu en fonction des informations du modèle d’exportation associé au fournisseur de services.

Dans l&#39;exemple suivant, le libellé, le coût prévisionnel estimé et la description de la composition associée à la diffusion seront ajoutés dans le fichier d&#39;extraction.

![](assets/campaign-export-template.png)

Le modèle d&#39;export doit être associé au prestataire sélectionné pour la diffusion concernée. Consultez [cette section](providers-stocks-and-budgets.md#creating-service-providers-and-their-cost-structures).
