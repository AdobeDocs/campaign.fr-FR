---
title: Schémas 64 bits
description: Découvrez les schémas 64 bits dans Adobe Campaign v8 pour les clients migrés vers Campaign Standard
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 18%
---
# Schémas 64 bits {#sixty-four-bit-tables}

Afin de faciliter la transition de Campaign Standard vers Campaign v8, plusieurs tables ont été modifiées de 32 à 64 bits. En effet, Campaign Standard prend en charge la pharmacocinétique 64 bits dans plusieurs schémas prêts à l’emploi, tandis que Campaign v8 prend en charge la pharmacocinétique 32 bits dans la plupart des schémas.

## Limites

* Cette modification technique s’applique uniquement aux clients effectuant la migration depuis Campaign Standard.
* L’extension de schéma et broadlog n’est pas prise en charge en 64 bits. Il restera en 32 bits.
* Les journaux liés aux diffusions envoyés aux utilisateurs techniques ne seront pas disponibles dans Campaign v8.
* Seul PostgreSQL est pris en charge.

## Schémas modifiés

Voici la liste des schémas modifiés en 64 bits et leurs attributs modifiés.

| Nom du schéma | Nom de l&#39;attribut |
|--- |--- |
| nms:broadLogRcp | identifiant |
| nms:trackingLogRcp | identifiant |
| nms:excludeLogRcp | identifiant |
| nms:broadLogVisitor | identifiant |
| nms:trackingLogVisitor | identifiant |
| nms:propositionRcp | interactionId |
| nms:propositionVisitor | interactionId |
| nms:webTrackingLog | identifiant |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | identifiant |
| nms:trackingLogAppSubRcp | identifiant |
| nms:excludeLogAppSubRcp | identifiant |
| nms:webEvent | broadLogSrc-id, broadLogRemote-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |
