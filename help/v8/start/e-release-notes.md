---
title: Notes de mise à jour anticipées de Campaign v8
description: Version anticipée de Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---

# Notes de mise à jour anticipées {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign .v8 Ce contenu est sujet à des modifications sans préavis jusqu’à la date de mise à jour. Les notes de mise à jour officielles sont disponibles sur cette [page](../start/release-notes.md).

## Version 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> La mise à niveau de la console client est obligatoire. Découvrez comment mettre à niveau votre console client sur cette [page](../start/connect.md#download-ac-console).

_7 octobre 2022_

**Améliorations**

* Correction d’un problème qui affectait les mises à jour du statut du journal de diffusion sur l’instance MID, lorsque l’option FeatureFlag_GZIP_Compression était activée. (NEO-49183)
* Le workflow technique **Nettoyage de la base de données** gère désormais également les schémas d’évaluation personnalisés. (NEO-48974)
* Correction d’un problème en raison duquel les diffusions pouvaient garder le statut **En attente** même si la date de contact avait été atteinte. (NEO-48079, NEO-48251)
* Stabilité améliorée lors de la gestion des chaînes XML non valides lors des appels SOAP. (NEO-48027)
* Correction d’une erreur qui ralentissait l’analyse de la diffusion, lors de l’étape d&#39;exclusion des destinataires placés sur la liste bloquée, lors du ciblage d’un grand nombre de destinataires. (NEO-48019)
* Afin de prévenir tout problème de lenteur lors de l’envoi de BAT aux adresses de contrôle, toutes les réplications consécutives des membres des adresses de contrôle sont désormais regroupées dans une seule demande de réplication. (NEO-44844)
* Correction d’un problème qui entraînait des problèmes de personnalisation lors de l’envoi de SMS à l’aide d’un mode de diffusion externe. (NEO-46415)
* Correction d’un problème qui affichait un message d’erreur lors d’une tentative de prévisualisation d’une diffusion dans un événement archivé de Message Center. (NEO-43620)
* Correction d’un problème dans les workflows en raison duquel des fichiers sur le serveur ne pouvaient pas être mis à jour lors de l’utilisation de l’activité **Chargement de données (fichier)**. Le processus s’est arrêté à 100 % mais n’a jamais pris fin. (NEO-47269)
* Correction d’un problème qui entraînait la création de DeliveryParts superflus lorsque la diffusion utilisait les modes Calendrier et Partage. (NEO-48634)
* Correction d’un problème de performances lors de l’utilisation de vagues basées sur le calendrier. (NEO-48451)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur dans l’écran de la liste de diffusion après la création d’un nouveau mapping de ciblage sur un schéma personnalisé. (NEO-49237)
* Correction d’une erreur qui pouvait se produire si une diffusion atteignait une taille précise pendant le processus MTA. (NEO-46097)
* Correction d’un problème en raison duquel les logs de tracking ne pouvaient pas renvoyer de données liées au navigateur du destinataire. (NEO-46612)
* Correction d’un problème lors du postupgrade sur les environnements japonais. (NEO-46640)
* Correction d’un problème qui se produisait lors de l’utilisation de l’activité **Requête** et du filtrage d’un tableau. Lorsqu’un nom de colonne contenait les mots « Mise à jour », une erreur de compilation se produisait avec un identifiant non valide et le message suivant : « nombre de lignes mises à jour ». (NEO-46485)
* Correction d’un problème en raison duquel le workflow technique (ffdaReplicateStagingData) **[!UICONTROL Répliquer les données d’évaluation]** ne pouvait pas s’arrêter même si une erreur s’était produite lors de son exécution. (NEO-46280)
* Correction d’un problème qui entraînait une perte de données si le workflow d’évaluation était en erreur et que la période de conservation était complètement dépassée. (NEO-48975)
* Correction d’un problème en raison duquel, lors de l’injection de données dans la base de données cloud Snowflake avec une activité de **requête** de Campaign ainsi qu’une activité **Modifier la source de données**, le processus échouait si une barre oblique inverse était présente dans les données. La chaîne source n’a pas été placée dans une séquence d’échappement et les données n’ont pas été traitées correctement sur Snowflake. (NEO-45549)
