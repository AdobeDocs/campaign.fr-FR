---
product: Adobe Campaign
title: Interaction de Campaign - Gestion des offres
description: Prise en main de la gestion des offres
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 100%

---

# Interaction et la gestion des offres{#interaction-and-offer-management}

Campaign comprend un module **Interaction** qui permet de répondre en temps réel lors d&#39;une interaction avec un contact donné (un client ou une cible) en proposant une ou plusieurs offres adaptées. Il peut s&#39;agir par exemple de messages de communication simples, d&#39;offres spéciales sur un ou plusieurs produits ou d&#39;un service.

Vous pouvez créer un catalogue d&#39;offres qui s&#39;interface avec vos canaux sortants (e-mail, courrier, SMS) pour sélectionner la meilleure offre à envoyer à un contact dans un contexte donné. La meilleure sélection d&#39;offres pour un destinataire est basée sur des **règles d&#39;éligibilité**. La sélection d&#39;une offre à partir d&#39;un ensemble d&#39;offres pertinentes est déterminée à l&#39;aide de règles de priorité. Les règles de présentation des offres prennent en compte l&#39;historique du contact et évitent de lui envoyer plusieurs fois la même offre.

Interaction vous permet de créer et de gérer un catalogue d&#39;offres, et de paramétrer les règles d&#39;éligibilité et les thèmes d&#39;application qui leur sont associés. Vous pouvez personnaliser le contenu de votre offre selon le canal choisi à l&#39;aide de différentes représentations. Enfin, pour déterminer l&#39;impact d&#39;une présentation d&#39;offres, vous pouvez utiliser le module de simulation mis à votre disposition.

## Prise en main des offres

Les étapes clés pour commencer sont répertoriées ci-dessous.

### Configuration de votre plateforme

Avant de commencer, en tant qu&#39;**administrateur** de Campaign, assurez-vous d&#39;avoir effectué les tâches suivantes dans les environnements en édition :

1. Création de profils utilisateur. [En savoir plus](interaction-operators.md)
1. (Facultatif) Création d&#39;un environnement d&#39;offres pour chaque dimension de ciblage. [En savoir plus](interaction-env.md)
1. Création de règles de typologie pour chaque environnement. [En savoir plus](interaction-offer.md#offer-presentation)
1. Création d&#39;emplacements pour chaque environnement et configuration des fonctions de rendu. [En savoir plus](interaction-offer-spaces.md)
Si l&#39;emplacement est défini sur un canal unitaire en mode identifié, il est nécessaire de spécifier les paramètres avancés de l&#39;emplacement.

### Création et publication du catalogue d&#39;offres {#managing-the-offer-catalog-}

En tant que **Chargé d&#39;offres** vous devez effectuer les tâches suivantes :

1. Créer des catégories d&#39;offres dans des environnements en édition. [En savoir plus](interaction-offer-catalog.md#creating-offer-categories)
1. Créer des offres dans des environnements en édition. [En savoir plus](interaction-offer.md)
1. Valider et publier des offres sur un ou plusieurs emplacements afin de les rendre disponibles dans les environnements en ligne pour le Chargé de diffusion. [En savoir plus](interaction-offer.md#approve-offers)

### Exploiter le catalogue d&#39;offres {#using-the-offer-catalog-}

En tant que **Chargé de diffusion**, vous devez effectuer les tâches suivantes :

1. Créer une campagne.
1. Référencer une offre dans la campagne ou la diffusion. [En savoir plus](interaction-send-offers.md).


## Concepts et terminologie

Découvrez les termes spécifiques aux offres et les conseils connexes avant de commencer.

* Les **environnements** incluent un catalogue d&#39;offres et des emplacements (points d&#39;extension). Vous devez créer un environnement par dimension de ciblage.
Il existe deux types d&#39;environnements :

   * **Environnement en édition** : les offres et les règles de typologie sont créées dans l&#39;environnement en édition. Les règles de typologie déterminent les offres à présenter (ou non) à une personne ciblée. La table des personnes qui seront ciblées par les offres et la table de stockage de toutes les propositions d&#39;offres sont également définies dans cet environnement. Le nœud **[!UICONTROL Environnement en édition]** contient des sous-dossiers d&#39;emplacements, des filtres prédéfinis et des catégories d&#39;offres. Pour chaque **[!UICONTROL Environnement en édition]**, il existe un **[!UICONTROL Environnement en ligne]** correspondant, généré à partir de ce même **[!UICONTROL Environnement en édition]**.
   * **Environnement en ligne** : environnement associé à un **[!UICONTROL Environnement en édition]** qui contient des offres en lecture seule dont le contenu et l&#39;éligibilité ont été validés via l&#39;**[!UICONTROL Environnement en édition]**. Ils doivent être sélectionnés pour être présentés et insérés dans un message.

* L&#39;**Emplacement** est une localisation (dossier) définissant l&#39;emplacement d&#39;exposition de l&#39;offre. Lors de la création d&#39;un emplacement, vous pouvez définir le canal, créer le contenu de l&#39;offre à l&#39;aide de fonctions de rendu, définir l&#39;ordre des offres et le mode : mode unitaire et/ou mode batch (par défaut). L&#39;emplacement est l&#39;interface entre le canal et le moteur d&#39;offres.
* Le **Catalogue d&#39;offres** est un ensemble d&#39;offres définies dans Adobe Campaign qui peuvent être sélectionnées lors d&#39;une interaction. Le catalogue est organisé de manière hiérarchique avec chaque nœud correspondant à une catégorie.
* Une **Catégorie** est un dossier lié au catalogue d&#39;offres dans un environnement, qui organise les offres en fonction de la nature, de la date d&#39;éligibilité et du thème de l&#39;application. Une catégorie peut contenir des sous-catégories qui héritent de toutes les caractéristiques de la catégorie parente. Les règles d&#39;éligibilité peuvent être définies pour une catégorie, de façon à les partager avec plusieurs offres.
* **Thèmes d&#39;application** : mots-clés définis au niveau de la catégorie qui permettent de filtrer les offres au moment de leur présentation en restreignant la sélection des offres à une ou deux catégories.
* Les **Règles d&#39;éligibilité** sont des contraintes appliquées à un environnement, une catégorie ou une offre, liées à la période de validité, la cible et le poids. Elles vous permettent de vous assurer qu&#39;une offre est en phase avec le contact ciblé.

   Au niveau des environnements, les règles d&#39;éligibilité comprennent les règles de présentation appliquées aux offres et les personnes à cibler.

   Au niveau des catégories, les règles d&#39;éligibilité permettent de limiter la validité de la catégorie dans le temps, de définir des thèmes d&#39;application et de déterminer les personnes à cibler. Elles peuvent également recevoir un poids multiplicateur pendant une période donnée. Cela permet de mutualiser les règles pour les offres d&#39;une même catégorie et ainsi d&#39;en simplifier la gestion.

   Au niveau des offres, les règles d&#39;éligibilité permettent de limiter la validité des offres dans le temps et de déterminer les personnes à cibler.

* L&#39;**Arbitrage** est l&#39;action de sélectionner des offres qui seront affichées dans un environnement (offres éligibles). L&#39;arbitrage classe les offres par priorité en fonction des critères définis dans les catégories, offres et offres contextuelles.
* Une **Interaction sortante** appelle le moteur d&#39;interaction à partir d&#39;une liste de contacts (utilisée pour la diffusion d&#39;e-mails, de courrier, etc.). Les mêmes règles et processus sont appliqués à chaque contact. Ce type d&#39;interaction est généralement traité en mode batch.
* Le **Mode batch** permet de sélectionner la meilleure offre pour un ensemble de contacts. Les règles d&#39;éligibilité/priorisation sont appliquées à tous les contacts de l&#39;ensemble. Ce mode est généralement utilisé pour les interactions sortantes.
* Le **Mode unitaire** permet de traiter un seul contact à la fois. Ce mode est généralement utilisé pour les messages transactionnels.
* Les **Offres éligibles** sont des offres répondant à des contraintes définies en amont pouvant être proposée de façon cohérente à une cible.
* Les **Règles de présentation** sont des règles de typologie référencées au niveau de l&#39;environnement d&#39;offres permettant d&#39;exclure certaines offres en tenant compte de l&#39;historique des propositions.
* Le **Poids** consiste en des formules de poids permettant de calculer précisément la pertinence d&#39;une offre, afin de sélectionner l&#39;offre la plus pertinente. Les poids sont définis dans les offres. Les offres éligibles sont prises en compte dans l&#39;ordre décroissant de poids.
* La **Fonction de rendu** est définie au niveau de l&#39;emplacement afin de construire sa représentation de l&#39;offre en fonction des attributs définis dans l&#39;offre. Il existe trois modes de fonction de rendu différents : HTML, XML et texte.
* La **Proposition d&#39;offre** est le résultat de l&#39;action consistant à présenter une ou plusieurs offres à un contact dans un emplacement donné (bannière sur un site web, e-mail ou SMS, par exemple). Ce résultat est stocké dans la table des propositions d&#39;offre. Toutefois, il n&#39;est pas obligatoire d&#39;enregistrer les propositions.
* La **Simulation** est un module permettant de tester la présentation d&#39;offres auprès des personnes à cibler avant de procéder à la véritable présentation.
* L&#39;**Aperçu** de l&#39;offre affiche l&#39;offre telle qu&#39;elle est affichée dans son dossier. Il est accessible à partir de la fenêtre de paramétrage des offres ou du profil du contact.
* Les **Filtres prédéfinis** sont des règles de filtrage qui peuvent prendre en compte les paramètres des offres (par exemple, un code d&#39;offre). Ils peuvent être réutilisés après la création des offres.
* Une **Représentation de l&#39;offre** est une information utilisée par le canal pour afficher l&#39;offre. La représentation de l&#39;offre peut être construite à partir de la fonction de rendu de l&#39;emplacement sur lequel l&#39;offre est représentée ou saisie directement dans l&#39;interface (par exemple, dans le bloc HTML). Une offre peut être représentée par un emplacement.

