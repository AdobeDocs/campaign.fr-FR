---
title: Versions et mises à niveau de Campaign
description: En savoir plus sur les versions et mises à niveau de Campaign
feature: Release Notes
role: User
level: Beginner
source-git-commit: 43994eb29af2b85272de0ce4dc34cc66aba2e04a
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 14%

---

# Versions et mises à niveau {#upgrades}

## Versions de campagne {#versions}

Adobe Campaign publie régulièrement des versions de produit qui améliorent les performances, la sécurité, la logique et la convivialité de votre infrastructure Campaign.

Ces mises à niveau peuvent être :

* **Mises à niveau majeures**, d’une version majeure à une autre, par exemple de v7 à v8. Ces mises à niveau apportent de nouvelles fonctionnalités, des améliorations, des mises à jour de compatibilité et de sécurité, ainsi que des correctifs.
* **Mises à niveau mineures**, d’une version mineure à une autre, par exemple de v8.5 à v8.6. Ces mises à niveau apportent des améliorations, des mises à jour de compatibilité et de sécurité, ainsi que des correctifs.
* **Mises à niveau des correctifs**, d’une version de correctif à une autre, par exemple de v8.5.1 à v8.5.2. Ces mises à niveau apportent des mises à jour et des correctifs de sécurité.

Des informations détaillées sur chaque nouvelle version sont disponibles dans la section [Notes de mise à jour](release-notes.md).

Pour garantir une configuration stable, Adobe recommande d’installer **la même version** sur tous vos serveurs Campaign. En outre, sauf mention contraire dans la section [Notes de mise à jour](release-notes.md), la console cliente doit être activée. **la même version** comme instance de serveur. Découvrez comment mettre à niveau votre console cliente [dans cette page](../start/connect.md#upgrade-ac-console).

En tant que client Campaign Managed Services, lorsqu’une nouvelle version de Campaign est disponible, votre infrastructure est mise à niveau par Adobe sans autre action.

Notez qu’en tant que client, vous devez vous assurer d’utiliser les dernières versions prises en charge des systèmes répertoriés dans la variable [Matrice de compatibilité](compatibility-matrix.md).


## Forum aux questions {#upgrades-faq}

### Comment vérifier ma version de Campaign ? {#version}

Pour vérifier la version de Campaign, accédez au **Aide > À propos...** à partir de la console cliente.

![](assets/ac-version.png)

Vous accédez aux informations suivantes :

* La variable **version** numéro de la console cliente et du serveur applicatif. Dans l’exemple ci-dessus, la version est 8.1.5 pour la console cliente et le serveur d’applications.
* Le numéro SHA, entre parenthèses.
* Un lien pour contacter l&#39;assistance clientèle d&#39;Adobe.
* Des liens vers la Politique de confidentialité, les Conditions d&#39;utilisation et la Politique relative aux cookies d&#39;Adobe.

### Comment puis-je être informé de la sortie d&#39;une nouvelle version ? {#upgrades-0}

Les nouvelles versions et les modifications qu’elles apportent sont répertoriées dans la [Notes de mise à jour](release-notes.md). Une fois une nouvelle version disponible, Adobe vous contactera et mettra à niveau vos environnements.

Pour être informé des nouvelles versions des solutions Experience Cloud, abonnez-vous au [Mise à jour produit prioritaire des Adobes](https://www.adobe.com/fr/subscription/priority-product-update.html){target="_blank"}.

Vous pouvez également [Communauté Campaign](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?style=all&amp;sort=date&amp;order=desc&amp;filters=adobe-campaign-classic-community&amp;topic=Campaign+v8){target="_blank"} pour être informé des mises à jour de la version.


### Pourquoi mon entreprise a-t-elle besoin de cette mise à niveau ? {#upgrades-1}

La mise à niveau de votre infrastructure vers la dernière version garantit la sécurité de votre compte contre les vulnérabilités et l’utilisation de technologies de performances mises à jour.

En règle générale, la mise à niveau vers la dernière version offre les avantages suivants :

* Sécurité améliorée

  La sécurité nécessite une attention constante et une maintenance proactive. Les risques de sécurité sont omniprésents et ne peuvent pas être ignorés : chaque mise à niveau de Campaign améliore la sécurité. Ces mises à niveau doivent être appliquées à toutes vos instances Campaign, ainsi qu&#39;à la console cliente. Une combinaison de technologies permet à Adobe Campaign de travailler ensemble pour offrir une valeur ajoutée. Toutes ces technologies doivent-elles être mises à jour ?

* Prise en charge améliorée

  La plupart des problèmes critiques sont en fait résolus grâce aux mises à niveau et peuvent être évités. Des mises à niveau régulières permettent de réduire les défis rencontrés et d’accroître l’efficacité en éliminant ces défis. Le nombre d’interventions de l’assistance clientèle est réduit, ce qui entraîne des résolutions plus rapides. Il est ainsi possible d’accorder davantage d’attention aux problèmes non liés aux mises à niveau.


* Maintenance et stabilité améliorées

  Au fil du temps, l’équipe Adobe Campaign identifie les moyens d’améliorer la stabilité et les performances du produit, ainsi que de résoudre les problèmes connus. La mise à niveau met à jour votre instance avec ces améliorations et élimine les défis courants auxquels sont confrontées les organisations qui connaissent une croissance rapide et/ou une complexité au sein de leurs instances Campaign. Les améliorations apportées à la pile technologique qui alimente Campaign se répercutent au sein des équipes marketing et informatiques de votre entreprise.


### Quels sont la procédure et le calendrier de cette mise à niveau ? {#upgrades-2}

En tant que client v8, si votre compte a été identifié comme devant être mis à niveau vers une nouvelle version, Adobe vous en informe directement.

L’équipe Adobe est là pour diriger et guider votre organisation tout au long de ce parcours. Une équipe constituée de représentants et représentantes de l’assistance clientèle, de responsables produit, d’ingénieurs et ingénieures, de spécialistes des opérations techniques et de consultants et consultantes produit est là pour vous accompagner et assurer le bon déroulement de l’expérience.





