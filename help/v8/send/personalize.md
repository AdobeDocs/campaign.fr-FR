---
title: Prise en main de la personnalisation
description: Découvrez comment personnaliser le contenu des messages.
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 100%

---

# Prise en main de la personnalisation {#personalize-content}

Pour tirer le meilleur parti de chacune de vos campagnes marketing, Adobe Campaign permet de diffuser du contenu personnalisé adapté au profil de la clientèle. Les fonctionnalités de personnalisation d’Adobe Campaign, basées sur les données de profil, vous permettent de créer une expérience personnalisée pour chaque groupe et personne : adaptez vos messages en fonction du ou de la destinataire grâce aux données et informations dont vous disposez à son sujet. Il peut s’agir de son prénom, de ses centres d’intérêts, de l’endroit où il/elle vit, de ses achats et bien plus encore.

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

  Configurez du contenu conditionnel pour ajouter une personnalisation dynamique basée notamment sur le profil de la personne destinataire. Lorsqu’une condition est rencontrée, des blocs de texte et/ou des images sont alors insérés. [En savoir plus](conditions.md).

<!--* Add **personalized offers**
    
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

Découvrez les différents types de contenu dynamique et apprenez à créer et à appliquer des blocs de personnalisation et des instructions conditionnelles à une diffusion.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
