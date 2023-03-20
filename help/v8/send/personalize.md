---
title: Prise en main de la personnalisation
description: Découvrez comment personnaliser le contenu d'un message
feature: Personalization
role: User
level: Beginner
source-git-commit: a8568e0c1e9af11b533b7d435691dc12cc0a2485
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Prise en main de la personnalisation {#personalize-content}

Pour tirer le meilleur parti de chaque campagne marketing, Adobe Campaign vous offre un moyen de diffuser du contenu personnalisé qui s’adresse aux clients à leur niveau. En fonction des données de profil, des fonctionnalités de personnalisation pour créer une expérience personnalisée pour différents groupes et individus : vous pouvez adapter vos messages à chaque destinataire spécifique en exploitant les données et informations dont vous disposez à son sujet. Il peut s&#39;agir de leur prénom, de leurs intérêts, de leur lieu de vie, de ce qu&#39;ils ont acheté, et bien plus encore.

Adobe Campaign simplifie la personnalisation : vous pouvez afficher différents types de contenu personnalisés pour chaque destinataire à l’aide d’un seul [modèle de courrier électronique](create-templates.md). Dans vos messages transactionnels, tels que les emails de confirmation d’achat ou d’abandon de panier, incluez les informations de liste de produits pour chaque individu dans un modèle d’email unique.


## Stratégies de personnalisation {#personalization-strategy}

Utilisez Campaign pour créer du contenu dynamique et envoyer des messages personnalisés. Les fonctionnalités de personnalisation peuvent être combinées pour améliorer vos messages et créer une expérience utilisateur personnalisée.

Vous pouvez personnaliser le contenu du message en procédant comme suit :

* Insérer des **champs de personnalisation** dynamiques.

   Les champs de personnalisation sont utilisés pour la personnalisation de premier niveau de vos messages. Vous pouvez sélectionner n’importe quel champ disponible dans la base de données de l’éditeur de personnalisation. Pour une diffusion, vous pouvez sélectionner n’importe quel champ associé au ou à la destinataire, au message ou à la diffusion. Ces attributs de personnalisation peuvent être insérés dans l’objet ou dans le corps de vos messages. [En savoir plus](personalization-fields.md).

   La syntaxe suivante insère la ville du ou de la destinataire dans votre contenu : &lt;%= recipient.location.city %>.

* Insérer des **blocs de contenu** prédéfinis

   Campaign est fourni avec un ensemble de blocs de personnalisation qui contiennent un rendu spécifique que vous pouvez insérer dans vos diffusions. Vous pouvez par exemple ajouter un logo, un message de salutation ou un lien vers la page miroir du message. Les blocs de contenu sont disponibles à partir d’une entrée dédiée dans l’éditeur de personnalisation. [En savoir plus](personalization-blocks.md).

* Créer **contenu conditionnel**

   Configurez du contenu conditionnel pour ajouter une personnalisation dynamique basée sur le profil du destinataire, par exemple. Des blocs de texte et/ou des images sont insérés lorsqu’une condition particulière est vraie. [En savoir plus](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Barrières de sécurité et recommandations{#perso-guardrails}

### Délai d’expiration de personnalisation{#perso-timeout}

Pour améliorer la protection de la diffusion, vous pouvez définir un délai d’expiration pour la phase de personnalisation.

Dans l’onglet **[!UICONTROL Livraison]** des **[!UICONTROL Propriétés de diffusion]**, sélectionnez une valeur maximale en secondes pour l’option **[!UICONTROL Durée maximale d’exécution de la personnalisation]**.

Lors de l’aperçu ou de l’envoi, si la phase de personnalisation dépasse la durée maximale définie dans ce champ, le processus est abandonné avec un message d’erreur et la diffusion échoue.

La valeur par défaut est de 5 secondes.

Si vous définissez cette option sur 0, il n’y aura aucune limite de temps pour la phase de personnalisation.


### Variables internes{#internal-variables}

Les variables suivantes sont des variables internes qui peuvent être utilisées dans le cadre de la personnalisation, mais ne doivent pas être modifiées : **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue**, **proposition**.


## Tutoriel vidéo {#personalization-video}

Découvrez les différents types de contenu dynamique et apprenez à créer et à appliquer des blocs de personnalisation et des instructions conditionnelles à une diffusion.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)