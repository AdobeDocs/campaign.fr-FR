---
title: Utilisation de Campaign et Adobe Experience Platform
description: Découvrez comment utiliser Campaign et Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Utilisation de Campaign et Adobe Experience Platform

La destination et les connecteurs source du Cloud Service géré Adobe Campaign permettent une intégration transparente entre Adobe Campaign et Adobe Experience Platform :

* Utilisation **Connecteur Adobe Campaign Managed Cloud Sources** pour envoyer des segments Experience Platform à Adobe Campaign en vue de leur activation,

   ![](assets/aep-destination.png)

* Utilisation **Connecteur Adobe Campaign Managed Cloud Destination** pour envoyer les logs de diffusion et de suivi Adobe Campaign à Adobe Experience Platform.

   ![](assets/aep-logs.png)

Les étapes de configuration de cette intégration dans Adobe Experience Platform sont les suivantes :

1. Configurez une nouvelle connexion de destination Adobe Campaign Managed Cloud Services pour activer un segment/une audience et envoyer ces données à Adobe Campaign.

   Fournissez des détails sur l’instance Campaign à utiliser, sélectionnez les segments à activer pour la destination, puis configurez les attributs à exporter vers Campaign.

   [Découvrez comment créer une connexion de destination Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configurez une nouvelle connexion source Adobe Campaign Managed Cloud Services pour ingérer des événements Campaign dans Adobe Experience Platform.

   Indiquez des détails sur l’instance Campaign et le schéma à utiliser, sélectionnez un jeu de données où les données doivent être ingérées, puis configurez les champs à récupérer.

   [Découvrez comment créer une connexion source Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)