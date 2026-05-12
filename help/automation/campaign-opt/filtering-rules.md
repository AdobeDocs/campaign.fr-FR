---
product: campaign
title: Configurer les règles de filtrage
description: Découvrir comment utiliser les règles de filtrage
feature: Typology Rules
exl-id: 17507cdf-211f-4fa2-abb9-33d4f6dc47bb
TQID: https://experienceleague.adobe.com/4dOJKJq9bGT93592ugAfrbQU27OBBpUp25QRpzDqtW0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 550
ht-degree: 86%

---

# Règles de filtrage{#filtering-rules}

Utilisez les règles de filtrage pour sélectionner les messages à exclure en fonction des critères définis dans une requête. Ces règles sont liées à une dimension de ciblage.

Les règles de filtrage peuvent être associées à d’autres types de règles (contrôle, pression, etc.) dans les typologies, ou regroupées dans une typologie dédiée **Filtrage**. [En savoir plus](#create-and-use-a-filtering-typology).

## Création dʼune règle de filtrage {#create-a-filtering-rule}

Vous pouvez par exemple filtrer les abonnés à vos newsletters afin de ne jamais adresser de communications aux inscrits mineurs.

Pour définir ce filtrage, les étapes sont les suivantes :

1. Accédez au dossier **[!UICONTROL Administration > Gestion de campagne > Gestion des typologies > Règles de typologie]** de l’explorateur Campaign, puis cliquez sur l’icône **Nouveau** pour créer une règle de typologie.
1. Créez une règle de typologie de type **[!UICONTROL Filtrage]**, applicable à tous les canaux.

   ![](assets/campaign_opt_create_filter_01.png)

1. Dans l’onglet **Filtre** modifiez la dimension de ciblage par défaut en **Abonnements** (**nms:subscription**).

   ![](assets/campaign_opt_create_filter_02.png)

1. Créez le filtre à partir du lien **[!UICONTROL Editer la requête à partir de la dimension de ciblage...]**.

   ![](assets/campaign_opt_create_filter_03.png)

1. Filtrez par âge des destinataires et enregistrez la condition de filtrage.

   ![](assets/campaign_opt_create_filter_03b.png)

1. Sous l’onglet **Typologies**, liez cette règle à une typologie de campagne et enregistrez-la.

   ![](assets/campaign_opt_create_filter_04.png)

Lorsque cette règle est utilisée dans une diffusion, les abonnés mineurs sont automatiquement exclus. Un message spécifique indique à quel moment la règle est appliquée :

![](assets/campaign_opt_create_filter_05.png)

## Traitement dʼune règle de filtrage {#condition-a-filtering-rule}

Vous pouvez restreindre le champ d’application de la règle de filtrage en fonction de la diffusion ou de la composition de diffusion associée.

Pour ce faire, accédez à l’onglet **[!UICONTROL Général]** de la règle de typologie, sélectionnez le type de restriction à appliquer et créez le filtre.
<!--
![](assets/campaign_opt_create_filter_06.png)
-->


Dans ce cas, même si la règle est associée à toutes les diffusions, elle ne sera appliquée qu’aux diffusions répondant aux critères du filtre défini.

>[!NOTE]
>
>Les typologies et les règles de filtrage peuvent être utilisées dans un workflow, dans l&#39;activité **[!UICONTROL Composition de diffusion]**. [En savoir plus](../workflow/delivery-outline.md).

## Création et utilisation dʼune typologie de filtrage {#create-and-use-a-filtering-typology}

Vous pouvez créer des typologies de **[!UICONTROL Filtrage]** : elles ne contiennent que des règles de filtrage.

![](assets/campaign_opt_create_typo_filtering.png)

Ces typologies spécifiques peuvent être associées à une diffusion lors du choix de la cible : dans l&#39;assistant de diffusion, cliquez sur le lien **[!UICONTROL Pour]**, puis sur l&#39;onglet **[!UICONTROL Exclusions]**.

![](assets/campaign_opt_apply_typo_filtering.png)

Sélectionnez ensuite la typologie de filtrage à appliquer à la diffusion. Pour ce faire, cliquez sur le bouton **[!UICONTROL Ajouter]** et sélectionnez les typologies à appliquer.

Vous pouvez également lier des règles de filtrage directement à partir de cet onglet, sans qu&#39;elles ne soient regroupées dans une typologie. Pour ce faire, utilisez la section inférieure de la fenêtre.

![](assets/campaign_opt_select_typo_filtering.png)

>[!NOTE]
>
>Seules les typologies et règles de filtrage sont proposées dans la fenêtre de sélection.
>
>Ces paramétrages peuvent être définis au niveau du modèle de diffusion afin de les appliquer automatiquement à toute nouvelle diffusion créée à partir de ce modèle.
>

## Règles d&#39;exclusion de délivrabilité par défaut {#default-deliverability-exclusion-rules}

Deux règles de filtrage sont disponibles par défaut : **[!UICONTROL Exclusion des adresses]** ( **[!UICONTROL addressExclusions]** ) et **[!UICONTROL Exclusion des domaines]** ( **[!UICONTROL domainExclusions]** ). Pendant l’analyse de l’e-mail, ces règles comparent les adresses e-mail des destinataires aux adresses ou noms de domaine interdits contenus dans une liste de suppression globale chiffrée, gérée dans l’instance de délivrabilité. S&#39;il existe une correspondance, le message n&#39;est pas envoyé au destinataire concerné.

Ces règles d’exclusion permettent d’éviter toute mise en liste bloquée liée à une activité malveillante, notamment l’utilisation d’un spam trap (piège à spam). Si un spam trap est par exemple utilisé pour s’abonner par le biais de l’un de vos formulaires web, un email de confirmation lui est automatiquement envoyé. Votre adresse est alors automatiquement mise en liste bloquée.

>[!NOTE]
>
>Les adresses et les noms de domaine contenus dans la liste de suppression globale sont masqués. Seul le nombre des personnes destinataires exclues est indiqué dans les logs d’analyse de diffusion.
