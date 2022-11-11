---
product: campaign
title: Gestion des ressources marketing
description: Découvrez comment gérer les ressources marketing
exl-id: 4d91fb7d-f846-4644-b83d-5a6a988ae297
source-git-commit: 399c81276d29622a2161c8c90395df1a38954763
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 38%

---

# Gestion des ressources marketing{#managing-marketing-resources}

Utilisez Adobe Campaign pour gérer et tracker les ressources marketing impliquées dans le cycle de vie de la campagne. Ces ressources marketing peuvent être un livre blanc, un fichier de données, un logo ou toute autre ressource liée à une campagne.

Pour chaque ressource marketing gérée via Adobe Campaign, vous pouvez à tout moment suivre son état et son historique, et visualiser la version actuelle.

Par défaut, les ressources marketing sont stockées dans la variable **[!UICONTROL MRM > Ressources marketing]** dossier de l&#39;explorateur Campaign.

## Ajouter une ressource marketing {#adding-a-marketing-resource}

Pour ajouter une ressource marketing, procédez comme suit :

1. Accédez au **[!UICONTROL Campagnes]** et sélectionnez **[!UICONTROL Ressources marketing]**.

1. Cliquez sur le bouton **[!UICONTROL Créer]**.
   ![](assets/add-a-mkt-resource.png)
1. Faites glisser et déposez le fichier dans la fenêtre Ressource marketing pour le charger sur le serveur Campaign. Vous pouvez également utiliser la variable **[!UICONTROL Télécharger le fichier sur le serveur...]** lien.
   ![](assets/mkt-resource-creation.png)

Une fois le chargement terminé, la ressource est ajoutée à la liste des ressources disponibles.

## Gestion des ressources marketing {#manage-marketing-resources}

Une fois le téléchargement effectué, la ressource marketing est disponible pour tous les opérateurs Adobe Campaign. Il peut l’afficher, en faire une copie pour la modifier ou mettre à jour le fichier sur le serveur.

![](assets/open-a-marketing-resource.png)

Utilisez la variable **[!UICONTROL Affecté à]** Liste déroulante dans la **[!UICONTROL Modifier]** pour sélectionner l&#39;opérateur responsable de la ressource.

![](assets/assign-a-mkt-resource.png)

Vous pouvez également sélectionner les opérateurs ou groupes d&#39;opérateurs chargés de la validation et de la publication des ressources. Pour accéder à ces options, cliquez sur le bouton  **[!UICONTROL Paramètres avancés]** lien.

Ces opérateurs sont notifiés par email lors du lancement du processus de validation des ressources.

Si aucun opérateur validant n&#39;est sélectionné, la ressource **[!UICONTROL ne pourra pas]** être soumise à validation.

Utilisez la variable **[!UICONTROL Audit]** pour ajouter un lecteur de BAT et définir une date de disponibilité pour la ressource. Au-delà de cette date, elle apparaîtra avec **[!UICONTROL Tard]** statut.

>[!NOTE]
>
>L’onglet **[!UICONTROL Historique]** contient le journal des téléchargements et mises à jour de la ressource. Le bouton **[!UICONTROL Détails]** permet de visualiser la version sélectionnée.
>
>Le **[!UICONTROL Audit]** vous permet de suivre les actions réalisées sur la ressource : validations, refus de validation, commentaires associés ou publications.

### Verrouiller/déverrouiller une ressource {#locking-unlocking-a-resource}

Une fois créées, les ressources sont disponibles dans le tableau de bord des ressources marketing et les opérateurs peuvent les éditer et les modifier.

Lorsqu&#39;un opérateur commence à travailler sur une ressource, il est recommandé de la verrouiller, afin d&#39;empêcher d&#39;autres opérateurs de la modifier en même temps. La ressource est alors réservée : il reste accessible, mais ne peut pas être publié ou mis à jour sur le serveur par un autre opérateur.

Une ressource marketing ne peut être verrouillée que si elle n&#39;a pas été approuvée.

Pour verrouiller une ressource, vous devez cliquer sur le bouton **[!UICONTROL Verrouiller]** dans le tableau de bord de la ressource.

![](assets/lock-a-resource.png)


Une fois la ressource mise à jour, cliquez sur le bouton **[!UICONTROL Verrouiller]** dans le tableau de bord de la ressource pour la rendre à nouveau accessible à tous les opérateurs.

Un message spécifique vient avertir l&#39;opérateur qui souhaite y accéder :

![](assets/mkt-resource-locked.png)

Le **[!UICONTROL Tracking]** tab indique le nom de l&#39;opérateur qui a verrouillé la ressource.

![](assets/mkt-resource-audit-tab.png)


>[!NOTE]
>
>Seul l&#39;opérateur ayant verrouillé la ressource et les opérateurs ayant des droits Administrateur sont autorisés à déverrouiller une ressource verrouillée.

### Forums de discussion {#discussion-forums}

Pour chaque ressource, la variable **[!UICONTROL Forum]** permet aux participants de partager des informations.

![](assets/mkt-resource-forum.png)

En savoir plus dans la section [Forums de discussion](discussion-forums.md) .

### Processus de validation {#approval-process}

La date de disponibilité attendue est affichée dans le détail de la ressource, si celle-ci a été indiquée dans l&#39;onglet **[!UICONTROL Tracking]**. Une fois cette date atteinte, il est possible de lancer le processus de validation via le bouton **[!UICONTROL Soumettre à validation]** du tableau de bord de la ressource. La ressource passe alors dans l&#39;état **[!UICONTROL En cours de validation]**.

Pour valider une ressource, cliquez sur le bouton **[!UICONTROL Valider la ressource]** sur son tableau de bord.

![](assets/mkt-resouce-approve.png)

Les opérateurs habilités peuvent alors accepter ou refuser la validation. Cette action est à la fois possible depuis l&#39;email envoyé (en cliquant sur le lien inclus dans le message de notification ) et à partir de la console (en cliquant sur le bouton **[!UICONTROL Valider]**).

La fenêtre de validation permet de saisir un commentaire.

![](assets/mkt-resource-approval-confirmation.png)

Accédez au **[!UICONTROL Tracking]** pour vérifier les validations.

>[!NOTE]
>
>En plus de l&#39;opérateur validant désigné au niveau de chaque ressource marketing, les opérateurs ayant les droits d&#39;administration et le responsable de la ressource sont habilités à valider une ressource marketing.

### Publier une ressource {#publishing-a-resource}

Une fois validée, la ressource marketing doit être publiée. Le processus de publication doit faire l&#39;objet d&#39;une implémentation spécifique en fonction des besoins de l&#39;entreprise. Ainsi, les ressources peuvent être publiées sur un extranet ou tout autre serveur, une information spécifique peut être transmise à un prestataire externe, etc.

Pour publier une ressource, cliquez sur le bouton **[!UICONTROL Publier]** situé dans sa zone d&#39;édition dans le tableau de bord des ressources marketing.

![](assets/mkt-resource-publish.png)

Vous pouvez également automatiser la publication d&#39;une ressource via un workflow.

Publier une ressource signifie la rendre disponible afin qu&#39;elle puisse être utilisée (par exemple dans une autre tâche). La publication proprement dite varie suivant la nature de votre ressource : pour un flyer, la publication peut consister à envoyer le fichier à un imprimeur, pour une page web, la publier sur un site...

Pour qu&#39;Adobe Campaign puisse publier, vous devez créer un workflow adéquat et le lier à la ressource. Pour ce faire, ouvrez le **[!UICONTROL Paramètres avancés...]** de la ressource, puis sélectionnez le workflow de votre choix dans la **[!UICONTROL Post-traitement]** champ .

![](assets/mkt-resource-post-processing-wf.png)

Le workflow est exécuté :

* Lorsque le validant de publication cliquera sur **[!UICONTROL Publier la ressource]** (ou, si aucun validant de publication n&#39;a été défini, le responsable de la ressource).
* Si la ressource est gérée via une tâche de création de ressource marketing, elle sera exécutée lorsque la tâche est définie sur **[!UICONTROL Terminé]**, tant que la variable **[!UICONTROL Publier la ressource marketing]** est cochée dans la tâche. [En savoir plus](creating-and-managing-tasks.md#marketing-resource-creation-task))

Si un workflow n&#39;est pas lancé immédiatement (par exemple si le workflow est arrêté), l&#39;état de la ressource passe à **[!UICONTROL En attente de publication]**. Une fois le workflow démarré, l&#39;état de la ressource passe à **[!UICONTROL Publié]**. Ce statut ne prend pas en compte les erreurs possibles dans le processus de publication. Vérifiez le statut de votre workflow pour vous assurer qu&#39;il s&#39;est exécuté correctement.

## Associer une ressource à une opération {#linking-a-resource-to-a-campaign}

### Référencer une ressource marketing {#referencing-a-marketing-resource}

Les ressources marketing peuvent être associées aux opérations, à condition que cette fonctionnalité ait été sélectionnée dans la variable [modèle de campagne](../campaigns/marketing-campaign-templates.md).

Accédez au **[!UICONTROL Modifier > Documents > Ressources]** dans le tableau de bord de l&#39;opération, puis cliquez sur **[!UICONTROL Ajouter]** pour sélectionner la ressource concernée.

![](assets/link-a-mkt-resource-to-a-campaign.png)

Vous pouvez filtrer les ressources par statut, par nature ou par type, ou appliquer un filtre personnalisé.

Utilisez la variable **[!UICONTROL Détails]** pour modifier et prévisualiser la ressource.

### Ajouter une ressource marketing à une composition de diffusion {#adding-a-marketing-resource-to-a-delivery-outline}

Les ressources marketing peuvent être associées à des diffusions via les compositions.

En savoir plus sur les compositions de diffusion dans [cette section](../campaigns/marketing-campaign-deliveries.md).

Pour cela, cliquez avec le bouton droit sur une composition de diffusion et sélectionnez **Nouveau > Ressource**.

![](assets/mkt-resource-add-in-del-outline.png)

Saisissez le nom de la ressource et sélectionnez-la dans le champ **Ressource marketing** liste déroulante.

![](assets/mkt-resource-select-in-del-outline.png)


## Gestion des stocks {#stock-management}

Vous pouvez associer une ressource marketing à un ou plusieurs stocks afin de gérer l&#39;approvisionnement et, au besoin, en cas de stock insuffisant, afficher une alerte dans le tableau de bord.


Pour associer une ressource marketing à un stock, procédez comme suit :

1. Editez un stock ou créez un nouveau stock. En savoir plus sur les stocks de [cette section](../campaigns/providers--stocks-and-budgets.md#stock-management).

1. Ajoutez une ligne de stock et sélectionnez la ressource marketing correspondante.

   ![](assets/mkt-resource-in-a-stock-line.png)

   Vous pouvez éditer la ressource sélectionnée à partir du **[!UICONTROL Editer le lien]** située à droite de la ressource, une fois sélectionnée.

1. Indiquez le stock initial et le stock d&#39;alerte puis enregistrez.

Le stock est indiqué dans la ressource marketing. **Stocks** .
