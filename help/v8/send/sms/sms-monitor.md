---
title: Surveiller et suivre un SMS
description: À propos de la surveillance et du suivi d’une diffusion SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 42be45db-3a90-4ad0-896d-f082afff1f8e
TQID: 'https://experienceleague.adobe.com/wETwv6lIEctnfT54WQjulzGxeCPo6lZDF-rxlwBtF4I'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 52%
---
# Surveiller et suivre un SMS

Il est important de surveiller votre diffusion par SMS, afin de vous assurer que vos campagnes marketing sont efficaces.

Voici les possibilités dont vous disposez pour savoir ce qui se passe après l’envoi de votre diffusion

## Comprendre le tableau de bord de la diffusion SMS

Le tableau de bord de la diffusion fournit de nombreuses informations sur votre SMS.

Pour accéder au tableau de bord, double-cliquez sur votre diffusion dans la liste des diffusions.

Dans l’onglet **[!UICONTROL Résumé]**, vous disposez des données principales comme le nombre de messages traités et le nombre de succès.

![Onglet Résumé du tableau de bord des diffusions SMS avec les messages à envoyer, les taux de succès et de traitement, ainsi que le statut de la diffusion](assets/sms_summary.png){zoomable="yes"}

Après l’envoi du SMS, l’onglet **[!UICONTROL SMS]**, qui concerne le contenu de la diffusion, n’est plus accessible pour une modification.

Dans l’onglet **[!UICONTROL Diffusion]**, vous disposez des informations sur les logs de diffusion. Pour chaque adresse contactée, vous pouvez voir si le SMS a été envoyé ou non.

![Liste des logs de l&#39;onglet Diffusion indiquant, pour chaque adresse contactée, si le SMS a été envoyé, avec statut et raison](assets/sms_deliverylogs.png){zoomable="yes"}

Vous pouvez voir dans l’onglet **[!UICONTROL Exclusions]** les détails sur les raisons pour lesquelles certaines adresses sont exclues de la cible.

![Onglet Diffusion Onglet Exclusions répertoriant les adresses ignorées avec la raison, telles que l&#39;adresse Placée sur la liste bloquée ou Double](assets/sms_exclusions.png){zoomable="yes"}

L’onglet **[!UICONTROL Tracking]** concerne le suivi. Ci-dessous l&#39;exemple d&#39;une URL trackée dans le contenu du SMS.

![Liste des URL de l&#39;onglet Tracking affichant une URL suivie à partir du contenu du SMS avec son libellé, son type et l&#39;URL source](assets/sms_trackinglogs.png){zoomable="yes"}

Et enfin, l’onglet **[!UICONTROL Audit]** avec tous les détails pendant le lancement de la diffusion :

![Onglet Audit Log répertoriant les messages enregistrés lors du lancement de la diffusion, avec les colonnes date et message](assets/sms_audit.png){zoomable="yes"}

## Comprendre les SMS en échec

Les raisons et les types des échecs sont les mêmes que pour les e-mails.

En savoir plus sur les [échecs de diffusion](../delivery-failures.md) et plus particulièrement sur les [quarantaines des SMS](../delivery-failures.md#sms-quarantines).
