---
solution: Campaign v8
product: Adobe Campaign
title: Gestion des abonnements et des désabonnements dans Campaign
description: Découvrez comment gérer les abonnements et les désabonnements dans Campaign v8
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 8%

---

# Gestion des abonnements et des désabonnements{#optin-optout}

Utilisez Adobe Campaign pour créer et surveiller vos services d’information tels que les newsletters et pour gérer les abonnements/désabonnements à ces services. Plusieurs services peuvent être définis en parallèle, par exemple : newsletters spécialisées pour certaines catégories de produits, thèmes ou zones d’un site web, abonnements à différents types de messages d’alerte et notifications en temps réel. Voir à ce propos la section Gestion des abonnements.

:[!DNL :arrow_upper_right:] : Découvrez comment créer un service d’information, envoyer une newsletter et gérer l’opt-in et l’opt-out dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html)

Pour abonner (opt-in) un profil à un service, les options disponibles sont les suivantes :

* Ajoutez manuellement le service au profil du destinataire : pour cela, dans l&#39;onglet **[!UICONTROL Abonnements]** de leur profil, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le service d&#39;information visé.

   :[!DNL :arrow_upper_right:] : En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)

* Abonner automatiquement un ensemble de destinataires au service. La liste des destinataires peut provenir d&#39;une opération de filtrage, d&#39;un groupe, d&#39;un dossier, d&#39;un import ou d&#39;une sélection manuelle directe. Pour abonner ces destinataires, sélectionnez les profils et cliquez avec le bouton droit de la souris. Sélectionnez **[!UICONTROL Actions > Abonner la sélection à un service...]**, sélectionnez le service concerné et démarrez l’opération.

   :[!DNL :arrow_upper_right:] : En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab)


* Importer des destinataires et les abonner automatiquement à un service d&#39;information : pour cela, sélectionnez le service visé dans la dernière étape de l&#39;assistant d&#39;import.

   :[!DNL :arrow_upper_right:] : En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients)

* Utiliser un formulaire web pour que les destinataires puissent s&#39;abonner à un service.

   :[!DNL :arrow_upper_right:] : En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in)


* Créez un workflow de ciblage et à l&#39;aide d&#39;une activité **[!UICONTROL Service d&#39;inscriptions]**.

   :[!DNL :arrow_upper_right:] : En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter)


Pour désabonner (exclure) un profil d’un service, les options disponibles sont les suivantes :

**Désinscription manuelle**

* Lien de désinscription personnalisé ou formulaire web
* Suppression manuelle d’un service d’information
* Suppression manuelle des destinataires d’un service d’abonnement particulier

**Désinscription automatique**

* Définissez une limite de durée du service d’information : les destinataires seront automatiquement désabonnés à l&#39;expiration de la période de validité. Cette période est spécifiée dans l&#39;onglet Edition des propriétés du service. Il est exprimé en jours.
* Configurer un workflow de désinscription pour une population

:[!DNL :arrow_upper_right:] : En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service)


>[!CAUTION]
>
>Les abonnements et les désabonnements sont des processus **asynchrones**. Les demandes d’opt-in et d’opt-out sont traitées toutes les heures. [En savoir plus](../dev/new-apis.md#sub-apis)

Vous pouvez également permettre aux destinataires de vos diffusions de transférer des messages à un ami. Pour cela, insérez les liens correspondants dans votre diffusion. Vous pouvez ensuite suivre ce processus de partage ainsi que le nombre de visites sur les pages concernées.

:[!DNL :arrow_upper_right:] : Pour plus d’informations sur cette fonctionnalité, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend).