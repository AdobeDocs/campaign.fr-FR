---
title: Accorder et restreindre des autorisations sur les dossiers Campaign
description: Découvrez comment accorder ou restreindre les autorisations sur des dossiers
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: 0513b9f65e9431f5207b384a0e2d8c5aeb8e209f
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 100%

---

# Gérer les autorisations pour les dossiers{#manage-folder-permissions}

## Limiter l&#39;accès à un dossier{#restrict-access-to-a-folder}

Utilisez les autorisations sur les dossiers pour organiser et contrôler l’accès aux données de Campaign.

La gestion des dossiers est présentée sur [cette page](../audiences/folders-and-views.md).

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
