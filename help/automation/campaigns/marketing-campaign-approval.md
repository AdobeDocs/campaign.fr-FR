---
product: campaign
title: Configuration et gestion du processus de validation
description: Découvrez comment gérer les validations des campagnes marketing
feature: Approvals, Campaigns
exl-id: 03be5058-436e-4de9-99a7-91d799aa17f6
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '2435'
ht-degree: 55%

---

# Configuration et gestion du processus de validation {#approval-marketing-campaigns}

Les méthodes et les personnes impliquées dans la création et l’approbation des campagnes marketing sont spécifiques à chaque organisation. Le processus d’approbation de campagne implique la coordination de plusieurs parties prenantes : marketeurs numériques, responsables de diffusion, gestionnaires de contenu et propriétaires externes tels que partenaires ou fournisseurs.

Avec Adobe Campaign, vous pouvez configurer un flux de validation pour vos campagnes et notifier les opérateurs lorsqu&#39;une action est requise. Vous pouvez définir les validations pour chaque étape d&#39;une diffusion : ciblage, contenu, budget, extraction et envoi de BAT. Au fur et à mesure que vos diffusions de campagne passent par les différentes étapes de validation, Adobe Campaign compile un historique des modifications et des validations, y compris les commentaires, commentaires, demandes de modification et commentaires.

Des messages de notification sont envoyés aux opérateurs Adobe Campaign désignés comme validants afin de les avertir d&#39;une demande de validation.


Les opérateurs peuvent valider de plusieurs manières :

* À partir du message de notification. Le lien contenu dans l&#39;email permet à l&#39;opérateur d&#39;accéder à Campaign via un navigateur web. Après la connexion, le validant peut choisir de valider ou non le contenu.
   ![](assets/approval-content-email.png)

* Depuis le tableau de bord de l&#39;opération.
   ![](assets/approval-from-dashboard.png)

* Depuis le tableau de bord de la diffusion.
   ![](assets/approval-from-delivery-dashboard.png)

Les opérateurs peuvent accéder à l&#39;opération et à la diffusion depuis la fenêtre de validation. Ils peuvent également saisir un commentaire.

![](assets/approval-target-confirm.png)

Une fois la validation effectuée par un opérateur, les informations sont affichées dans les tableaux de bord de l&#39;opération et de la diffusion, ainsi que dans les logs.

![](assets/approvals-from-delivery.png)

Les informations sont également disponibles dans les logs de validation de la diffusion, ainsi que dans le journal de validation de la campagne. Ces logs sont accessibles à partir du **[!UICONTROL Modifier > Suivi > Approbations]** onglets.

![](assets/approval-logs.png)


## Activer les validations{#enable-approvals}

Les notifications de validation sont envoyées aux opérateurs concernés par chaque processus pour lequel la validation a été activée.

Elles peuvent être activées au niveau du modèle d&#39;opération, au niveau de chaque opération ou au niveau d&#39;une diffusion.

Toutes les tâches qui doivent faire l&#39;objet d&#39;une validation sont sélectionnées dans le modèle de l&#39;opération, à partir du  **[!UICONTROL Propriétés]** > **[!UICONTROL Paramètres avancés de l&#39;opération...]** > **[!UICONTROL Approbations]** . Les réviseurs ou groupes de réviseurs sont sélectionnés dans cet onglet. Ils reçoivent des notifications, sauf si cette option n’est pas activée. [En savoir plus](#approving-processes).

Ces paramètres peuvent être remplacés pour chaque opération créée à partir de ce modèle, et unitairement pour chaque diffusion. Parcourez les **[!UICONTROL Propriétés]** du bouton de la diffusion, puis du bouton **[!UICONTROL Approbations]** .

Dans l&#39;exemple ci-dessous, le contenu de cette diffusion courrier ne fera l&#39;objet d&#39;aucune validation :

![](assets/approval-not-enabled.png)


>[!CAUTION]
>
>Vérifiez que les validants disposent des **autorisations appropriées** pour la validation et que leur zone de sécurité est correctement définie. [En savoir plus](#selecting-reviewers).

Le processus de validation des diffusions est présenté dans la section [cette section](#review-and-approve-deliveries).

## Sélection des validants {#select-reviewers}

Pour chaque type de validation, les opérateurs ou groupes d’opérateurs chargés de la validation sont sélectionnés dans la liste déroulante de la diffusion. Vous pouvez ajouter d’autres opérateurs à l’aide du lien **[!UICONTROL Modifier...]**. Cette fenêtre vous permet également de modifier la date limite de validation. Par défaut, les opérateurs validants disposent de trois jours à partir de la date de soumission pour valider un processus. Pour ajouter un rappel automatique, utilisez le **[!UICONTROL Ajouter un rappel]** lien.

![](assets/add-reviewers.png)

Si aucun opérateur validant n&#39;est spécifié, le propriétaire de l&#39;opération est responsable des validations et reçoit les notifications. Le propriétaire de l’opération est spécifié dans la variable **[!UICONTROL Modifier > Propriétés]** de l&#39;opération :

![](assets/campaign-owner.png)

Tous les autres opérateurs Adobe Campaign avec **[!UICONTROL Administrateur]** les droits peuvent également approuver les tâches, mais ils ne reçoivent pas de notifications.

>[!NOTE]
>
>Par défaut, le propriétaire de l&#39;opération ne peut pas effectuer de validation ni démarrer les diffusions si des opérateurs validants ont été définis. En tant qu&#39;administrateur Adobe Campaign, vous pouvez modifier ce comportement et permettre aux propriétaires de l&#39;opération de valider/démarrer des diffusions en créant la variable **NmsCampaign_Activate_OwnerConfirmation** option, définie sur **1**.


Si une liste de validants est définie, un traitement est validé lorsqu&#39;un validant l&#39;a validé. Le lien de validation n&#39;est alors plus disponible dans les tableaux de bord de l&#39;opération et de la diffusion. Lorsque l’envoi de notifications est activé et qu’un autre validant clique sur le lien de validation du message de notification, il est alors averti qu’un autre opérateur a déjà validé le traitement.

![](assets/delivery-target-already-approved.png)


## Révision et validation des diffusions {#review-and-approve-deliveries}

Pour chaque opération, vous pouvez valider la cible de la diffusion, [contenu de diffusion](#approving-content) et les coûts. Les opérateurs Adobe Campaign en charge de la validation peuvent être avertis par e-mail et peuvent accepter ou refuser la validation depuis la console ou via une connexion web. [En savoir plus](#approving-processes).

Pour les diffusions courrier, les opérateurs Adobe Campaign peuvent visualiser le fichier d&#39;extraction avant l&#39;envoi au routeur et, au besoin, modifier le format et relancer l&#39;extraction. [En savoir plus](#approve-an-extraction-file).

Une fois ces phases de validation achevées, la diffusion peut être lancée. [En savoir plus](marketing-campaign-deliveries.md#starting-a-delivery).

>[!NOTE]
>
>Les traitements qui nécessitent une validation sont sélectionnés dans le modèle de l&#39;opération. [En savoir plus](marketing-campaign-templates.md).

### Étapes de validation d’une diffusion {#approving-processes}

Les étapes qui doivent être validées apparaissent dans le tableau de bord de l&#39;opération (à partir de la console ou de l&#39;interface web). Elles apparaissent également dans la table de tracking des diffusions et dans le tableau de bord des diffusions.

![](assets/delivery-approval-actions.png)

Pour chaque diffusion de l&#39;opération, il est possible de valider les traitements suivants :

* **Valider le ciblage, le contenu, le budget**

   Lorsque la variable **[!UICONTROL Activer la validation de la cible]**, **[!UICONTROL Activer la validation du contenu]** ou **[!UICONTROL Activer la validation du budget]** les options sont sélectionnées dans la fenêtre de paramétrage de la validation des traitements, les liens correspondants sont affichés dans les tableaux de bord de l&#39;opération et de la diffusion.

   ![](assets/template-activate-6.png)

   >[!NOTE]
   >
   >La validation du budget n&#39;est disponible que si la validation de la cible est activée dans la fenêtre de paramétrage de la validation. Le lien de validation du budget ne s&#39;affiche qu&#39;une fois la cible analysée.

   Lorsque les options **[!UICONTROL Assigner l&#39;édition du contenu]** ou **[!UICONTROL Validation externe du contenu]** sont sélectionnées dans la fenêtre de paramétrage de la validation des traitements, le tableau de bord propose respectivement les liens **[!UICONTROL Contenu disponible]** et **[!UICONTROL Validation externe du contenu]**.

   La validation du contenu permet d&#39;accéder aux BAT envoyés.

* **Valider l&#39;extraction (diffusion courrier)**

   Lorsque l&#39;option **[!UICONTROL Activer la validation de l&#39;extraction]** est sélectionnée dans la fenêtre de paramétrage de la validation des traitements, le fichier extrait doit être validé avant que le routeur puisse être notifié.

   Le **[!UICONTROL Approuver le fichier]** est disponible dans les tableaux de bord des opérations et des diffusions.

   ![](assets/approve-file-preview.png)

   Vous pouvez prévisualiser le fichier de sortie avant validation. L’aperçu du fichier d’extraction affiche uniquement un exemple de données. Le fichier entier n’est pas chargé.

* **Valider les diffusions associées**

   Le **[!UICONTROL Activer la validation individuelle de chaque diffusion associée]** est utilisée pour une diffusion Principale associée à des diffusions secondaires. Par défaut, cette option n&#39;est pas sélectionnée afin qu&#39;une validation globale de la diffusion principale puisse être effectuée. Si cette option est sélectionnée, chaque diffusion doit être validée unitairement.

   ![](assets/enable-ind-approval.png)


>[!NOTE]
>
>Dans un workflow de ciblage, si une erreur liée à un problème de configuration se produit lors de la préparation du message, la variable **[!UICONTROL Redémarrer la préparation des messages]** s’affiche sur le tableau de bord. Corrigez l&#39;erreur et utilisez ce lien pour relancer la préparation des messages tout en contournant l&#39;étape de ciblage.


### Validation d’un contenu {#approve-content}

>[!CAUTION]
>
>Pour valider un contenu, un cycle de BAT est obligatoire. Les BAT vous permettent de valider l’affichage des informations, les données de personnalisation et de vérifier que les liens fonctionnent.
>
>Les fonctionnalités de validation du contenu décrites ci-dessous se rapportent à la diffusion du BAT.

Il est possible de configurer un cycle de validation du contenu. Pour ce faire, sélectionnez l’option **[!UICONTROL Activer la validation du contenu]** dans la fenêtre des paramètres de validation. Les étapes principales du processus de validation de contenu sont les suivantes :

1. Après la création d&#39;une nouvelle diffusion, le responsable de l&#39;opération clique sur le lien **[!UICONTROL Soumettre le contenu]**, dans le tableau de bord de l&#39;opération, pour lancer le cycle de validation du contenu.

   >[!NOTE]
   >
   >Si vous avez sélectionné, dans la fenêtre de paramétrage de la validation des traitements, l&#39;option **[!UICONTROL Activer l&#39;envoi des BAT]** (pour une diffusion email) ou **[!UICONTROL Activer l&#39;envoi et la validation des BAT]** (pour une diffusion courrier), l&#39;envoi des BAT se fait automatiquement.

1. Un email de notification est envoyé au responsable du contenu. Celui-ci choisit alors de valider ou non le contenu :

   * via l&#39;email de notification : l&#39;email de notification contient un lien vers les BAT déjà envoyés, et éventuellement vers un rendu du message pour les différents webmails si la variable **Délivrabilité** est activé pour cette instance.

   * depuis la console ou l&#39;interface web, le tracking des diffusions, le tableau de bord des diffusions ou le tableau de bord de l&#39;opération. Dans le tableau de bord de l&#39;opération, vous pouvez visualiser la liste des BAT envoyés, en cliquant sur le lien **[!UICONTROL Inbox Rendering...]**. Vous pouvez consulter leur contenu en cliquant sur l&#39;icône **[!UICONTROL Détails]** située à droite de la liste.

1. Un email de notification est envoyé au responsable de la campagne pour l’informer de la validation ou de la non-validation du contenu. A tout moment, le responsable de l&#39;opération peut relancer le cycle de validation du contenu. Pour cela, cliquez sur le lien situé sur la ligne **[!UICONTROL Etat du contenu]**, dans le tableau de bord de l&#39;opération (au niveau de la diffusion), puis cliquez sur **[!UICONTROL Réinitialiser la validation du contenu pour la soumettre à nouveau.]**

#### Assigner l&#39;édition du contenu {#assign-content-editing}

Cette option permet de définir un responsable de l&#39;édition du contenu, par exemple un webmaster. Lorsque l&#39;option **[!UICONTROL Assigner l&#39;édition du contenu]** est sélectionnée dans la fenêtre de paramétrage de la validation des traitements, plusieurs étapes de validation sont ajoutées entre la création de la diffusion et l&#39;envoi de l&#39;email de notification au responsable du contenu :

1. Après la création d&#39;une nouvelle diffusion, le responsable de l&#39;opération clique sur le lien **[!UICONTROL Soumettre l&#39;édition du contenu]**, dans le tableau de bord de l&#39;opération, pour lancer le cycle d&#39;édition du contenu.

1. Le responsable de l&#39;édition du contenu reçoit un email l&#39;informant de la mise à disposition du contenu.

1. Il se connecte à la console, ouvre la diffusion et l&#39;édite via un assistant d&#39;édition simplifié lui permettant de modifier l&#39;objet, le contenu HTML et texte, et d&#39;envoyer des BAT.

   >[!NOTE]
   >
   >Si vous avez sélectionné, dans la fenêtre de paramétrage de la validation des traitements, l&#39;option **[!UICONTROL Activer l&#39;envoi des BAT]** (pour une diffusion email) ou **[!UICONTROL Activer l&#39;envoi et la validation des BAT]** (pour une diffusion courrier), l&#39;envoi des BAT se fait automatiquement.

1. Lorsqu&#39;il a terminé l&#39;édition du contenu de la diffusion, le responsable de l&#39;édition du contenu peut mettre le contenu à disposition.

   Pour cela, ils peuvent utiliser :

   * la valeur **[!UICONTROL Contenu disponible]** dans la console Adobe Campaign.
   * le lien contenu dans le message de notification.
L&#39;opérateur peut ajouter un commentaire avant de soumettre le contenu au responsable de l&#39;opération.
Le message de notification permet au responsable de valider ou refuser le contenu qui lui a été soumis.

#### Validation externe du contenu {#external-content-approval}

Cette option permet de définir un responsable externe du contenu qui validera le rendu de la diffusion, par exemple la cohérence de la communication de la marque, les tarifs annoncés, etc. Lorsque l&#39;option **[!UICONTROL Validation externe du contenu]** est sélectionnée dans la fenêtre de paramétrage de la validation des traitements, plusieurs étapes de validation sont ajoutées entre la validation du contenu par le responsable du contenu et l&#39;envoi de l&#39;email de notification au responsable de l&#39;opération :

1. Le responsable externe du contenu reçoit un email de notification l&#39;informant que le contenu a été validé et que la validation externe doit être effectuée.
1. L&#39;email de notification propose des liens vers les BAT envoyés, lui permettant de visualiser le rendu de la diffusion, et un bouton pour valider ou refuser le contenu de la diffusion.

Ces liens ne sont disponibles que si un ou plusieurs BAT ont été envoyés. Si ce n&#39;est pas le cas, vous devez accéder à la console ou l&#39;interface web pour visualiser le rendu de la diffusion.

### Validation d’un fichier d’extraction {#approve-an-extraction-file}

Pour les diffusions offline, Adobe Campaign génère un fichier d&#39;extraction qui, selon le paramétrage, est transmis au routeur. Le contenu du fichier dépend du modèle d&#39;export utilisé.

Une fois le contenu, le ciblage et le budget validés, la diffusion passe à l&#39;état **[!UICONTROL Extraction en attente]**, en attendant le lancement du workflow d&#39;extraction pour les opérations.

A la date de la demande d&#39;extraction, le fichier d&#39;extraction est créé et la diffusion passe à l&#39;état **[!UICONTROL Fichier à valider]**.

Vous pouvez visualiser le contenu du fichier extrait (en cliquant sur son nom), le valider, ou, au besoin, modifier le format et relancer l&#39;extraction, via les liens proposés dans le tableau de bord.

Une fois le fichier validé, vous pouvez envoyer l’e-mail de notification au routeur. [En savoir plus](marketing-campaign-deliveries.md#start-an-offline-delivery).

## Modes de validation {#approval-modes}

Les traitements peuvent être validés dans le tableau de bord de l&#39;opération, dans l&#39;onglet de tracking des diffusions, dans le tableau de bord de la diffusion ou dans l&#39;email de notification envoyé aux validants.

### Approuver dans le tableau de bord {#approval-via-the-dashboard}

Pour valider un traitement depuis la console ou l&#39;interface web, cliquez sur le lien correspondant dans le tableau de bord de l&#39;opération.

Par exemple, une fois l&#39;analyse de diffusion exécutée :

1. Sélectionner **[!UICONTROL Valider le ciblage]**.

![](assets/target-validation-from-console.png)

1. Dans la fenêtre contextuelle, vérifiez les informations à valider.
1. Sélectionnez **[!UICONTROL Accepter]** ou **[!UICONTROL Refuser]** et saisissez éventuellement un commentaire. Ce commentaire s’affiche dans les journaux de validation.
1. Confirmez votre choix en utilisant la méthode **[!UICONTROL Validation de la cible]** bouton .

![](assets/confirm-validation-from-console.png)


Lorsqu&#39;un traitement a déjà été validé par un opérateur, le lien de validation n&#39;est pas proposé.

Si un traitement a été rejeté, les informations sont affichées dans le tableau de bord de la diffusion de la manière suivante :

![](assets/target-approval-rejected.png)


### Valider depuis les messages de notification {#approval-via-notification-messages}

Pour approuver une tâche à partir de la fonction [message de notification](#notifications):

1. Cliquez sur le lien de la notification.
1. Connexion à Adobe Campaign.
1. Vérifier les informations à valider
1. Sélectionnez **[!UICONTROL Accepter]** ou **[!UICONTROL Refuser]** et saisissez éventuellement un commentaire.
1. Validation. Votre choix et votre commentaire s’affichent dans les journaux de validation.

>[!NOTE]
>
>Si des alertes ont été générées par le traitement, un message d&#39;avertissement est affiché dans la notification.

### Suivi de la validation{#approval-tracking}

Les journaux d’approbation sont disponibles dans l’interface utilisateur :

* Dans le log de validation de l&#39;opération, **[!UICONTROL Approbations]** sous-onglet du **[!UICONTROL Modifier > Audit]** tab :

   ![](assets/approval-tracking-from-campaign.png)

* Dans le log de diffusion de l&#39;opération, **[!UICONTROL Diffusions]** sous-onglet du **[!UICONTROL Modifier > Audit]** tab :

   ![](assets/approval-tracking-from-campaign-deliveries.png)

* Pour visualiser l&#39;état de validation de chaque diffusion, cliquez sur le bouton **[!UICONTROL Masquer/afficher les journaux]** de l’option **[!UICONTROL Résumé]** .

   ![](assets/approval-tracking-delivery-dashboard.png)

* Ces informations sont également accessibles à partir du **[!UICONTROL Audit > Validations]** onglet de chaque diffusion :

   ![](assets/approval-tracking-delivery-tab.png)

>[!NOTE]
>
>Une fois qu&#39;un opérateur a validé ou refusé un traitement, les autres opérateurs validants ne peuvent plus le modifier.

### Approbation automatique/manuelle {#automatic-and-manual-approval}

Lors de la création d&#39;un workflow de ciblage, lorsque la validation est automatique (mode par défaut), Adobe Campaign propose le lien de validation ou envoie une notification dès qu&#39;un ciblage est à valider.

Pour choisir le mode de validation (manuelle ou automatique), cliquez sur le bouton **[!UICONTROL Modifier > Propriétés]** de l&#39;opération ou du modèle d&#39;opération, puis cliquez sur **[!UICONTROL Paramètres avancés de l&#39;opération...]** et enfin le **[!UICONTROL Approbations]** .
par
![](assets/approval-mode.png)

>[!NOTE]
>
>Le mode de validation s&#39;applique à toutes les diffusions de l&#39;opération.

La validation manuelle permet, lors de la construction du workflow de ciblage, de ne pas créer les liens de validation et envoyer les notifications automatiquement. Le tableau de bord de l&#39;opération propose alors un lien **[!UICONTROL Soumettre le ciblage à validation]** afin de lancer le processus de validation manuellement.

Un message de confirmation permet d&#39;autoriser les validations sur les traitements sélectionnés pour cette diffusion.

Les boutons de validation sont alors affichés dans le tableau de bord de l&#39;opération (au niveau de cette diffusion), dans le tableau de bord de la diffusion et dans le tracking des diffusions. Si les notifications sont activées, elles seront parallèlement envoyées.

Ce mode d&#39;activation des validations permet de travailler sur des recherches de ciblage sans notifier les opérateurs validants de façon intempestive.

## Notifications {#notifications}

Les notifications sont des emails spécifiques envoyés aux opérateurs validants afin de les avertir qu&#39;un traitement est en attente de validation. Lorsque l&#39;opérateur clique sur le lien contenu dans le message, il accède à une page d&#39;authentification. Après connexion, il peut consulter les éléments concernés puis valider ou non le traitement. Il peut également saisir un commentaire dans la fenêtre de validation.

Le contenu des emails de notification peut être personnalisé. Voir [Contenu des notifications](#notification-content).

### Activation/désactivation de la notification {#enabling-disabling-notification}

Par défaut, les messages de notification sont envoyés si la validation du traitement correspondant est activée au niveau du modèle de l&#39;opération, au niveau de l&#39;opération ou au niveau de la diffusion concernée. Toutefois, il est possible de désactiver les notifications afin de n&#39;autoriser les validations que depuis la console.

Pour cela, éditez la fenêtre de validation de l&#39;opération ou du modèle d&#39;opération ( **[!UICONTROL Modifier > Propriétés]** > **[!UICONTROL Paramètres avancés de l&#39;opération...]** > **[!UICONTROL Approbations]** et sélectionnez **[!UICONTROL Ne pas activer l’envoi de notifications]**.

![](assets/enable-disable-notifications.png)

### Contenu des messages de notification {#notification-content}

Le contenu des notifications est défini dans un modèle spécifique : **[!UICONTROL Notification des validations dans une opération marketing]**. Ce modèle est enregistré dans le dossier **[!UICONTROL Administration > Gestion de campagne > Modèles des diffusions techniques]** de l&#39;arborescence Adobe Campaign.
