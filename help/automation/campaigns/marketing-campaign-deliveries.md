---
product: campaign
title: Diffusions de campagnes marketing
description: En savoir plus sur les diffusions d'opérations marketing
feature: Campaigns, Resource Management, Cross Channel Orchestration
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 35%

---

# Diffusions de campagnes marketing {#marketing-campaign-deliveries}

Orchestrez vos diffusions cross-canal dans vos campagnes : rationaliser vos communications avec Adobe Campaign par le biais d&#39;emails personnalisés, de SMS, de notifications push et de messages in-app. Vous pouvez utiliser des médias enrichis tels que des vidéos, des émoticônes ou des GIFs et les intégrer directement.

Les diffusions peuvent être créées depuis le tableau de bord d&#39;une opération, un workflow d&#39;opération ou directement à partir de la vue d&#39;ensemble des diffusions. Une fois créées à partir d’une campagne, les diffusions y sont liées et sont consolidées au niveau de cette campagne.

## Création de diffusions {#create-deliveries}

Vous pouvez ajouter des diffusions à vos campagnes marketing de deux façons :

* Dans la **[!UICONTROL Ajouter une diffusion]** dans le tableau de bord de l&#39;opération.

![](assets/campaign_op_add_delivery.png)

Une fois enregistrée, la diffusion est ajoutée dans le tableau de bord de l&#39;opération.

* Dans un workflow de campagne, dans la variable **[!UICONTROL Ciblage et workflows]** en ajoutant la diffusion.

   ![](assets/campaign-wf-delivery.png)

   Une fois le workflow démarré, la diffusion est ajoutée dans le tableau de bord de l&#39;opération.

Découvrez comment configurer et exécuter le flux de validation de diffusion [dans cette page](marketing-campaign-approval.md).

## Démarrage dʼune diffusion {#start-a-delivery}

Une diffusion peut être envoyée une fois toutes les validations accordées. Le processus d&#39;exécution de la diffusion dépend du canal.

* Pour les diffusions par email ou sur les canaux mobiles, reportez-vous à la section [cette section](#start-an-online-delivery)

* Pour les diffusions courrier, voir [cette section](#start-an-offline-delivery)

### Démarrer une diffusion email ou mobile {#start-an-online-delivery}

Une fois toutes les demandes de validation approuvées, la diffusion passe à l’état **[!UICONTROL Confirmation en attente]** et peuvent être démarrés. Les validants qui peuvent démarrer la diffusion sont informés qu&#39;une diffusion est prête à être démarrée.

![](assets/confirm-delivery.png)

L&#39;information est également remontée au niveau du tableau de bord de l&#39;opération. Le lien **[!UICONTROL Confirmer l&#39;envoi]** permet de lancer la diffusion.

![](assets/confirm-delivery-from-dashboard.png)

La confirmation de la diffusion est réservée aux administrateurs, ainsi qu&#39;à l&#39;opérateur ou au groupe d&#39;opérateurs explicitement mentionnés dans les propriétés de la diffusion ou de la campagne. Si aucun opérateur n&#39;est conçu, les administrateurs et le propriétaire de l&#39;opération peuvent valider.

![](assets/select-delivery-reviewers.png)

Cependant, vous pouvez également permettre au propriétaire de l&#39;opération de confirmer l&#39;envoi, même si des opérateurs validants spécifiques ont été définis dans les propriétés de la diffusion ou de la campagne. Pour ce faire, en tant qu’administrateur, créez la variable **NmsCampaign_Activate_OwnerConfirmation** et définissez-la sur **1**. Les options sont gérées à partir du **[!UICONTROL Administration]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Options]** dans l’explorateur Adobe Campaign.


### Démarrer une diffusion courrier {#start-an-offline-delivery}

Une fois toutes les validations accordées, l&#39;état de la diffusion passe à **[!UICONTROL En attente d&#39;extraction]**. Les fichiers d&#39;extraction sont créés via un dossier dédié [workflow technique](../workflow/technical-workflows.md) qui, dans une configuration par défaut, démarre automatiquement lorsqu&#39;une diffusion courrier est en attente d&#39;extraction. Lorsqu&#39;un processus est en cours, il est affiché dans le tableau de bord et peut être édité à partir de son lien.

Une fois le workflow d&#39;extraction exécuté correctement, le fichier d&#39;extraction doit être validé (sous réserve que la validation du fichier d&#39;extraction ait été sélectionnée dans le paramétrage de la diffusion). [En savoir plus](marketing-campaign-approval.md#approving-an-extraction-file).

Suivez les étapes ci-dessous pour valider le contenu et envoyer le fichier au fournisseur :

1. Une fois le fichier d’extraction validé, vous pouvez générer le BAT de l’e-mail de notification au routeur. Ce message e-mail est construit à partir d’un modèle de diffusion. Il doit être approuvé.

   Cette étape n’est disponible que si la variable **[!UICONTROL Activer l&#39;envoi et la validation des BAT (courrier)]** était activée dans . **[!UICONTROL Approbations]** de l&#39;onglet paramètres avancés de l&#39;opération.

   ![](assets/enable-proof-validation.png)

1. Cliquez sur le bouton **[!UICONTROL Envoyer un BAT]** pour lancer la création des BAT.

   La cible des BAT doit avoir été préalablement définie.

   Vous pouvez créer autant de BAT que nécessaire. Ils sont accessibles à partir du lien **[!UICONTROL Courriers...]** du détail de la diffusion.

1. La diffusion est alors à l&#39;état **[!UICONTROL A soumettre]**. Le bouton **[!UICONTROL Soumettre les BAT]** lance le processus de validation des BAT.

1. La diffusion passe à l&#39;état **[!UICONTROL BAT à valider]** et un bouton permet d&#39;accepter ou refuser la validation.

   Vous pouvez alors accepter ou refuser cette validation, ou revenir à l&#39;étape d&#39;extraction

1. Une fois le BAT validé, le fichier d&#39;extraction est envoyé au routeur et la diffusion est terminée.

### Calcul des budgets et des coûts {#compute-costs-and-stocks}

L&#39;extraction du fichier lance deux processus : calcul du budget et du stock. Les entrées de budget sont mises à jour.

* Le **[!UICONTROL Budget]** vous permet de gérer les budgets de l&#39;opération. Le total des postes de coût est affiché dans la variable **[!UICONTROL Coût calculé]** champ de l&#39;onglet principal de l&#39;opération et du programme auquel elle appartient. Les montants sont également répercutés dans le budget de l&#39;opération.

   ![](assets/campaign-budget-tab.png)

   Le coût réel sera calculé au final en fonction des informations fournies par le routeur : seuls les courriers réellement envoyés sont facturés.

* Les stocks sont définis dans la variable **[!UICONTROL Administration > Gestion de campagne > Stocks]** du noeud de l’arborescence.

   ![](assets/campaign-stocks.png)

   Structures de coûts dans la variable **[!UICONTROL Administration > Gestion de campagne > Prestataires]** noeud .

   ![](assets/campaign-service-providers.png)

   Au niveau des stocks, vous pouvez visualiser les lignes de stocks. Pour définir le stock initial, vous devez ouvrir une ligne de stock. Le stock est décrémenté au fur et à mesure des diffusions. Vous pouvez définir un niveau d&#39;alerte et des notifications.


   >[!NOTE]
   >
   >En savoir plus sur les budgets [dans cette section](providers--stocks-and-budgets.md).
