---
title: Notes de mise à jour initiales de Campaign v8
description: Version de début de Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---

# Notes de mise à jour initiales {#e-new-release}

Cette page décrit les améliorations et les correctifs inclus dans la prochaine version de Campaign v8. Ce contenu est sujet à des modifications sans préavis jusqu’à la date de publication. Les notes de mise à jour officielles sont disponibles dans cette [page](../start/release-notes.md).

## Version 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> La mise à niveau de la console cliente est obligatoire. Découvrez comment mettre à niveau votre console cliente dans cette [page](../start/connect.md#download-ac-console).

_7 octobre 2022_

**Améliorations**

* Correction d’un problème qui affectait les mises à jour de l’état du log de diffusion sur l’instance MID, lorsque l’option FeatureFlag_GZIP_Compression était activée. (NEO-49183)
* Le **Nettoyage de la base** Le workflow technique gère désormais également les schémas d’évaluation personnalisés. (NEO-48974)
* Correction d’un problème en raison duquel les diffusions pouvaient rester dans **En attente** même si la date de contact a été atteinte. (NEO-48079, NEO-48251)
* Stabilité améliorée lors de la gestion des chaînes XML non valides lors des appels SOAP. (NEO-48027)
* Correction d&#39;une erreur qui ralentissait l&#39;analyse de la diffusion, lors de l&#39;étape d&#39;exclusion des destinataires placés sur la liste bloquée, lors du ciblage d&#39;un grand nombre de destinataires. (NEO-48019)
* Afin d&#39;éviter la lenteur lors de l&#39;envoi du BAT aux adresses de contrôle, toutes les réplications consécutives des membres des adresses de contrôle sont désormais regroupées dans une seule demande de réplication. (NEO-44844)
* Correction d’un problème qui entraînait des problèmes de personnalisation lors de l’envoi de SMS à l’aide d’un mode de diffusion externe. (NEO-46415)
* Correction d&#39;une erreur qui affichait une erreur lors de la tentative de prévisualisation d&#39;une diffusion dans un événement archivé de Message Center. (NEO-43620)
* Correction d’un problème dans les workflows qui empêchait la mise à jour des fichiers sur le serveur lors de l’utilisation de la fonction **Chargement (fichier)** activité. Le processus s&#39;est arrêté à 100% mais n&#39;a jamais pris fin. (NEO-47269)
* Correction d’un problème qui entraînait la création de DeliveryParts superflus lorsque la diffusion utilisait les modes Calendrier et Partage. (NEO-48634)
* Correction d’un problème de performances lors de l’utilisation de vagues calendaires. (NEO-48451)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur dans l’écran de la liste de diffusion après la création d’un nouveau mapping de ciblage sur un schéma personnalisé. (NEO-49237)
* Correction d’un problème qui se produisait lorsqu’une diffusion atteignait une taille spécifique pendant le processus MTA. (NEO-46097)
* Correction d’un problème qui empêchait les logs de tracking de renvoyer des données liées au navigateur du destinataire. (NEO-46612)
* Correction d’un problème lors du postupgrade dans les environnements japonais. (NEO-46640)
* Correction d’un problème lors de l’utilisation de la variable **Requête** activité et filtrage d’un tableau. Lorsqu&#39;un nom de colonne contenait le mot &quot;Mettre à jour&quot;, une erreur de compilation se produisait avec un identifiant non valide et le message suivant : &quot;nombre de lignes mis à jour&quot;. (NEO-46485)
* Correction d’un problème qui empêchait la variable **[!UICONTROL Réplication des données d’évaluation]** Workflow technique (ffdaReplicateStagingData) de l’arrêt même lorsqu’une erreur s’est produite lors de son exécution. (NEO-46280)
* Correction d’un problème qui entraînait une perte de données si le workflow d’évaluation était en erreur et que la période de conservation était complètement dépassée. (NEO-48975)
* Correction d’un problème lors de l’injection de données dans la base de données cloud Snowflake avec une campagne. **Requête** activité et une **Modifier la source de données** activité : le processus échouait lorsqu’une barre oblique inverse était présente dans les données. La chaîne source n’a pas été placée dans une séquence d’échappement et les données n’ont pas été traitées correctement sur Snowflake. (NEO-45549)
