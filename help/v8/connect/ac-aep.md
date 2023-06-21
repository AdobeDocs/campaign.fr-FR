---
title: Utiliser Campaign et Adobe Experience Platform
description: Découvrez comment utiliser Campaign et Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 58%

---

# Utiliser Campaign et Adobe Experience Platform

La destination et les connecteurs source d’Adobe Campaign Managed Cloud Services permettent une intégration transparente entre Adobe Campaign et Adobe Experience Platform.

* Utilisation d’un Adobe Campaign Managed Cloud Services **Connexion destination** pour envoyer des segments Experience Platform à Adobe Campaign pour activation :

  Pour ce faire, configurez un nouveau Adobe Campaign Managed Cloud Services **Connexion destination** pour activer un segment/une audience et envoyer ces données à Adobe Campaign. Fournissez des détails sur l’instance Campaign à utiliser, sélectionnez les segments à activer pour la destination, puis configurez les attributs à exporter vers Campaign. [Découvrez comment créer une connexion de destination Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* Utilisation d’un Adobe Campaign Managed Cloud Services **Connexion source** pour envoyer des logs de diffusion et de tracking Adobe Campaign à Adobe Experience Platform :

  Pour ce faire, configurez un nouveau Adobe Campaign Managed Cloud Services **Connexion source** pour ingérer des événements Campaign dans Adobe Experience Platform. Fournissez des détails sur l’instance Campaign et le schéma à utiliser, sélectionnez un jeu de données où les données doivent être ingérées, puis configurez les champs à récupérer. [Découvrez comment créer une connexion source Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
