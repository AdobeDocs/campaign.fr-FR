---
solution: Campaign
product: Adobe Campaign
title: Interaction Campaign - Gestion des Offres
description: Prise en main de la gestion des Offres
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 6f84e739f25caf5dbd2ef964e38a6264e4b4342b
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 15%

---

# Interaction et la gestion des offres{#interaction-and-offer-management}

Campaign est fourni avec un module d&#39;**Interaction** qui vous permet de répondre en temps réel lors d&#39;une interaction avec un contact donné (un client ou une cible) en en faisant une ou plusieurs offres adaptées. Par exemple, il peut s’agir de messages de communication simples, d’offres spéciales sur un ou plusieurs produits ou d’un service.

Vous pouvez créer un catalogue d&#39;offres qui s&#39;interface avec vos canaux sortants (courriel, courriel direct, SMS) pour sélectionner la meilleure offre à envoyer à un contact dans un contexte donné. La sélection des meilleures offres pour un destinataire est basée sur **règles d&#39;éligibilité**. Le choix d&#39;une offre parmi un ensemble d&#39;offres pertinentes est déterminé à l&#39;aide de règles de priorité. Les règles de présentation d&#39;Offre tiennent compte de l&#39;historique du contact et évitent de lui faire parvenir plusieurs fois la même offre.

Interaction vous permet de créer et gérer un catalogue d’offres, et de paramétrer les règles d’éligibilité et les thèmes d’application qui leur sont associés. Vous pouvez personnaliser le contenu de votre offre selon le canal choisi à l’aide de différentes représentations. Enfin, pour déterminer l’impact d’une présentation d’offres, vous pouvez utiliser le module de simulation mis à votre disposition.

## Concepts et terminologie

Découvrez les termes spécifiques à une offre et les conseils connexes avant de commencer.

* **Les** environnements incluent un catalogue d&#39;offres et des emplacements (crochets). Vous devez créer un environnement par dimension de ciblage.
Il existe deux types d’environnements :

   * **Environnement** de conception : Les offres sont créées dans l’environnement de conception, ainsi que dans les règles de typologie. Les règles de typologie déterminent les offres à présenter (ou non) à une personne ciblée. La table des personnes qui seront ciblées par les offres et la table pour le stockage de toutes les Propositions d&#39;offre sont également définies dans cet environnement. Le noeud **[!UICONTROL environnement de conception]** contient des sous-dossiers d’emplacement, des filtres prédéfinis et des catégories d’offre. Pour chaque **[!UICONTROL environnement de conception]**, il existe un **[!UICONTROL environnement dynamique]** en lecture seule correspondant, généré à partir de cet **[!UICONTROL environnement de conception]**.
   * **Environnement** en direct : environnement lié à un  **[!UICONTROL environnement de]** conception qui contient des offres en lecture seule dont le contenu et l’éligibilité ont été approuvés via l’environnement **[!UICONTROL de]** conception. Ils doivent être sélectionnés pour être présentés dans un message.

* L&#39;**Emplacement** est un emplacement (dossier) définissant l&#39;emplacement où l&#39;offre est exposée. Lors de la création d’un emplacement, vous pouvez spécifier le canal, créer le contenu de l’offre à l’aide des fonctions de rendu, spécifier l’ordre des offres et son mode : mode unitaire et/ou mode batch (par défaut). L&#39;emplacement est l&#39;interface entre le canal et le moteur d&#39;offre.
* Le **Catalogue d&#39;offres** est un ensemble d&#39;offres définies dans Adobe Campaign qui peuvent être sélectionnées au cours d&#39;une interaction. Le catalogue est organisé de manière hiérarchique avec chaque noeud correspondant à une catégorie.
* Une **Catégorie** est un dossier lié au catalogue d&#39;offres dans un environnement, qui organise les offres en fonction de la nature, de la date d&#39;éligibilité et du thème de l&#39;application. Une catégorie peut contenir des sous-catégories, qui héritent de toutes les caractéristiques de la catégorie parent. Les règles d&#39;éligibilité peuvent être définies pour une catégorie de manière à les partager pour plusieurs offres.
* **Les** thèmes d&#39;application sont des mots-clés définis dans la catégorie, ce qui vous permet de filtrer les offres lorsqu&#39;elles sont présentées en limitant la sélection des offres à une ou deux catégories.
* **Les** règles d&#39;éligibilité sont des contraintes appliquées à un environnement, une catégorie ou une offre, liées à la période de validité, à la cible et au poids. Ils vous permettent de vous assurer qu’une offre est conforme au contact ciblé.

   Au niveau des environnements, les règles d&#39;éligibilité comprennent les règles de présentation appliquées aux offres et les personnes à cibler.

   Au niveau des catégories, les règles d&#39;éligibilité permettent de limiter la validité de la catégorie dans le temps, de définir des thèmes d&#39;application et de déterminer les personnes à cibler. Elles peuvent également recevoir un poids multiplicateur pendant une période donnée. Cela permet de mutualiser les règles pour les offres d&#39;une même catégorie et ainsi d&#39;en simplifier la gestion.

   Au niveau des offres, les règles d&#39;éligibilité permettent de limiter la validité des offres dans le temps et de déterminer les personnes à cibler.

* L&#39;**Arbitrage** est l&#39;action de sélection des offres qui seront affichées sur un environnement (offres admissibles). L&#39;arbitrage classe les offres par priorité en fonction des critères définis dans les catégories, les offres et les offres contextuelles.
* Une **interaction sortante** appelle le moteur d&#39;interaction à partir d&#39;une liste de contact (utilisée pour la remise de courriels, de publipostage, etc.). Les mêmes règles et processus sont appliqués à chaque contact. Ce type d’interaction est généralement traité en mode batch.
* Le **mode de traitement par lots** vous permet de sélectionner la meilleure offre pour un ensemble de contacts. Les règles d’éligibilité/de hiérarchisation sont appliquées à tous les contacts de l’ensemble. Ce mode est généralement utilisé pour les interactions sortantes.
* Le **mode unitaire** vous permet de traiter un seul contact à la fois. Ce mode est généralement utilisé pour les messages transactionnels.
* **Les** offres admissibles sont des offres qui répondent aux contraintes définies en amont et qui peuvent être proposées de manière cohérente à une cible.
* **Les** règles de présentation sont des règles de typologie référencées dans l’environnement d’offre, ce qui vous permet d’exclure certaines offres en prenant en compte l’historique des propositions.
* **Les formules** Weightare qui vous permettent de calculer précisément la pertinence d&#39;une offre, afin de sélectionner l&#39;offre la plus pertinente. Les poids sont définis dans les offres. Les offres admissibles sont prises en compte dans l&#39;ordre décroissant des poids.
* **La** fonction de rendu est définie dans l’emplacement afin de construire son rendu de l&#39;offre en fonction des attributs définis dans l’offre. Il existe trois modes de fonction de rendu différents : HTML, XML et texte.
* **La** proposition d&#39;Offre est le résultat de l&#39;action qui consiste à présenter une ou plusieurs offres à un contact dans un espace donné (bannière sur un site Web, courriel ou SMS, par exemple). Ce résultat est stocké dans la table Propositions d&#39;offre. Cependant, il n&#39;est pas obligatoire de sauvegarder les propositions.
* **** Simulationest un module qui vous permet de tester la présentation des offres sur les destinataires ciblés avant d&#39;envoyer les offres.
* La **Prévisualisation** de l’offre affiche l’offre telle qu’elle est affichée dans son dossier. Il est accessible à partir de la fenêtre des paramètres de l&#39;offre ou du profil de contact.
* **Les** filtres prédéfinis que les règles de filtrage peuvent prendre en compte les paramètres d’offre (par exemple, un code d’offre). Ils peuvent être réutilisés une fois les offres créées.
* Un **Rendu de l&#39;offre** est une information utilisée par le canal pour afficher l&#39;offre. Le rendu de l&#39;offre peut être construit à partir de la fonction de rendu de l&#39;espace sur lequel l&#39;offre est représentée ou directement entrée dans l&#39;interface (par exemple, dans le bloc HTML). Une offre peut être représentée par un espace.

## Commencer avec les offres

Les étapes clés du début sont énumérées ci-dessous.

### Configuration de votre plateforme

Avant de commencer, en tant qu&#39;administrateur **Campaign**, vérifiez que vous avez effectué les tâches suivantes dans les environnements de conception :

1. Créez des profils d’utilisateur. [En savoir plus](interaction-operators.md).
1. (facultatif) Créez un environnement d’offre pour chaque dimension de ciblage. [En savoir plus](interaction-env.md)
1. Créez des règles de typologie pour chaque environnement. [En savoir plus](interaction-offer.md#offer-presentation).
1. Créez des emplacements pour chaque environnement et configurez les fonctions de rendu. [En savoir plus](interaction-offer-spaces.md).
Si l&#39;emplacement est défini sur un canal unitaire en mode identifié, il est nécessaire de spécifier les paramètres avancés de l&#39;emplacement.

### Créer et publier le catalogue d&#39;offres {#managing-the-offer-catalog-}

En tant que **gestionnaire d’Offres**, vous devez exécuter les tâches suivantes :

1. Créez des catégories d’offre dans les environnements de conception. [En savoir plus](interaction-offer-catalog.md#creating-offer-categories).
1. Créez des offres dans les environnements de conception. [En savoir plus](interaction-offer.md).
1. Approuvez et publiez des offres sur un ou plusieurs espaces afin de les rendre disponibles sur des environnements en direct pour le gestionnaire de diffusions. [En savoir plus](interaction-offer.md#approve-offers).

### Exploitation du catalogue d&#39;offres {#using-the-offer-catalog-}

En tant que **gestionnaire de Diffusions**, vous devez exécuter les tâches suivantes :

1. Créez une campagne.
1. Référencez une offre dans la campagne ou la diffusion. [En savoir plus](interaction-send-offers.md).

