---
title: Autorisations d’octroi et de réaffectation sur les dossiers Campaign
description: Découvrez comment accorder ou restreindre des autorisations sur des dossiers
feature: Permissions
role: User, Admin
level: Beginner
source-git-commit: 857445d7d7d8080e479bdc596fb3162c2b4a2b6b
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 90%

---

# Gestion des autorisations de dossier{#manage-folder-permissions}

## Limiter l&#39;accès à un dossier{#restrict-access-to-a-folder}

Utilisez les autorisations sur les dossiers pour organiser et contrôler l&#39;accès aux données de Campaign.

La gestion des dossiers est présentée dans la section [cette page](../audiences/folders-and-views.md).

Pour modifier les autorisations sur un dossier Campaign spécifique, procédez comme suit :

1. Cliquez avec le bouton droit sur le dossier et sélectionnez **[!UICONTROL Propriétés...]**.
1. Accédez à l&#39;onglet **[!UICONTROL Sécurité]** pour visualiser les autorisations sur ce dossier.

   ![](assets/folder-permissions.png)

* Pour **autoriser un groupe ou un opérateur**, cliquez sur le bouton **[!UICONTROL Ajouter]** et sélectionnez le groupe ou l&#39;opérateur auquel attribuer les autorisations pour ce dossier.
* Pour **interdire un groupe ou un opérateur**, cliquez sur **[!UICONTROL Supprimer]** et sélectionnez le groupe ou l&#39;opérateur pour supprimer les autorisations pour ce dossier.
* Pour **sélectionner les droits attribués à un groupe ou un opérateur**, cliquez sur le groupe ou l&#39;opérateur, sélectionnez les droits d&#39;accès que vous voulez attribuer, et décochez les autres.

## Propager les autorisations {#propagate-permissions}

Pour propager les autorisations et les droits d&#39;accès, sélectionnez l&#39;option **[!UICONTROL Propager]** dans les propriétés du dossier.

Les autorisations définies dans cette fenêtre seront alors appliquées à tous les sous-dossiers du nœud actuel. Vous pouvez toujours surcharger ces autorisations pour chacun des sous-dossiers.

>[!NOTE]
>
>Le fait de décocher l&#39;option **[!UICONTROL Propager]** pour un dossier ne la désélectionne pas pour les sous-dossiers : vous devez la désélectionner explicitement pour chacun des sous-dossiers.

## Accorder l&#39;accès à tous les opérateurs {#grant-access-to-all-operators}

Dans l&#39;onglet **[!UICONTROL Sécurité]**, sélectionnez la variable **[!UICONTROL Dossier système]** pour permettre l&#39;accès à tous les opérateurs, quelles que soient leurs autorisations.

Si cette option est désélectionnée, vous devez ajouter explicitement l&#39;opérateur (ou son groupe) dans la liste des autorisations pour qu&#39;il y ait accès.
