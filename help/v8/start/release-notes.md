---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4fe8b8eaf88f763e796dbe06ef3c1477de12bad6
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 18%

---

# Dernières versions {#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **dernières versions** de Campaign v8 (console). Pour en savoir plus sur les publications, les versions et les mises à niveau de Campaign, consultez [cette page](upgrades.md). Les autres versions sont répertoriées dans la section Versions précédentes de cette documentation.

## Version 8.9.1 {#release-8-9-1}

_27 janvier 2026_

>[!CAUTION]
>
> La mise à niveau de la console cliente est obligatoire. Découvrez comment mettre à niveau votre console cliente sur cette [page](../start/connect.md#upgrade-ac-console).

### Nouvelles fonctionnalités {#new-8-9-1}

Le **nouveau connecteur d&#39;envoi de SMS** est désormais disponible pour tous les clients (GA). Consultez la [documentation détaillée](../send/sms/sms.md).

Cette version est fournie avec un ensemble de fonctionnalités disponibles dans l’interface utilisateur web de Campaign :

* [Fonctionnalités de diffusion multilingue (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [Enrichissement du profil dans les messages transactionnels (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Adobe Experience Manager Live et copies de langue](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [Expériences de contenu - Tests AB](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [Activité de diffusion au fil de l&#39;eau](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [Gestion de la validation des campagnes](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

Reportez-vous aux notes de mise à jour de l’interface utilisateur web de Campaign [&#128279;](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=fr){target="_blank"}

### Améliorations de la sécurité {#security-8-9-1}

* Les comptes externes Snowflake prennent désormais en charge l’authentification OAuth2, fournissant des méthodes d’authentification modernes et sécurisées pour les connexions d’accès aux données fédérées. (NEO-87013)
* Correction de vulnérabilités d’accès aux fichiers de workflow en limitant les opérations aux répertoires autorisés, en empêchant l’accès non autorisé et l’exécution potentielle de code à distance. (NEO-88460)
* Placer sur la liste autorisée Ajout de contrôles d’URL FTP aux activités de code de JavaScript de workflow, limitant les connexions FTP sortantes aux adresses autorisées uniquement. (NEO-89083)

### Autres changements {#changes-8-9-1}

* Amélioration de la gestion de la mémoire de conteneur en implémentant la limitation automatique des workflows dans des conditions de mémoire élevée, avec des fonctionnalités intelligentes de redémarrage des workflows et des mécanismes de sécurisation de la mémoire pour les processus non critiques. (NEO-89041)
* Ajout de la prise en charge des fonctions de chiffrement et de déchiffrement asymétriques dans les workflows Campaign. (NEO-80257)
* Amélioration des performances de l’agent de réplication et de la résilience de la mémoire pour les chargements de données volumineux dans les déploiements FFDA. (NEO-88430)


### Correctifs {#fixes-8-9-1}

* Correction d’un problème en raison duquel la structure de la base de données ne pouvait pas être mise à jour après les modifications de sysFilter. (NEO-93306)
* Correction d’un problème en raison duquel les données du rapport dynamique étaient manquantes après la migration. (NEO-92962)
* Correction d&#39;un problème en raison duquel le statut de la diffusion ne se mettait pas à jour correctement. (NEO-92908)
* Ajout d’une solution pour la restriction Catalogue d’utilisation FDA des briques de données . (NEO-92900)
* Correction d’un problème en raison duquel l’éditeur visuel rompait la disposition HTML dans Outlook Windows Desktop. (NEO-92611)
* Correction d’un problème d’intégrité des données critique en raison duquel les clés primaires de diffusion étaient dupliquées sur l’instance Mid après la mise à niveau. (NEO-92424)
* Correction d’un problème en raison duquel les liens ne pouvaient pas être désactivés dans la boîte de dialogue Tracking et images d’une diffusion. (NEO-92381)
* Correction d’un problème en raison duquel la fonction nms.subscription.RecipientSubscribe() ne fonctionnait pas pour l’abonnement en bloc. (NEO-92308)
* Correction d’un problème en raison duquel des fragments de diffusion étaient manquants après la mise à niveau. (NEO-92278)
* Correction d&#39;un problème dans le workflow de tracking. (NEO-92239)
* Correction d’un problème où les références d’énumération temporaires étaient manquantes dans le XML de liste après la création de la liste à l’aide d’un workflow. (NEO-91158)
* Correction d’un problème en raison duquel la boîte de dialogue Publier/Dépublier de RT ne se fermait pas et ne se figeait pas. (NEO-91038)
* Correction d&#39;un problème en raison duquel les destinataires dont le statut était défini sur « Pris en compte par le fournisseur de services » n&#39;atteignaient pas Momentum. (NEO-90927)
* Correction d’un problème en raison duquel l’origine de l’(désabonnement)était manquante dans v8 pour les liens d’opt-out. (NEO-90714)
* Correction d’un problème en raison duquel l’ajout de coupons échouait dans la préparation de la diffusion. (NEO-90547)
* Correction d’un problème en raison duquel le nombre d’insertions et de rejets n’était pas reflété précisément dans l’onglet Audit. (NEO-90318)
* Correction d’un problème de sécurité qui entraînait un déni de service de l’application. (NEO-89984)
* Correction d’un problème en raison duquel le PDF téléchargé du rapport Hotclick était endommagé. (NEO-89954)
* Correction d’une erreur SSL qui se produisait après la mise à niveau, provoquant un EOF inattendu lors de la lecture des erreurs. (NEO-89108)
* Correction d’un problème en raison duquel les données ne pouvaient pas être interrogées dans le schéma de données après la mise à niveau. (NEO-88663)
* Correction d’une erreur qui se produisait lors de la concaténation d’un champ « char » dans PostgreSQL 15. (NEO-88028)
* Correction d’un problème en raison duquel l’ordre des variables du modèle de diffusion changeait lors de l’enregistrement ou de la duplication du modèle. (NEO-87845)
* Correction d’un problème en raison duquel la création d’un schéma de bibliothèque de données entraînait le blocage de l’interface web. (NEO-87816)
* Correction d’un problème en raison duquel le code segment du jeu de compléments de l’activité Déduplication ne fonctionnait pas. (NEO-87711)
* Résolution d’une demande de package d’installation sans dépendance X11. (NEO-87471)
* Correction d’un problème en raison duquel les codes segment ne pouvaient pas être utilisés dans les rapports dynamiques. (NEO-87276)
* Correction d’un problème où les workflows étaient bloqués dans l’activité Mise à jour de données . (NEO-87252)
* Correction d’un problème en raison duquel BigQuery utilisait un fuseau horaire incorrect. (NEO-86622)
* Correction d’une erreur JavaScript qui se produisait lors de l’évaluation du script « mcSynch_mcExec1/jsReplicateUrl ». (NEO-86553)
* Correction d’un problème où des événements en double apparaissaient dans la table eventHisto en raison de la méthode de calcul de l’identifiant. (NEO-86544)
* Correction d’un problème en raison duquel l’onglet Avancé ne s’affichait pas pour la notification push iOS lors de la copie. (NEO-86231)
* Correction d’un problème en raison duquel le workflow Répliquer les tables de référence échouait dans la réplication du schéma nms:delivery. (NEO-85884)
* Correction d’un problème en raison duquel les erreurs de domaine null correspondant aux adresses MXIP s’affichaient dans les journaux d’erreurs lors de l’envoi de diffusions. (NEO-85238)
* Ajout d’un moyen d’actualiser les modèles de diffusion techniques après toute modification pouvant avoir été apportée aux options. (NEO-84149)
* Correction d’une erreur dans le workflow de facturation prêt à l’emploi. (NEO-83624)
* Correction d&#39;un problème d&#39;exclusion des doublons basé uniquement sur la clé primaire des enregistrements ciblés. (NEO-82910)
* Correction d’incohérences dans les rapports de l’interface utilisateur web de Campaign où les statistiques de tracking affichaient des valeurs différentes par rapport à la console. Les rapports Indicateurs de tracking, Résumé d’envoi et Flux de clics sur les URL affichent désormais des mesures cohérentes sur les deux interfaces. (NEO-82339)
* Correction d&#39;un problème en raison duquel la date de dernière modification était modifiée même si l&#39;enregistrement ne devait pas être mis à jour dans l&#39;activité Mise à jour de données . (NEO-82002)
* Correction d’un problème en raison duquel l’ajout de nouveaux attributs dans une liste entraînait l’échec des workflows qui lisaient la liste. (NEO-80258)
* Correction d’une anomalie dans le rapport des indicateurs de tracking. (NEO-79466)