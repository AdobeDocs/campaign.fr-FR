---
title: Interaction de Campaign - Gestion des offres
description: Prise en main de la gestion des offres
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
TQID: https://experienceleague.adobe.com/VpyoAhpD-da4BUAXLJyUyaJBPMqoQ-PHNcZToe3QBlc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 1639
ht-degree: 74%

---

# Gestion des interactions en temps réel

Campaign comprend un module **Interaction** qui permet de répondre en temps réel lors d’une interaction avec un contact donné en lui proposant une ou plusieurs offres adaptées. Il peut s’agir par exemple de messages de communication simples, d’offres spéciales sur un ou plusieurs produits ou d’un service.

Vous pouvez créer un catalogue d’offres qui s’interface avec vos canaux sortants (e-mail, courrier, SMS) pour sélectionner la meilleure offre à envoyer à un contact dans un contexte donné. La meilleure sélection d&#39;offres pour un destinataire est basée sur des **règles d&#39;éligibilité**. La sélection d&#39;une offre à partir d&#39;un ensemble d&#39;offres pertinentes est déterminée à l&#39;aide de règles de priorité. Les règles de présentation des offres prennent en compte l’historique du contact et évitent de lui envoyer plusieurs fois la même offre.

Interaction vous permet de créer et de gérer un catalogue d&#39;offres, et de paramétrer les règles d&#39;éligibilité et les thèmes d&#39;application qui leur sont associés. Selon le canal choisi, le contenu de l&#39;offre peut être personnalisé grâce à différentes fonctions de rendu. Enfin, vous pouvez utiliser le module de simulation pour calculer l&#39;impact d&#39;une présentation d&#39;offres.

![](assets/interaction-cycle.png)

Tout d’abord, un contact se produit entre un client et une entreprise par le biais d’un canal de communication : il peut s’agir d’un site web (interaction sortante), d’un e-mail, d’un SMS, d’une notification push (interactions entrantes). [En savoir plus](#interaction-types)

Ce contact génère un appel au moteur d’offres. (1)

Lorsque l’appel au moteur d’offres se produit, une ou plusieurs offres sont sélectionnées dans le catalogue d’offres en fonction du nombre de paramètres d’offres sur la proposition. (2)

Ensuite, les règles d’éligibilité sont appliquées : les meilleures offres sont sélectionnées en fonction des règles d’éligibilité, des dates de début et de fin des offres, des données de profil et du comportement en temps réel du client ou de la cliente. (3)

L’historique des propositions de profil est mis à jour une fois la sélection effectuée afin d’éviter la duplication des offres présentées. (4)

Enfin, la meilleure offre est proposée à la cible. (5)

## Prise en main des offres

Les étapes clés pour commencer sont répertoriées ci-dessous.

### Configuration de votre plateforme

Avant de commencer, en tant qu&#39;**administrateur** de Campaign, assurez-vous d&#39;avoir effectué les tâches suivantes dans les environnements en édition :

1. Création de profils utilisateur. [En savoir plus](interaction-operators.md)
1. (Facultatif) Création d&#39;un environnement d&#39;offres pour chaque dimension de ciblage. [En savoir plus](interaction-env.md)
1. Création de règles de typologie pour chaque environnement. [En savoir plus](interaction-offer.md#offer-presentation)
1. Création d&#39;emplacements pour chaque environnement et configuration des fonctions de rendu. [En savoir plus](interaction-offer-spaces.md)
Si l&#39;emplacement est défini sur un canal unitaire en mode identifié, il est nécessaire de préciser les paramètres avancés de l&#39;emplacement.

   >[!NOTE]
   >
   >Si l&#39;emplacement est défini sur un canal unitaire en mode identifié, il est nécessaire de spécifier les paramètres avancés de l&#39;emplacement.

1. Paramétrez le moteur d’offres pour les interactions entrantes, afin de proposer et mettre à jour une ou plusieurs offres.

   Les différents modes d’intégration sont décrits dans [cette section](interaction-present-offers.md).

   >[!NOTE]
   >
   >Lorsqu’un emplacement est créé sur le canal web entrant, vous devez configurer le site web pour afficher cette offre.
   >

### Créer et publier le catalogue d’offres {#managing-the-offer-catalog-}

En tant que **Chargé(e) d’offres**, vous devez :

1. Créer des catégories d’offres dans des environnements en édition. [En savoir plus](interaction-offer-catalog.md#creating-offer-categories)
1. Créer des offres dans des environnements en édition. [En savoir plus](interaction-offer.md)
1. Valider et publier des offres sur un ou plusieurs emplacements afin de les rendre disponibles dans les environnements en ligne pour le chargé/la chargée de diffusion. [En savoir plus](interaction-offer.md#approve-offers)

### Utiliser le catalogue d’offres {#using-the-offer-catalog-}

En tant que **Chargé(e) de diffusion**, vous devez :

1. Créez une campagne.
1. Référencer une offre dans la campagne ou la diffusion. [En savoir plus](interaction-send-offers.md).

## Glossaire

Découvrez les termes spécifiques aux offres et les conseils connexes avant de commencer.

* **Environnement** : ensemble comprenant un catalogue d&#39;offres et des points d&#39;extension (emplacements). Créer un environnement par dimension de ciblage. Il existe deux types d’environnements :

   * **Environnement en édition** : environnement dans lequel les offres sont créées et/ou les règles de typologie sont définies (règles qui déterminent les offres à présenter ou non à une personne ciblée). Le tableau des personnes à cibler par les offres et la table de stockage de toutes les propositions d’offres sont également définis dans cet environnement. Le nœud **[!UICONTROL Environnement en édition]** contient des sous-dossiers d&#39;’mplacements, des filtres prédéfinis et des catégories d’offres. Pour chaque **[!UICONTROL Environnement en édition]**, il existe un **[!UICONTROL Environnement en ligne]** correspondant, généré à partir de ce même **[!UICONTROL Environnement en édition]**.
   * **Environnement en ligne** : environnement associé à un **[!UICONTROL Environnement en édition]**. Il contient des offres en lecture seule dont le contenu et l’éligibilité ont été approuvés via l’**[!UICONTROL Environnement en édition]**. Ils peuvent être affichés sur un site web ou insérés dans un message.

* Un **emplacement** désigne un dossier définissant l’emplacement d’exposition de l’offre. Lors de la définition d’un emplacement, vous pouvez :
   * sélectionner le canal
   * choisir d’utiliser le mode unitaire (ou par défaut, uniquement en mode Lot)
   * créer le contenu de l’offre à l’aide de fonctions de rendu
   * indiquer les offres à présenter

  Un emplacement est une interface entre le canal et le moteur d’offres.

  >[!CAUTION]
  >
  >Un emplacement n&#39;est pas un canal de communication, il correspond à un lieu d&#39;exposition spécifique sur le canal. Par exemple, les offres exposées sur un site web peuvent occuper deux emplacements sur la même page. Dans ce cas, vous avez deux espaces pour le même canal.
  >
  >Les emplacements doivent être définis dans le cahier des charges et ne doivent pas être modifiés en cours de projet.

* **Catalogue d&#39;offres** : ensemble des offres définies dans Adobe Campaign pouvant être sélectionnées lors d&#39;une interaction. Le catalogue est organisé de manière hiérarchique avec chaque nœud correspondant à une catégorie.
* **Catégorie** : dossier lié au catalogue d&#39;offres dans un environnement, qui organise les offres en fonction de la nature, de la date d&#39;éligibilité et du thème de l&#39;application. Une catégorie peut contenir des sous-catégories qui héritent de toutes les caractéristiques de la catégorie parente. Les règles d&#39;éligibilité peuvent être définies pour une catégorie, de manière à les partager avec plusieurs offres.
* **Thèmes d&#39;application** : mots-clés définis au niveau de la catégorie qui permettent de filtrer les offres au moment de leur présentation sur un canal sortant ou entrant en restreignant la sélection des offres à une ou plusieurs catégorie(s).

  >[!NOTE]
  >
  >Les catégories enfants héritent des thèmes définis au niveau de la catégorie parent.

* **Règles d&#39;éligibilité** : contraintes appliquées à un environnement, à une catégorie ou à une offre, portant sur la période de validité, la cible et le poids. Elles permettent de s’assurer qu’une offre est en phase avec le contact ciblé.

  Au niveau des environnements, les règles d&#39;éligibilité comprennent les règles de présentation appliquées aux offres et les personnes à cibler.

  Dans les catégories, les règles d’éligibilité permettent aux opérateurs de limiter la validité de la catégorie dans le temps, de définir des thèmes d’application et de déterminer les personnes à cibler. Elles peuvent également définir un poids multiplicateur pour une période donnée. Ainsi, les opérateurs peuvent partager les règles relatives aux offres d’autres catégories et ainsi simplifier leur gestion.

  Au niveau des offres, les règles d&#39;éligibilité permettent de limiter la validité des offres dans le temps et de déterminer les personnes à cibler.

* **Arbitrage** : sélection des offres à afficher dans un environnement donné (offres éligibles). Le principe de l’arbitrage permet de classer les offres par priorité en fonction des critères définis dans les catégories, les offres et les offres contextuelles.
* **Contact** : contact provenant d’une interaction entrante. Lors du traitement des appels au moteur, le contact est associé à une dimension de ciblage. Il existe deux types de contacts :

   * **[!UICONTROL Contact identifié]** : contact s’étant volontairement identifié sur le canal. Dans les interactions sortantes, le contact est automatiquement identifié.
   * **[!UICONTROL Contact anonyme]** : contact qui ne s’est pas volontairement inscrit sur le canal mais qui peut être identifié implicitement au moyen d’un cookie. Cette terminologie n’est utilisée que pour les interactions entrantes.

     >[!NOTE]
     >
     >Les contacts anonymes non identifiés sont rattachés à la dimension de ciblage des visiteurs.

* **Interaction sortante** : appel vers le moteur dʼoffres à partir dʼune liste de contacts (utilisée pour la diffusion dʼe-mails, de publipostage direct, etc.). Les mêmes règles et processus sont appliqués à chaque contact. Ce type d’interaction est généralement traité en mode Lot.
* **Interaction entrante** : interaction faisant suite à un appel entrant généré par l’action d’un contact sur le canal. Ce type d’interaction est généralement traité en mode unitaire.
* **Mode Lot** : le mode Lot permet de sélectionner la meilleure offre pour un ensemble de contacts. Les règles d’éligibilité/hiérarchisation sont appliquées à tous les contacts de l’ensemble. Ce mode est généralement utilisé pour les interactions sortantes.
* **Mode unitaire** : un seul contact est traité à la fois. Ce mode est généralement utilisé pour les interactions entrantes et les messages transactionnels.
* Le **Mode d’identification** fait référence au statut d’un contact :

   * **[!UICONTROL Explicite]** : les contacts sont identifiés par leur connexion à l’interface du canal.
   * **[!UICONTROL Implicite]** : les contacts sont identifiés par un cookie (permanent ou de session). Ils peuvent être traités comme des contacts anonymes ou identifiés.
   * **[!UICONTROL Anonyme]** : les contacts ne peuvent pas être identifiés.

* **Offre éligible** : offre répondant à des contraintes définies en amont pouvant être proposée de façon cohérente à une cible.
* **Règles de présentation** : règles de typologie référencées au niveau de l&#39;environnement d&#39;offres permettant d&#39;exclure certaines offres en tenant compte de l&#39;historique des propositions.
* **Poids** : il s’agit de formules permettant de calculer de manière précise la pertinence d’une offre, afin de sélectionner l’offre la plus pertinente. Les poids sont définis dans les offres. Les offres éligibles sont prises en compte dans l’ordre de poids décroissant.
* **Fonction de rendu** : il s’agit d’une fonction définie au niveau de l’emplacement d’offre afin de construire son rendu de l’offre en fonction des attributs définis dans l’offre. Il existe trois modes de fonction de rendu différents : HTML, XML et texte.
* **Proposition d&#39;offre** : résultat de l&#39;action qui consiste à présenter une ou plusieurs offres à un contact sur un emplacement donné (une bannière sur un site web, un email ou un SMS par exemple). Ce résultat est stocké dans la table des propositions d&#39;offre. Toutefois, il n’est pas obligatoire d’enregistrer les propositions.
* **Simulation** : module permettant de tester la présentation d&#39;offres auprès des personnes à cibler avant de procéder à la véritable présentation.
* **Aperçu** : aperçu de l&#39;offre telle qu&#39;elle est affichée dans son dossier. Il est accessible à partir de la fenêtre de paramétrage des offres ou du profil du contact.
* **filtres prédéfinis** : règles de filtrage prédéfinis pouvant prendre en compte des paramètres d&#39;une offre (par exemple le code de l&#39;offre). Ils peuvent être réutilisés après la création des offres.
* **Représentation de l’offre** : informations utilisées par le canal pour afficher l’offre. La représentation de l’offre peut être construite à partir de la fonction de rendu de l’emplacement sur lequel l’offre est représentée ou saisie directement dans l’interface (par exemple, dans le bloc HTML). Une offre peut être représentée par un emplacement.
* **Processus de basculement** : processus activé dans un environnement identifié, chargé de diriger l&#39;appel vers un environnement anonyme si le contact n&#39;a pas pu être identifié explicitement et/ou implicitement.
