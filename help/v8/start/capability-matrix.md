---
title: Campaign Classic v7 - Matrice des fonctionnalités Campaign v8
description: Comprendre les différences entre Campaign Classic v7 et Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 0c01b0a597e54ae93dd581ccba6f19b2ff13f956
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 100%

---

# [!DNL Campaign Classic]Fonctionnalités v7 -[!DNL Campaign] v8{#gs-matrix}

En tant qu’ancien utilisateur de [!DNL Campaign Classic] v7, votre manière habituelle d&#39;interagir avec [!DNL Adobe Campaign] ne devrait pas subir de perturbations importantes. La plupart des modifications apportées à v8 ne sont pas visibles, à l&#39;exception des petites modifications qui apparaissent dans l&#39;interface utilisateur et dans les étapes de configuration.

Adobe Campaign v8 est disponible en tant que **Managed Cloud Service**. La nouvelle offre combine les services les plus performants avec une surveillance proactive et des alertes rapides, en se concentrant sur trois domaines :

* **Agilité du cloud** : automatisation par Adobe, avec des déploiements cloud optimisés et normalisés pour des performances plus prévisibles, une plus grande agilité et une productivité en libre-service améliorée.
* **Expérience de service** : supervision proactive de la disponibilité, de la capacité et des performances et intervention pour prévenir les perturbations, résoudre les incidents plus rapidement et passer régulièrement en revue les services pour une amélioration continue.
* **Expertise approfondie dans Adobe Campaign** : service à haute affinité d’équipes d’ingénieurs client expertes pour répondre aux besoins fonctionnels, techniques ou de délivrabilité, réduire les risques de déploiement et améliorer la gestion du changement.

En tant qu’ancien utilisateur [!DNL Campaign Classic], veuillez noter que la plupart des fonctionnalités de [!DNL Campaign Classic] v7 sont disponibles dans [!DNL Campaign] v8, à l’exception d’un petit ensemble de fonctionnalités répertoriées dans [cette section](#gs-removed). Les prochaines versions proposeront d&#39;autres fonctionnalités. [En savoir plus dans cette section](#gs-unavailable-features)

>[!NOTE]
>
> Campaign v8 repose sur une architecture hybride. Si vous effectuez une transition à partir de Campaign Classic v7, veuillez noter que toutes les diffusions passent par le serveur de midsourcing. [En savoir plus](../architecture/architecture.md)
>
> Par conséquent, le routage interne est **impossible** dans Campaign v8 et le compte externe a été désactivé en conséquence.


## [!DNL Campaign] et [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 fonctionne avec [!DNL Snowflake]. Deux modèles de déploiement sont disponibles.

![](../assets/do-not-localize/glass.png) Pour en savoir plus sur l&#39;architecture de [!DNL Campaign] v8, consultez [cette page](../architecture/architecture.md).


## Utilisation de votre Adobe ID pour vous connecter à Campaign{#adobe-id}

Les utilisateurs de Campaign se connectent via leur Adobe ID. Le même Adobe ID est utilisé pour conserver tous vos abonnements Adobe et produits associés à un seul compte, pour toutes les solutions Adobe Experience Cloud.

![](../assets/do-not-localize/glass.png) Découvrez comment vous connecter à [!DNL Campaign] dans [cette page](connect.md).

## Analyse des données avec des cubes{#adobe-reporting}

Utilisez le module Marketing Analytics pour analyser et mesurer les données, calculer les statistiques, simplifier et optimiser la création et le calcul de rapports. Créez également des rapports et des populations cibles : une fois identifiés, ils sont stockés dans des listes qui peuvent être utilisées dans Adobe Campaign (ciblage, segmentation, etc.).

Notez que les rapports de cube Adobe Campaign sont optimisés et offrent de meilleures fonctionnalités d’échelle que Campaign Classic v7. Les anciennes limitations sur les cubes ne s’appliquent pas dans Campaign v8.

## Modification de la source de données {#change-data-source}

Campaign v8 propose une activité de workflow de ciblage supplémentaire : **[!UICONTROL Modifier la source de données]**.

L&#39;activité **[!UICONTROL Modifier la source de données]** permet de modifier la source de données d&#39;un workflow **[!UICONTROL Table de travail]** pour gérer les données de différentes sources de données telles que FDA, FFDA et base de données locale.

![](../assets/do-not-localize/glass.png) En savoir plus sur l’activité **[!UICONTROL Modifier la source de données]** dans [cette page](../config/workflows.md#change-data-source-activity).

## Fonctionnalités non disponibles{#gs-unavailable-features}

Veuillez noter que certaines fonctionnalités ne sont pas disponibles dans cette version de Campaign, telles que :

* Gestion des ressources marketing
* Modèles de déploiement hybrides/On-premise

>[!CAUTION]
>
>* À l&#39;heure actuelle, Campaign v8 est **uniquement** disponible en tant que Managed Cloud Service et ne peut pas être déployé dans des environnements on-premise ou hybrides.
>
>* La migration depuis un environnement Campaign Classic v7 existant n&#39;est pas encore disponible.
>
>* Si vous n’êtes pas sûr de votre modèle de déploiement ou si vous avez des questions, contactez votre responsable de compte Adobe.


## Fonctionnalités non prises en charge{#gs-removed}

Pour s&#39;aligner sur la nouvelle architecture et le nouveau modèle de déploiement de Campaign v8, certaines fonctionnalités historiques de Campaign Classic v7 ne sont plus prises en charge dans Campaign v8, telles que :

* Coupons
* Tracking web
* Questionnaires
* Marketing pour réseaux sociaux
* Connecteur ACS (offre principale)
* Intégration avec LDAP
* Connexion utilisateur/mot de passe

>[!NOTE]
>
>Certaines fonctionnalités non disponibles ou non prises en charge sont toujours visibles dans l’interface utilisateur.
