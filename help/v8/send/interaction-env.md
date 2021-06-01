---
product: Adobe Campaign
title: Opérateurs d'interaction Campaign
description: Créer des opérateurs Gestion des offres
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 37%

---

# Environnements en ligne et édition{#live-design-environments}

Interaction fonctionne avec deux types d&#39;environnements d&#39;offres :

* des environnements d&#39;offres **[!UICONTROL En édition]**, dans lesquels les offres sont en cours de création et peuvent être modifiées. Ces offres ne sont pas encore passées par un cycle de validation et ne sont donc pas diffusées aux contacts.
* des environnements d&#39;offres **[!UICONTROL En ligne]** qui contiennent les offres validées, telles qu&#39;elles sont présentées aux contacts. Les offres contenues dans ces environnements sont en lecture seule.

![](assets/offer_environments_overview_001.png)

Chaque environnement **[!UICONTROL En édition]** est associé à un environnement **[!UICONTROL En ligne]**. Lorsqu&#39;une offre est finalisée, son contenu et ses règles d&#39;éligibilité passent par un cycle de validation. Lorsque le cycle de validation est complet, l&#39;offre concernée est automatiquement déployée dans l&#39;environnement **[!UICONTROL En ligne]**. Dès lors, elle est disponible pour être diffusée.

Par défaut, Campaign est livré avec un environnement **[!UICONTROL Conception]** et un environnement **[!UICONTROL Live]** qui lui est associé. Les deux environnements sont préconfigurés pour cibler la [table de destinataires intégrée](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>Pour cibler la table des destinataires, vous devez utiliser l&#39;assistant de mapping de ciblage pour créer les environnements. [En savoir plus](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Les gestionnaires de diffusion peuvent uniquement afficher l’environnement **[!UICONTROL En ligne]** et exploiter les offres pour les diffuser. Les gestionnaires d’offres peuvent afficher et utiliser l’environnement **[!UICONTROL Conception]**, ainsi que l’environnement **[!UICONTROL Live]**. [En savoir plus](interaction-operators.md).

## Créer un environnement d&#39;offres {#creating-an-offer-environment}

Par défaut, Campaign est livré avec un environnement intégré pour cibler la table des destinataires (offres identifiées). Pour cibler un autre tableau, procédez comme suit :

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Gestion de campagne]** > **[!UICONTROL Mappings de ciblage]**, cliquez avec le bouton droit sur le mapping de ciblage à utiliser et sélectionnez **[!UICONTROL Actions]** > **[!UICONTROL Modifier les options de la dimension de ciblage]**.

   ![](assets/offer_env_anonymous_001.png)

1. Cliquez sur **[!UICONTROL Suivant]**, sélectionnez l&#39;option **[!UICONTROL Générer un schéma de stockage pour les propositions]** et cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Si l’option est déjà cochée, décochez-la, puis revérifiez-la.

1. Adobe Campaign crée deux environnements - **[!UICONTROL Conception]** et **[!UICONTROL Live]** - avec les informations de ciblage du mapping de ciblage activé précédemment. L&#39;environnement est préconfiguré avec les informations de ciblage.
