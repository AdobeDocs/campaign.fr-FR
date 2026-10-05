---
title: Utiliser des environnements Campaign Interaction
description: Découvrez comment créer des environnements pour Campaign Interaction
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
TQID: 'https://experienceleague.adobe.com/SQgbIgxLE5Ef10i6wI07XBeEgBsTpxpMrFIMjgv5Lwo'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 96%
---
# Utilisation des environnements{#work-with-environments}

## Environnements en ligne et en édition{#live-design-environments}

Interaction fonctionne avec deux types d&#39;environnements d&#39;offres :

* Des environnements d’offres **[!UICONTROL Conception]**, dans lesquels les offres sont en cours de création et peuvent être modifiées. Ces offres ne sont pas encore passées par un cycle de validation et ne sont donc pas diffusées aux personnes contacts.
* Des environnements d’offres **[!UICONTROL En ligne]**, qui contiennent les offres approuvées telles qu’elles sont présentées aux personnes contacts. Les offres contenues dans ces environnements sont en lecture seule.

![](assets/offer_environments_overview_001.png)

Chaque environnement **[!UICONTROL Conception]** est lié à un environnement **[!UICONTROL En ligne]**. Lorsqu’une offre est terminée, son contenu et ses règles d’éligibilité sont soumis à un cycle de validation. Lorsque le cycle de validation est complet, l’offre concernée est automatiquement déployée dans l’environnement **[!UICONTROL En ligne]**. Dès lors, elle est disponible pour être diffusée.

Par défaut, Campaign comprend un environnement **[!UICONTROL En édition]** et un environnement **[!UICONTROL En ligne]** qui lui est associé. Les deux environnements sont préconfigurés pour cibler la [table de destinataires native](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>Pour cibler la table des destinataires, vous devez utiliser l&#39;assistant de mapping de ciblage pour créer les environnements. [En savoir plus](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Les chargés de diffusion peuvent uniquement afficher l&#39;environnement **[!UICONTROL En ligne]** et exploiter les offres pour les diffuser. Les chargés d&#39;offres peuvent consulter et utiliser l&#39;environnement **[!UICONTROL En édition]**, et consulter l&#39;environnement **[!UICONTROL En ligne]**. [En savoir plus](interaction-operators.md)

## Création d&#39;un environnement pour les interactions anonymes{#create-an-offer-environment}

Par défaut, Campaign comprend un environnement intégré pour cibler la table des destinataires (offres identifiées). Pour cibler une autre table, par exemple les profils anonymes qui visitent votre site web pour des interactions entrantes, vous devez mettre à jour votre configuration.

Procédez comme suit :

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Gestion de campagne]** > **[!UICONTROL Mappings de ciblage]**, cliquez avec le bouton droit sur le mapping de ciblage à utiliser et sélectionnez **[!UICONTROL Actions]** > **[!UICONTROL Modifier les options de la dimension de ciblage]**.

   ![](assets/offer_env_anonymous_001.png)

1. Cliquez sur **[!UICONTROL Suivant]**, sélectionnez l&#39;option **[!UICONTROL Générer un schéma de stockage pour les propositions]** et cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Si la case est déjà cochée, décochez-la puis recochez-la.

1. Adobe Campaign crée les deux environnements **[!UICONTROL En édition]** et **[!UICONTROL En ligne]** correspondant au mapping de ciblage activé précédemment. L’environnement est préconfiguré avec les informations de ciblage.

Si vous avez activé le mapping **[!UICONTROL Visiteurs]**, la case **[!UICONTROL Environnement dédié aux interactions anonymes entrantes]** est automatiquement cochée dans l&#39;onglet **[!UICONTROL Général]** de l&#39;environnement.

Cette option vous permet d’activer les fonctions spécifiques aux interactions anonymes, notamment lors de la configuration des emplacements d’environnement. Vous pouvez également configurer des options permettant de basculer d’un environnement « identifié » vers un environnement « anonyme ».

Vous pouvez par exemple lier un emplacement d&#39;environnement de destinataire (contact identifié) à un emplacement correspondant d&#39;environnement de visiteur (contact non identifié). Ainsi, différentes offres seront mises à la disposition du contact, en fonction du caractère identifié ou non de ce dernier. Voir à ce sujet la section [Créer des emplacements](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>Pour plus d&#39;informations sur les interactions anonymes sur canal entrant, consultez la section [Interactions anonymes](anonymous-interactions.md).
