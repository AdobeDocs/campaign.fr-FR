---
title: Utiliser Campaign et Adobe Experience Platform
description: Découvrez comment utiliser Campaign et Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: d9a91fddbdcfae0f59fe780f8b6962238b89c886
workflow-type: ht
source-wordcount: '558'
ht-degree: 100%

---

# Utiliser Campaign et Adobe Experience Platform

La destination et les connecteurs source d’Adobe Campaign Managed Cloud Services permettent une intégration transparente entre Adobe Campaign et Adobe Experience Platform. Avec cette intégration, vous pouvez effectuer les actions suivantes :

* Envoyer des audiences Adobe Experience Platform vers Adobe Campaign, puis renvoyer les logs de tracking et de diffusion vers Adobe Experience Platform à des fins d’analyse.
* Importer des attributs de profil Adobe Experience Platform dans Adobe Campaign et mettre en place un processus de synchronisation afin de les mettre à jour régulièrement.

## Envoyer des audiences Adobe Experience Platform vers Campaign.{#audiences}

Les principales étapes pour envoyer des audiences Adobe Experience Platform vers Adobe Campaign et renvoyer les logs de diffusion et de tracking sont les suivantes :

* Utilisez une **connexion de destination** Adobe Campaign Managed Cloud Services pour envoyer des segments Experience Platform vers Adobe Campaign :

   1. Accédez au catalogue des destinations Adobe Experience Platform et créez une nouvelle connexion **[!UICONTROL Adobe Campaign Managed Cloud Services]**.
   1. Fournissez des détails sur l’instance de Campaign à utiliser et sélectionnez **[!UICONTROL Synchronisation de l’audience]** comme type de synchronisation.

      ![](assets/aep-audience-sync.png){width="800" align="center"}

   1. Sélectionnez les segments à envoyer vers Adobe Campaign.
   1. Configurez les attributs que vous souhaitez exporter dans l’audience.
   1. Une fois le flux configuré, les audiences sélectionnées seront disponibles pour activation dans Adobe Campaign.

      ![](assets/aep-destination.png){width="800" align="center"}

  Vous trouverez des informations détaillées sur la configuration de la destination dans la [documentation sur la connexion Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en){target="_blank"}.

* Utilisez une **connexion source** Adobe Campaign Managed Cloud Services pour envoyer les logs de diffusion et de tracking Adobe Campaign à Adobe Experience Platform :

  Pour ce faire, configurez une nouvelle **connexion source** Adobe Campaign Managed Cloud Services pour ingérer des événements Campaign dans Adobe Experience Platform. Fournissez des détails sur l’instance Campaign et le schéma à utiliser, sélectionnez un jeu de données où les données doivent être ingérées, puis configurez les champs à récupérer. [Découvrez comment créer une connexion source Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}

## Synchroniser des attributs de profil entre Adobe Experience Platform et Adobe Campaign {#profile}

En connectant Adobe Campaign à Adobe Experience Platform, vous pouvez importer des attributs de profil supplémentaires liés à un profil sur Adobe Experience Platform et mettre en place un processus de synchronisation afin de les mettre à jour dans la base de données Adobe Campaign.

Supposons, par exemple, que vous capturiez des valeurs d&#39;opt-in et d&#39;opt-out dans Adobe Experience Platform. Avec cette connexion, vous pouvez importer ces valeurs dans Adobe Campaign et mettre en place un processus de synchronisation afin de les mettre à jour régulièrement.

>[!NOTE]
>
>La synchronisation des attributs de profil est disponible pour les profils déjà présents dans la base de données Adobe Campaign.

Les principales étapes de synchronisation des attributs de profil Adobe Experience Platform avec Adobe Campaign sont les suivantes :

1. Accédez au catalogue des destinations Adobe Experience Platform et créez une nouvelle connexion **[!UICONTROL Adobe Campaign Managed Cloud Services]**.
1. Fournissez des détails sur l’instance de Campaign à utiliser et sélectionnez **[!UICONTROL Synchronisation des profils (mise à jour uniquement)]** comme type de synchronisation.

   ![](assets/aep-profile-sync.png){width="800" align="center"}

1. Sélectionnez les segments ciblant les profils à mettre à jour dans la base de données Adobe Campaign.
1. Configurez les attributs de profil que vous souhaitez mettre à jour dans Adobe Campaign.
1. Une fois le flux configuré, les attributs de profil sélectionnés seront synchronisés avec Adobe Campaign et mis à jour pour tous les profils ciblés par les segments configurés dans la destination.

Vous trouverez des informations détaillées sur la configuration de la destination dans la [documentation sur la connexion Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en){target="_blank"}.