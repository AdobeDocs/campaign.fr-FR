---
title: Notes de mise à jour anticipées de Campaign v8
description: Version anticipée de Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 96%

---

# Notes de mise à jour anticipées {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign .v8 Ce contenu est sujet à des modifications sans préavis jusqu’à la date de mise à jour. Les notes de mise à jour officielles sont disponibles sur cette [page](../start/release-notes.md).

## Version 8.6.1 {#release-8-6-1}

_14 février 2024_


### Nouveautés {#new-8-6-1}

* À compter de cette version, vous avez accès à la nouvelle **interface utilisateur web de Campaign**, disponible via l’environnement central Adobe Experience Cloud. Experience Cloud est la famille intégrée d’applications, de produits et de services de marketing numérique d’Adobe. Grâce à son interface intuitive, vous pouvez accéder rapidement à vos applications cloud, fonctionnalités de produit et services. Découvrez comment vous connecter à Adobe Experience Cloud et accéder à l’interface web d’Adobe Campaign [dans cette page](campaign-ui.md#ac-web-ui).

* La version 32 bits de la console cliente est désormais obsolète. À compter de la version 8.6, la console cliente sera uniquement disponible en 64 bits. La mise à niveau vers la version 64 bits de la console cliente est transparente. Pour plus d&#39;informations sur la mise à niveau de votre système d&#39;exploitation, reportez-vous à cette section [technote](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=fr){target="_blank"}.


### Améliorations générales {#improvements-8-6-1}

* Campaign v8.6 améliore le débit des **indicateurs de tracking des diffusions par e-mail**. Grâce à nos processus optimisés, le suivi de l’ingestion et le temps de calcul sont réduits, et vous pouvez vérifier beaucoup plus rapidement vos indicateurs clés de diffusion.

* Vous pouvez désormais connecter votre instance Campaign v8 à la base de données externe Azure Synapse. Cette connexion est gérée à l’aide d’un nouveau compte externe.

* Adobe Campaign v8 s’intègre désormais à **Adobe Experience Manager as a Cloud Service**, la création étant exclusivement possible via l’interface utilisateur web d’Adobe Campaign.

* Vous pouvez désormais utiliser votre **bibliothèque Adobe Experience Manager Assets** avec Experience Cloud Assets, même si le package **Intégration avec Adobe Experience Cloud** est installé sur votre instance Adobe Campaign.

* Vous ne pouvez plus créer d’opérateurs ou d’opératrices à partir de la console cliente. Vous devez désormais utiliser Admin Console. [En savoir plus](../start/gs-permissions.md).

* Plusieurs outils tiers ont été mis à jour pour optimiser la sécurité.

### Mises à jour de la délivrabilité {#deliverability-8-6-1}

* D’ici février 2024, toute société qui envoie plus de 5 000 e-mails via Google ou Yahoo! devra commencer à utiliser une technologie d’authentification appelée DMARC (Domain-based Message Authentication Reporting and Conformance). Assurez-vous que l’enregistrement DMARC est configuré pour tous les sous-domaines que vous utilisez avec Adobe Campaign. [En savoir plus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=fr){target="_blank"}

* À compter du 1er juin 2024, Google et Yahoo! exigeront que les expéditeurs et expéditrices se conforment à List-Unsubscribe en un clic. Adobe Campaign prend désormais en charge cette option. [En savoir plus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=fr#one-click-list-unsubscribe){target="_blank"}


### Correctifs {#fixes-8-6-1}

Les problèmes suivants ont été corrigés dans cette version :
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789.