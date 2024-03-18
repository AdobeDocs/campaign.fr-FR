---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3a63539bc6bb20fa79bdac76dd60efe7b232458b
workflow-type: ht
source-wordcount: '478'
ht-degree: 100%

---

# Dernière version{#latest-release}

Adobe Campaign fait l&#39;objet de mises à jour régulières. Cette fréquence régulière de mise à jour a pour but de vous fournir les dernières fonctionnalités et améliorations. Vous bénéficiez ainsi d&#39;un environnement sécurisé et d&#39;une expérience optimale avec notre produit. Adobe recommande vivement à toute sa clientèle d’effectuer la mise à niveau vers la dernière version. Pour en savoir plus sur les versions de Campaign et les recommandations, consultez [cette page](upgrades.md).

En tant qu’utilisateur ou utilisatrice de Managed Cloud Services, votre instance est mise à niveau par Adobe avec chaque nouvelle version. Adobe vous contactera et mettra à niveau vos environnements. La console cliente Campaign **doit être mise à niveau vers la même version** que les serveurs Campaign. Découvrez comment mettre à niveau votre console cliente [sur cette page](../start/connect.md#upgrade-ac-console).

En outre, en tant que client ou cliente, assurez-vous d’utiliser la dernière version prise en charge des systèmes répertoriés dans la [matrice de compatibilité](compatibility-matrix.md).


## Version 8.6.2 {#release-8-6-2}

_23 février 2024_

### Correctifs {#fixes-8-6-2}

Cette version corrige le problème suivant :

* Correction d’un problème de performances qui pouvait se produire sur l’instance de midsourcing (NEO-72595).

## Version 8.6.1 {#release-8-6-1}

_14 février 2024_

### Nouveautés {#new-8-6-1}

* À compter de cette version, vous avez accès à la nouvelle **interface utilisateur web de Campaign**, disponible via l’environnement central Adobe Experience Cloud. Experience Cloud est la famille intégrée d’applications, de produits et de services de marketing numérique d’Adobe. Grâce à son interface intuitive, vous pouvez accéder rapidement à vos applications cloud, fonctionnalités de produit et services. Découvrez comment vous connecter à Adobe Experience Cloud et accéder à l’interface d’Adobe Campaign Web [dans cette page](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 s’intègre désormais à **Adobe Experience Manager as a Cloud Service**, la création étant exclusivement possible via l’interface utilisateur web d’Adobe Campaign. [En savoir plus](../connect/ac-aem.md)

* Vous pouvez désormais utiliser votre **bibliothèque Adobe Experience Manager Assets** avec vos Experience Cloud Assets même si le package Intégration avec Adobe Experience Cloud est installé sur votre instance Adobe Campaign. [En savoir plus](../connect/ac-aem.md#assets-library)

### Améliorations générales {#improvements-8-6-1}

* Campaign v8.6 améliore le débit des **indicateurs de tracking des diffusions par e-mail**. Grâce à nos processus optimisés, le suivi de l’ingestion et le temps de calcul sont réduits, et vous pouvez vérifier beaucoup plus rapidement vos indicateurs clés de diffusion.


### Mises à jour de la délivrabilité {#deliverability-8-6-1}

* D’ici février 2024, toute société qui envoie plus de 5 000 e-mails via Google ou Yahoo! devra commencer à utiliser une technologie d’authentification appelée DMARC (Domain-based Message Authentication Reporting and Conformance). Assurez-vous que l’enregistrement DMARC est configuré pour tous les sous-domaines que vous utilisez avec Adobe Campaign. [En savoir plus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=fr){target="_blank"}

* À compter du 1er juin 2024, Google et Yahoo! exigeront que les expéditeurs et expéditrices se conforment à List-Unsubscribe en un clic. Adobe Campaign prend désormais en charge cette option. [En savoir plus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=fr#one-click-list-unsubscribe){target="_blank"}


### Correctifs {#fixes-8-6-1}

Les problèmes suivants ont été corrigés dans cette version :
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789.