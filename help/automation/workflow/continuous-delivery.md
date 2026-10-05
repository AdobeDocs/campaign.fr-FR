---
product: campaign
title: Diffusion continue
description: Diffusion continue
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: e3ad6d92-8d53-4098-90fd-cfed29f2e56e
TQID: 'https://experienceleague.adobe.com/1w3RSzcB8TDy7JLPqzH8COVIS1Uhz1l4-I5kr1o9Z-U'
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
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 100%
---
# Diffusion continue{#continuous-delivery}



L’activité de type **Diffusion continue** permet d’ajouter de nouvelles personnes destinataires à une diffusion existante. Ce type de diffusion évite d’avoir à créer une diffusion à chaque fois : ce mode est souvent plus efficace, plus particulièrement pour les alertes ou notifications à faible volume envoyées selon les besoins.

![](assets/do-not-localize/how-to-video.png) [Découvrez cette fonctionnalité en vidéo](#continuous-delivery-video)

Au niveau du modèle de diffusion, vous pouvez spécifier un script pour calculer le libellé (et le dossier de campagne) de la diffusion associée. Si le script calcule une diffusion qui n’existe pas encore, elle est créée à la volée.

![](assets/edit_diffusion_fil.png)

L’option **[!UICONTROL Traiter les erreurs]** affiche une transition particulière qui sera activée si une erreur est générée. Dans ce cas, le workflow ne passe pas en état d’erreur et son exécution se poursuit.

Les erreurs prises en compte sont les erreurs du système de fichiers (impossible de déplacer un fichier, impossible d&#39;accéder au répertoire, etc.).

Cette option ne traite pas les erreurs liées au paramétrage de l&#39;activité, c&#39;est-à-dire des valeurs invalides.

## Paramètres d&#39;entrée {#input-parameters}

* tableName
* schéma

Chacun des événements entrants doit spécifier une cible définie par ces paramètres.

Uniquement lorsque l&#39;action **[!UICONTROL Spécifiés par l&#39;événement entrant]** est sélectionnée.

## Paramètres de sortie {#output-parameters}

* tableName
* schéma
* recCount

Ce triplet de valeurs identifie la cible résultant de la diffusion à la volée. **[!UICONTROL tableName]** est le nom de la table qui enregistre les identifiants de la cible, **[!UICONTROL schema]** est le schéma de la population (habituellement nms:recipient) et **[!UICONTROL recCount]** est le nombre d’éléments dans la table.

La transition associée au complémentaire possède les mêmes paramètres.

## Comment configurer une diffusion au fil de l’eau

Cette section explique comment configurer une diffusion au fil de l’eau.

Une **diffusion au fil de l’eau** permet d&#39;ajouter de nouveaux destinataires à une diffusion existante, ce qui évite d&#39;avoir à créer une diffusion chaque fois qu’un nouveau destinataire est ajouté. Vous pouvez mettre à jour le contenu créatif directement dans le workflow de campagne et le modèle sera mis à jour dans le dossier Ressource du modèle de diffusion.

Une diffusion au fil de l’eau crée une diffusion et des logs de diffusion UNIQUES (broadLog) et des logs de tracking qui font référence à l&#39;ajout d&#39;une diffusion chaque fois qu&#39;elle s&#39;exécute.

![Diffusion continue](assets/delivery_continuous.jpg)

## Tutoriel vidéo {#continuous-delivery-video}

Cette vidéo montre comment configurer une diffusion en continu avec une requête incrémentale.

>[!VIDEO](https://video.tv.adobe.com/v/25039?quality=12)

D’autres vidéos pratiques sur Campaign sont disponibles [ici](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html?lang=fr){target="_blank"}.
