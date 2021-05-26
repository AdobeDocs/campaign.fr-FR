---
solution: Campaign v8
product: Adobe Campaign
title: Prise en main des campagnes marketing
description: Prise en main des campagnes marketing
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
source-git-commit: 167730cc3e81ee47f02bcdbc2c39fe793a99c534
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 12%

---

# Prise en main des campagnes marketing{#gs-ac-campaigns}

Adobe Campaign propose un ensemble de solutions qui vous aident à personnaliser et à diffuser des campagnes sur l’ensemble de vos canaux en ligne et hors ligne. Vous pouvez créer, paramétrer, exécuter et analyser des campagnes marketing. Toutes les campagnes marketing peuvent être gérées à partir d’un centre de contrôle unifié. Découvrez comment parcourir et créer des campagnes marketing dans cette section.

Les campagnes comprennent des actions (diffusions) et des processus (import ou extraction de fichiers), ainsi que des ressources (documents marketing, compositions de diffusion). Elles sont utilisées dans les campagnes marketing. Les campagnes font partie d’un programme et les programmes sont inclus dans un plan de campagne.

## Orchestration de campagnes cross-canal

Adobe Campaign vous permet de concevoir et orchestrer des campagnes ciblées et personnalisées sur plusieurs canaux : email, courrier, SMS, notification push. Une seule interface vous fournit toutes les fonctions nécessaires pour planifier, orchestrer, configurer, personnaliser, automatiser, exécuter et mesurer toutes vos campagnes et communications.

### Concepts de base

Avant de commencer à implémenter des campagnes marketing, vous devez connaître les concepts suivants :

* **Campagne** marketing : une campagne centralise tous les éléments liés à une campagne marketing : diffusions, règles de ciblage, coûts, fichiers d&#39;export, documents associés, etc. Chaque opération est rattachée à un programme.

* **Programme** : un programme permet de définir des actions marketing sur une période calendaire : lancement, campagne, fidélité, etc. Chaque programme contient les opérations liées à un calendrier, qui donne une vue d&#39;ensemble.

* **Plan** : le plan marketing peut contenir plusieurs programmes. Il est rattaché à une période calendaire, est doté d&#39;un budget alloué et peut être rattaché à des documents et objectifs.

* **Workflow** de campagne : un workflow de campagne contient des activités pour créer la logique de campagne. Utilisez les workflows de campagne pour définir des audiences et créer des diffusions pour tous les canaux disponibles.

* **Campagnes** récurrentes : les opérations récurrentes sont créées à partir d&#39;un modèle spécifique qui définit le modèle de workflow à exécuter et le planning d&#39;exécution.

* **Campagnes** périodiques : une opération périodique est une opération créée automatiquement en fonction du planning d&#39;exécution de son modèle.

## Espace de travail des campagnes marketing

Adobe Campaign vous permet de créer, paramétrer, exécuter et analyser toutes les campagnes marketing depuis un centre de contrôle unifié.

:[!DNL :arrow_upper_right:] : Découvrez comment accéder aux campagnes marketing et les mettre en oeuvre dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=en#orchestrating-campaigns)


## Principales étapes de démarrage

Les étapes clés pour créer une campagne marketing cross-canal sont les suivantes :

1. **Planification et conception de programmes marketing et de campagnes**

   Définissez la hiérarchie et le planning, définissez le budget, ajoutez des ressources, sélectionnez des opérateurs.

   [!DNL :arrow_upper_right:] Découvrez comment créer un plan marketing et configurer des campagnes dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#creating-plan-and-program-hierarchy)

   Toutes les campagnes marketing sont basées sur un modèle qui stocke les principaux paramètres et fonctionnalités. Un modèle natif est fourni pour créer une opération pour laquelle aucune configuration spécifique n’a été définie. Vous pouvez créer et configurer des modèles d’opération, puis créer des opérations à partir de ces modèles.

   [!DNL :arrow_upper_right:] Découvrez comment utiliser les modèles de campagne dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] Découvrez les campagnes récurrentes et comment les configurer dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)

1. **Définition des audiences**

   Vous pouvez créer l&#39;audience dans un workflow ou sélectionner un groupe existant, tel qu&#39;une liste de destinataires, des abonnés à une newsletter, des destinataires d&#39;une diffusion précédente ou toute condition de filtrage.

   [!DNL :arrow_upper_right:] Découvrez comment définir l&#39;audience de vos messages dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#orchestrating-campaigns)

1. **Créer des diffusions**

   Sélectionnez le ou les canaux, définissez le contenu du message et démarrez les diffusions.

   [!DNL :arrow_upper_right:] Découvrez comment créer et démarrer des diffusions de campagne marketing dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=en#creating-deliveries)

   Vous pouvez associer différents documents à une opération : rapport, photo, page web, diagramme, etc.

   [!DNL :arrow_upper_right:] En savoir plus sur les documents associés dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=en#adding-documents)

1. **Configuration du processus de validation**

   Adobe Campaign permet de mettre en place des processus collaboratifs de validation des principales étapes de la campagne marketing. Pour chaque opération, vous pouvez valider la cible, le contenu et les coûts de la diffusion. Les opérateurs Adobe Campaign en charge de la validation peuvent être notifiés par email et accepter ou refuser la validation depuis la console ou via une connexion web.

   [!DNL :arrow_upper_right:] Découvrez comment configurer et gérer les validations dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)

