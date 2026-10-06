---
product: campaign
title: Mettre à jour la liste trimestrielle à l’aide d’une requête incrémentielle
description: Dans ce cas pratique, une requête incrémentielle est utilisée pour mettre automatiquement à jour une liste de destinataires.
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: eedc796a-865f-47a8-8807-5980546b8adf
TQID: 'https://experienceleague.adobe.com/0C-z3NZX9SMcI4Zl2dxUKwf4l3welUfwGQijq3H5K6A'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 100%
---
# Mise à jour de la liste trimestrielle à l’aide d’une requête incrémentielle {#quarterly-list-update}



Dans l’exemple suivant, une [requête incrémentale](incremental-query.md) est utilisée pour mettre automatiquement à jour une liste de personnes destinataires. Ces personnes destinataires sont ciblées dans le cadre des campagnes marketing saisonnières.

Comme ces campagnes sont lancées au début de chaque saison afin de proposer des activités sportives pertinentes, ces listes sont mises à jour tous les trimestres. Cependant, une personne destinataire ne doit être ciblée ici qu’une fois tous les 9 mois par cette campagne. Vous pouvez ainsi espacer la fréquence d’éligibilité de la personne destinataire et proposer des activités selon les saisons au fil des ans.

![](assets/incremental_query_example.png)

1. Placez une activité de requête incrémentale ainsi qu&#39;une activité de mise à jour de liste dans un nouveau workflow.
1. Paramétrez l’onglet **[!UICONTROL Requête incrémentale]** de l’activité comme indiqué à la section [Création dʼune requête](query.md#creating-a-query).
1. Sélectionnez l’onglet **[!UICONTROL Planification et historique]** et indiquez un historique de 270 jours. Une personne destinataire déjà ciblée ne sera plus ciblée pendant une période de 270 jours, soit environ 9 mois.

   Cliquez ensuite sur le bouton **[!UICONTROL Changer...]**.

1. Le but étant de mettre à jour la liste avant chaque début de saison, sélectionnez le type de périodicité **[!UICONTROL Mensuel]**.
1. Dans l’écran suivant, sélectionnez Mars, Juin, Septembre et Décembre. Indiquez comme jour le 20 du mois et choisissez l’heure à laquelle lancer l’exécution du workflow.
1. Sélectionnez ensuite la période de validité de la requête. Par exemple, si vous souhaitez que cette dernière soit active en permanence, sélectionnez **[!UICONTROL Validité permanente]**.

1. Après avoir validé le paramétrage de la requête incrémentale, paramétrez l&#39;activité de mise à jour de liste comme décrit à la section [Mise à jour de liste](list-update.md).

Le workflow sera ainsi lancé automatiquement juste avant chaque début de saison. La liste sera mise à jour avec les nouvelles personnes destinataires éligibles pour recevoir les offres.
