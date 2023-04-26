---
title: Utiliser Campaign et Adobe Experience Platform
description: Découvrez comment utiliser Campaign et Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 91%

---

# Utiliser Campaign et Adobe Experience Platform

La destination et les connecteurs source d’Adobe Campaign Managed Cloud Services permettent une intégration transparente entre Adobe Campaign et Adobe Experience Platform.

* Utilisez la connexion de destination **** Adobe Campaign Managed Cloud Services pour envoyer des segments Experience Platform à Adobe Campaign en vue de leur activation

   ![](assets/aep-destination.png)

* Utilisez la connexion source **** Adobe Campaign Managed Cloud Services pour envoyer les logs de diffusion et de tracking Adobe Campaign à Adobe Experience Platform

   ![](assets/aep-logs.png)

Les étapes de configuration de cette intégration dans Adobe Experience Platform sont les suivantes :

1. Configurez une nouvelle connexion de destination Adobe Campaign Managed Cloud Services pour activer un segment/une audience et envoyer ces données à Adobe Campaign.

   Fournissez des détails sur l’instance Campaign à utiliser, sélectionnez les segments à activer pour la destination, puis configurez les attributs à exporter vers Campaign.

   [Découvrez comment créer une connexion de destination Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configurez une nouvelle connexion Source Adobe Campaign Managed Cloud Services pour ingérer des événements Campaign dans Adobe Experience Platform.

   Fournissez des détails sur l’instance Campaign et le schéma à utiliser, sélectionnez un jeu de données où les données doivent être ingérées, puis configurez les champs à récupérer.

   [Découvrez comment créer une connexion source Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)
