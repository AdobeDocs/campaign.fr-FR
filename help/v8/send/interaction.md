---
product: Adobe Campaign
title: Interaction de Campaign - Gestion des offres
description: Prise en main de la Gestion des offres
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 15%

---

# Interaction et la gestion des offres{#interaction-and-offer-management}

Campaign est livré avec un module **Interaction** qui permet de répondre en temps réel lors d&#39;une interaction avec un contact donné (un client ou une cible) en proposant une ou plusieurs offres adaptées. Par exemple, il peut s’agir de messages de communication simples, d’offres spéciales sur un ou plusieurs produits ou d’un service.

Vous pouvez créer un catalogue d&#39;offres qui s&#39;interface avec vos canaux sortants (email, courrier, SMS) pour sélectionner la meilleure offre à envoyer à un contact dans un contexte donné. La meilleure sélection d&#39;offres pour un destinataire est basée sur **les règles d&#39;éligibilité**. La sélection d’une offre à partir d’un ensemble d’offres pertinentes est déterminée à l’aide de règles de priorité. Les règles de présentation des offres prennent en compte l&#39;historique du contact et évitent de lui faire proposer la même offre plusieurs fois.

Interaction vous permet de créer et gérer un catalogue d’offres, et de paramétrer les règles d’éligibilité et les thèmes d’application qui leur sont associés. Vous pouvez personnaliser le contenu de votre offre selon le canal choisi à l’aide de différentes représentations. Enfin, pour déterminer l’impact d’une présentation d’offres, vous pouvez utiliser le module de simulation mis à votre disposition.

## Prise en main des offres

Les étapes clés pour commencer sont répertoriées ci-dessous.

### Configuration de votre plateforme

Avant de commencer, en tant qu&#39;administrateur de Campaign ****, assurez-vous d&#39;avoir effectué les tâches suivantes dans les environnements de conception :

1. Création de profils utilisateur. [En savoir plus](interaction-operators.md).
1. (Facultatif) Créez un environnement d&#39;offres pour chaque dimension de ciblage. [En savoir plus](interaction-env.md)
1. Créez des règles de typologie pour chaque environnement. [En savoir plus](interaction-offer.md#offer-presentation).
1. Créez des emplacements d&#39;offre pour chaque environnement et configurez les fonctions de rendu. [En savoir plus](interaction-offer-spaces.md).
Si l&#39;emplacement est défini sur un canal unitaire en mode identifié, il est nécessaire de spécifier les paramètres avancés de l&#39;emplacement.

### Créer et publier le catalogue d&#39;offres {#managing-the-offer-catalog-}

En tant que **Chargé d&#39;offres** vous devez effectuer les tâches suivantes :

1. Créez des catégories d’offres dans les environnements de conception. [En savoir plus](interaction-offer-catalog.md#creating-offer-categories).
1. Créez des offres dans des environnements de conception. [En savoir plus](interaction-offer.md).
1. Validez et publiez des offres sur un ou plusieurs emplacements afin de les rendre disponibles dans les environnements en ligne pour le chargé de diffusion. [En savoir plus](interaction-offer.md#approve-offers).

### Tirez parti du catalogue d&#39;offres {#using-the-offer-catalog-}

En tant que **chargé de diffusion**, vous devez effectuer les tâches suivantes :

1. Créez une campagne.
1. Référencez une offre dans l&#39;opération ou la diffusion. [En savoir plus](interaction-send-offers.md).


## Concepts et terminologie

Découvrez les termes spécifiques aux offres et les conseils connexes avant de commencer.

* **** Les environnements incluent un catalogue d’offres et des emplacements (points d’extension). Vous devez créer un environnement par dimension de ciblage.
Il existe deux types d’environnements :

   * **Environnement** de conception : les offres sont créées dans l’environnement de conception, ainsi que dans les règles de typologie et . Les règles de typologie déterminent les offres à présenter (ou non) à une personne ciblée. La table des personnes qui seront ciblées par les offres et la table de stockage de toutes les propositions d&#39;offres sont également définies dans cet environnement. Le noeud **[!UICONTROL Environnement de conception]** contient des sous-dossiers d’emplacements, des filtres prédéfinis et des catégories d’offres. Pour chaque **[!UICONTROL environnement de conception]**, il existe un **[!UICONTROL environnement en ligne]** correspondant, généré à partir de cet **[!UICONTROL environnement de conception]**.
   * **Environnement** en ligne : environnement associé à un  **[!UICONTROL environnement en édition qui contient des offres en lecture seule dont le contenu et l&#39;éligibilité ont été validés via l&#39;environnement en]** édition ****. Ils doivent être sélectionnés pour être présentés et insérés dans un message.

* **L’emplacement** est un emplacement (dossier) définissant l’emplacement d’exposition de l’offre. Lors de la création d&#39;un emplacement, vous pouvez définir le canal, créer le contenu de l&#39;offre à l&#39;aide de fonctions de rendu, définir l&#39;ordre des offres et son mode : mode unitaire et/ou mode batch (par défaut). L&#39;emplacement est l&#39;interface entre le canal et le moteur d&#39;offres.
* Le **Catalogue d’offres** est un ensemble d’offres définies dans Adobe Campaign qui peuvent être sélectionnées lors d’une interaction. Le catalogue est organisé de manière hiérarchique avec chaque noeud correspondant à une catégorie.
* Une **Catégorie** est un dossier lié au catalogue d’offres dans un environnement, qui organise les offres en fonction de la nature, de la date d’éligibilité et du thème de l’application. Une catégorie peut contenir des sous-catégories qui héritent de toutes les caractéristiques de la catégorie parente. Les règles d&#39;éligibilité peuvent être définies pour une catégorie afin de les partager avec plusieurs offres.
* **Les thèmes d&#39;application** sont des mots-clés définis dans la catégorie, qui permettent de filtrer les offres lorsqu&#39;elles sont présentées en limitant la sélection des offres à une ou deux catégories.
* **Les** règles d&#39;éligibilité sont des contraintes appliquées à un environnement, une catégorie ou une offre, liées à la période de validité, la cible et le poids. Elles vous permettent de vous assurer qu’une offre est en phase avec le contact ciblé.

   Au niveau des environnements, les règles d&#39;éligibilité comprennent les règles de présentation appliquées aux offres et les personnes à cibler.

   Au niveau des catégories, les règles d&#39;éligibilité permettent de limiter la validité de la catégorie dans le temps, de définir des thèmes d&#39;application et de déterminer les personnes à cibler. Elles peuvent également recevoir un poids multiplicateur pendant une période donnée. Cela permet de mutualiser les règles pour les offres d&#39;une même catégorie et ainsi d&#39;en simplifier la gestion.

   Au niveau des offres, les règles d&#39;éligibilité permettent de limiter la validité des offres dans le temps et de déterminer les personnes à cibler.

* **Arbitrage** est l’action de sélection des offres qui seront affichées dans un environnement (offres éligibles). L&#39;arbitrage classe les offres par priorité en fonction des critères définis dans les catégories, offres et offres contextuelles.
* Une **interaction sortante** appelle le moteur d&#39;interaction à partir d&#39;une liste de contacts (utilisée pour la diffusion d&#39;emails, de courrier, etc.). Les mêmes règles et processus sont appliqués à chaque contact. Ce type d’interaction est généralement traité en mode batch.
* Le **mode batch** permet de sélectionner la meilleure offre pour un ensemble de contacts. Les règles d’éligibilité/priorisation sont appliquées à tous les contacts de l’ensemble. Ce mode est généralement utilisé pour les interactions sortantes.
* Le **mode unitaire** permet de traiter un seul contact à la fois. Ce mode est généralement utilisé pour les messages transactionnels.
* **Les** offres éligibles sont des offres répondant à des contraintes définies en amont qui peuvent être proposées de manière cohérente à une cible.
* **Les** règles de présentation sont des règles de typologie référencées dans l&#39;environnement des offres, qui permettent d&#39;exclure certaines offres en prenant en compte l&#39;historique des propositions.
* **** Formules de poids permettant de calculer précisément la pertinence d&#39;une offre, afin de sélectionner l&#39;offre la plus pertinente. Les poids sont définis dans les offres. Les offres éligibles sont prises en compte dans l&#39;ordre décroissant de poids.
* **La** fonction de rendu est définie au niveau de l&#39;emplacement afin de construire sa représentation des offres en fonction des attributs définis dans l&#39;offre. Il existe trois modes de fonctions de rendu différents : HTML, XML et texte.
* **La** proposition d&#39;offre est le résultat de l&#39;action consistant à présenter une ou plusieurs offres à un contact dans un emplacement donné (bannière sur un site web, email ou SMS, par exemple). Ce résultat est stocké dans la table des propositions d&#39;offre. Toutefois, il n&#39;est pas obligatoire d&#39;enregistrer les propositions.
* **** La simulation est un module qui permet de tester la présentation des offres auprès des destinataires ciblés avant d&#39;envoyer réellement les offres.
* La section **Aperçu** de l’offre affiche l’offre telle qu’elle est affichée dans son dossier. Il est accessible à partir de la fenêtre de paramétrage des offres ou du profil du contact.
* **Les** filtres prédéfinis sont des règles de filtrage qui peuvent prendre en compte les paramètres des offres (par exemple, un code d&#39;offre). Elles peuvent être réutilisées après la création des offres.
* Une **Représentation d’offre** est une information utilisée par le canal pour afficher l’offre. La représentation d&#39;une offre peut être construite à partir de la fonction de rendu de l&#39;emplacement sur lequel l&#39;offre est représentée ou saisie directement dans l&#39;interface (par exemple, dans le bloc HTML). Une offre peut être représentée par un emplacement.

