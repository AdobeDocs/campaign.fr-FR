---
title: Messagerie transactionnelle de Campaign
description: Prise en main de la messagerie transactionnelle
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 253f3be945cbfa304fa7342c68f0c73b079e2870
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 100%

---

# Prise en main de la messagerie transactionnelle{#send-transactional-messages}

La messagerie transactionnelle (Message Center) est un module de Campaign conçu pour gérer les messages de déclenchement. Ces notifications sont générées à partir d’événements déclenchés depuis des systèmes d’information et peuvent correspondre aux éléments suivants : facture, confirmation de commande, confirmation d&#39;expédition, changement de mot de passe, notification d&#39;indisponibilité du produit, relevé de compte, création de compte web, etc.

>[!NOTE]
>
>En tant qu’utilisateur ou utilisatrice Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support){target="_blank"} pour configurer la messagerie transactionnelle de Campaign dans votre environnement.

Les messages transactionnels sont utilisés pour envoyer :

* des notifications, telles que les confirmations de commande ou les réinitialisations de mot de passe, par exemple ;
* une réponse individuelle en temps réel à une action client ;
* du contenu non promotionnel.

Les paramètres de messagerie transactionnelle sont décrits dans [cette section](../config/transactional-msg-settings.md).

Découvrez l’architecture de la messagerie transactionnelle dans [cette page](../architecture/architecture.md#transac-msg-archi).

## Principe de fonctionnement des messages transactionnels {#transactional-messaging-operating-principle}

Le module de messages transactionnels Adobe Campaign s&#39;intègre dans un système d&#39;informations qui renvoie les événements à transformer en messages transactionnels personnalisés. Ces messages peuvent être envoyés individuellement ou par lots via e-mail, SMS ou notifications push.

Par exemple, imaginez que vous êtes une société disposant d&#39;un site web sur lequel vos clients peuvent acheter des produits.

Adobe Campaign vous permet d’envoyer un email de notification aux clients qui ont ajouté des produits à leur panier. Lorsque l&#39;un d&#39;eux quitte votre site web sans passer par ses achats (événement externe qui déclenche un événement Campaign), un email d&#39;abandon de panier lui est automatiquement envoyé (diffusion de message transactionnel).

Les principales étapes de mise en place de ce système sont décrites ci-dessous :

1. [Créer un type d&#39;événement](#create-event-types).
1. [Créer et concevoir le modèle de message](transactional-template.md#create-message-template). Vous devez associer un événement à votre message au cours de cette étape.
1. [Tester le message](transactional-template.md#test-message-template).
1. [Publier le modèle de message](transactional-template.md#publish-message-template).

Une fois que vous avez conçu et publié le modèle de message transactionnel, si un événement correspondant est déclenché, les données pertinentes sont envoyées à Campaign via les [méthodes SOAP](../send/event-description.md) PushEvent et PushEvents, puis la diffusion est envoyée aux destinataires ciblés.

## Création de types d&#39;événements {#create-event-types}

Pour que chaque événement puisse être transformé en message personnalisé, vous devez d&#39;abord créer des **types d&#39;événements**.

Lors de la [création d&#39;un modèle de message](#create-message-template), vous sélectionnerez le type d&#39;événement correspondant au message que vous souhaitez envoyer.

>[!CAUTION]
>
>Vous devez créer des types d&#39;événements avant de pouvoir les utiliser dans des modèles de message.

Pour créer des types d&#39;événements qui seront traités par Adobe Campaign, procédez comme suit :

1. Accédez au dossier **[!UICONTROL Administration > Plateforme > Énumérations]** de l’explorateur Campaign.
1. Sélectionnez l’énumération **[!UICONTROL Type d’événement]** de la liste.
1. Cliquez sur **[!UICONTROL Ajouter]** pour créer une valeur d&#39;énumération. Il peut s&#39;agir d&#39;une confirmation de commande, d&#39;un changement de mot de passe, d&#39;un changement de livraison de commande, etc.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Chaque type d&#39;événement doit correspondre à une valeur de l&#39;énumération **[!UICONTROL Type d&#39;événement]**.

1. Une fois les valeurs de l&#39;énumération créées, vous devez vous déconnecter puis vous reconnecter à votre instance afin que la création soit effective.

>[!NOTE]
>
>Pour en savoir plus sur les énumérations, consultez [cette page](../../v8/config/ui-settings.md#enumerations).

Pour l’étape suivante, découvrez comment [créer et publier votre modèle pour la messagerie transactionnelle](transactional-template.md).
