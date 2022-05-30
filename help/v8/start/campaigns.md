---
title: Prise en main des campagnes marketing
description: Prise en main des campagnes marketing
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
source-git-commit: fc0be5fe82ba11e54851a8f612ece0b310447cdd
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 81%

---

# Prise en main des campagnes marketing{#gs-ac-campaigns}

Adobe Campaign propose un ensemble de solutions qui vous permettent de personnaliser et diffuser des campagnes à travers l’ensemble de vos canaux en ligne et hors ligne. Vous pouvez ainsi créer, configurer, exécuter et analyser des campagnes marketing. Toutes les campagnes marketing peuvent être gérées à partir d&#39;un centre de contrôle unifié. Dans cette section, découvrez comment parcourir et créer des campagnes marketing.

Les campagnes comprennent des actions (diffusions) et des processus (import ou extraction de fichiers), ainsi que des ressources (documents marketing, compositions de diffusion). Elles sont utilisées dans les campagnes marketing. Les campagnes font partie d&#39;un programme et les programmes sont inclus dans un plan de campagne.

## Orchestration de campagnes cross-canal{#cross-channel-orchestration}

Adobe Campaign vous permet de concevoir et d’orchestrer des campagnes ciblées et personnalisées sur plusieurs canaux tels que l’e-mail, le courrier, les SMS, les notifications push, etc. Vous bénéficiez dans une seule interface de toutes les fonctions nécessaires pour planifier, orchestrer, configurer, personnaliser, automatiser, exécuter et mesurer l’ensemble des campagnes et communications.

![](assets/campaign-tab.png)

### Concepts de base{#ac-core-concepts}

Avant de démarrer l&#39;implémentation de campagnes marketing, il vous faut connaître les concepts suivants :

* **Campagne marketing** : une campagne centralise tous les éléments liés à une campagne marketing, notamment les diffusions, les règles de ciblage, les coûts, les fichiers d&#39;export, les documents connexes, etc. Chaque campagne est associée à un programme.

* **Programme** : un programme vous permet de définir des actions marketing pour une période calendaire, notamment le lancement, le démarchage, la fidélité, etc. Chaque programme contient des campagnes liées à un calendrier, ce qui fournit une vue globale.

* **Plan** : le plan marketing peut contenir plusieurs programmes. Il est lié à une période calendaire, dispose d&#39;un budget alloué et peut également être associé à des documents et objectifs.

* **Workflow d&#39;opération** : un workflow d&#39;opération contient des activités permettant de concevoir la logique de la campagne. Utilisez des workflows d&#39;opération pour définir des audiences et créer des diffusions pour tous les canaux disponibles.

* **Campagnes récurrentes** : les campagnes récurrentes sont créées à partir d&#39;un modèle spécifique qui définit le modèle de workflow à exécuter ainsi que le planning d&#39;exécution.

* **Campagnes périodiques** : une campagne périodique est une opération créée automatiquement selon le planning d&#39;exécution de son modèle.

## Espace de travail de campagne marketing{#ac-workspace}

Avec Adobe Campaign, vous pouvez créer, configurer, exécuter et analyser toutes les campagnes marketing à partir d&#39;un centre de contrôle unifié.

![](assets/calendar.png)

![](../assets/do-not-localize/book.png) Découvrez comment accéder aux campagnes marketing et comment les implémenter dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=fr#orchestrating-campaigns).{target=&quot;_blank&quot;}


## Étapes clés pour bien démarrer{#gs-ac-start}

Les étapes clés permettant de créer une campagne marketing cross-canal sont les suivantes :

1. **Planification et conception de programmes et de campagnes marketing**

   Définissez une hiérarchie, un planning et un budget, puis ajoutez des ressources et sélectionnez des opérateurs.

   ![](../assets/do-not-localize/book.png) Découvrez comment créer un plan marketing et configurer des campagnes dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=fr#creating-plan-and-program-hierarchy).{target=&quot;_blank&quot;}

   Toutes les campagnes marketing sont basées sur un modèle qui stocke les principaux paramètres et fonctionnalités. Un modèle natif est fourni pour créer une opération pour laquelle aucune configuration spécifique n&#39;a été définie. Vous pouvez créer et configurer des modèles d&#39;opération, puis créer des opérations à partir de ces modèles.

   ![](../assets/do-not-localize/book.png) Découvrez comment utiliser les modèles de campagnes dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=fr#orchestrating-campaigns).{target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png) Découvrez les opérations récurrentes et comment les configurer dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=fr#recurring-and-periodic-campaigns).{target=&quot;_blank&quot;}

1. **Définition d&#39;audiences**

   Vous pouvez créer l&#39;audience dans un workflow ou sélectionner un groupe existant, par exemple une liste de destinataires, les abonnés d&#39;une newsletter, les destinataires d&#39;une diffusion précédente ou toute autre condition de filtrage.

   ![](assets/campaign-wf.png)

   ![](../assets/do-not-localize/book.png) Découvrez comment définir l&#39;audience de vos messages dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=fr#orchestrating-campaigns).{target=&quot;_blank&quot;}

1. **Création de diffusions**

   Sélectionnez un ou plusieurs canaux, définissez le contenu du message et démarrez les diffusions.

   ![](assets/campaign-dashboard.png)

   ![](../assets/do-not-localize/book.png) Découvrez comment créer et lancer des diffusions de campagnes marketing dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=fr#creating-deliveries).{target=&quot;_blank&quot;}

   Vous pouvez associer divers documents à une opération, comme des rapports, photos, pages web, diagrammes, etc.

   ![](../assets/do-not-localize/book.png) En savoir plus sur les documents associés dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=fr#adding-documents){target=&quot;_blank&quot;}

1. **Configuration du processus de validation**

   Avec Adobe Campaign, vous pouvez mettre en place des processus collaboratifs de validation des principales étapes d’une campagne marketing. Pour chaque campagne, vous pouvez valider la cible de diffusion, le contenu et les coûts. Les opérateurs Adobe Campaign en charge de la validation peuvent être avertis par e-mail et peuvent accepter ou refuser la validation depuis la console ou via une connexion web.

   ![](../assets/do-not-localize/book.png) Découvrez comment configurer et gérer les validations dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=fr#orchestrating-campaigns).{target=&quot;_blank&quot;}


## Module complémentaire Marketing distribué{#distributed-marketing-add-on}

Adobe Campaign propose une **Marketing distribué** module complémentaire pour la mise en oeuvre de campagnes de coopération entre entités centrales (siège social, départements marketing, etc.) et les entités locales (magasins, agences régionales, etc.). Cette coopération repose sur un espace de travail partagé appelé **[!UICONTROL Liste des kits d&#39;opération]**, où des modèles d&#39;opération conçus par des entités centrales sont proposés aux entités locales.

>[!NOTE]
>
>Cette fonctionnalité est disponible à partir de Campaign v8.3. Pour vérifier votre version, reportez-vous à la section [cette section](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

[](../assets/do-not-localize/book.png) Découvrez comment configurer et utiliser les fonctionnalités de marketing distribué de Campaign dans [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/distributed-marketing/about-distributed-marketing.html){target=&quot;_blank&quot;}

## Module complémentaire Gestion de la réaction{#response-manager-add-on}

Adobe Campaign propose une **Gestion de la réaction** module complémentaire permettant de mesurer le succès et la rentabilité des campagnes marketing ou des propositions d’offres sur l’ensemble des canaux de communication : email, mobile, courrier, etc.

>[!NOTE]
>
>Cette fonctionnalité est disponible à partir de Campaign v8.3. Pour vérifier votre version, reportez-vous à la section [cette section](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

[](../assets/do-not-localize/book.png) Découvrez comment configurer et utiliser le gestionnaire de réponse de Campaign dans [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/response-manager/about-response-manager.html){target=&quot;_blank&quot;}
