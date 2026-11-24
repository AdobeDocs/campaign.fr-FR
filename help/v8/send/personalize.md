---
title: Commencer avec la personnalisation
description: Découvrez comment personnaliser le contenu des messages.
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
TQID: 'https://experienceleague.adobe.com/G8-4BinRvCMosfdiTD6FuEztviEDn6ea8hKeQd8QVSA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 13af5358-448e-5a4a-850b-0db592bb0f8f
    internal-label: Personalization
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: ba520da057d2568b2ef65042342301f5ad5eacd8
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 82%
---
# Commencer avec la personnalisation {#personalize-content}

Pour tirer le meilleur parti de chacune de vos campagnes marketing, Adobe Campaign permet de diffuser du contenu personnalisé adapté au profil de la clientèle. En fonction des données de profil, les fonctionnalités de personnalisation vous permettent de créer une expérience personnalisée pour différents groupes et individus : vous pouvez adapter vos messages à chaque destinataire spécifique en exploitant les données et informations que vous possédez à son sujet. Il peut s’agir de son prénom, de ses centres d’intérêts, de l’endroit où il/elle vit, de ses achats et bien plus encore.

Adobe Campaign simplifie la personnalisation : affichez différents types de contenu personnalisé à chaque personne destinataire à l’aide d’un seul [modèle de message](create-templates.md). Dans vos messages transactionnels, tels que les e-mails de confirmation d’achat ou d’abandon de panier, incluez les informations sur les listes de produits pour chaque personne dans un modèle d’e-mail unique.


## Stratégies de personnalisation {#personalization-strategy}

Utilisez Campaign pour créer du contenu dynamique et envoyer des messages personnalisés. Vous pouvez cumuler les fonctionnalités de personnalisation afin d’améliorer vos messages et créer une expérience utilisateur personnalisée.

Vous pouvez personnaliser le contenu du message en procédant comme suit :

* Insérer des **champs de personnalisation** dynamiques.

  Les champs de personnalisation sont utilisés pour la personnalisation de premier niveau de vos messages. Vous pouvez sélectionner n’importe quel champ disponible dans la base de données de l’éditeur de personnalisation. Pour une diffusion, vous pouvez sélectionner n’importe quel champ associé au ou à la destinataire, au message ou à la diffusion. Ces attributs de personnalisation peuvent être insérés dans l’objet ou dans le corps de vos messages. [En savoir plus](personalization-fields.md).

  La syntaxe suivante insère la ville du ou de la destinataire dans votre contenu : &lt;%= recipient.location.city %>.

* Insérer des **blocs de contenu** prédéfinis

  Campaign est fourni avec un ensemble de blocs de personnalisation qui contiennent un rendu spécifique que vous pouvez insérer dans vos diffusions. Vous pouvez par exemple ajouter un logo, un message de salutation ou un lien vers la page miroir du message. Les blocs de contenu sont disponibles à partir d’une entrée dédiée dans l’éditeur de personnalisation. [En savoir plus](personalization-blocks.md).

* Créer du **contenu conditionnel**

  Configurez du contenu conditionnel et ajoutez une personnalisation dynamique basée sur le profil du ou de la destinataire, par exemple : Lorsqu’une condition est rencontrée, des blocs de texte et/ou des images sont alors insérés. [En savoir plus](conditions.md).

<!--
* Add **personalized offers**

    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Mécanisme de sécurisation et recommandations{#perso-guardrails}

### Délai d’expiration de la personnalisation {#perso-timeout}

Pour améliorer la protection de la diffusion, vous pouvez définir un délai d’expiration pour la phase de personnalisation.

Dans l’onglet **[!UICONTROL Livraison]** des **[!UICONTROL Propriétés de diffusion]**, sélectionnez une valeur maximale en secondes pour l’option **[!UICONTROL Durée maximale d’exécution de la personnalisation]**.

Lors de la prévisualisation ou de l’envoi, si la phase de personnalisation dépasse la durée maximale définie dans ce champ, le processus est abandonné avec un message d’erreur et la diffusion échoue.

La valeur par défaut est de 5 secondes.

Si vous définissez cette option sur 0, il n’y aura aucune limite de temps pour la phase de personnalisation.


### Variables internes{#internal-variables}

Les variables suivantes sont des variables internes qui peuvent être utilisées dans le cadre de la personnalisation, mais ne doivent pas être modifiées : **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue**, **proposition**.


## Tutoriel vidéo {#personalization-video}

Découvrez les différents types de contenu dynamique et comment créer et appliquer des blocs de personnalisation et des instructions conditionnelles à une diffusion.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
