---
product: Adobe Campaign
title: Utilisation de Campaign et Adobe Target
description: Découvrez comment utiliser Campaign et Adobe Target
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 91%

---

# Utilisation de Campaign et Adobe Target

Connectez Campaign et Target pour inclure une offre provenant d’Adobe Target dans une diffusion e-mail Adobe Campaign.

Cette intégration vous aide à mettre en oeuvre les cas d’utilisation comme suit : lorsqu&#39;un destinataire ouvre un email envoyé via Adobe Campaign, un appel à Adobe Target permet d&#39;afficher une version dynamique du contenu. Cette version dynamique est calculée en fonction des règles définies en amont, lors de la création de l’e-mail.

>[!NOTE]
>L&#39;intégration prend uniquement en charge les images statiques. Les autres types de contenu ne peuvent pas être personnalisés.

[!DNL :speech_balloon:] En tant qu’utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour implémenter des triggers Experience Cloud avec Campaign.

Adobe Target peut utiliser les types de données suivants :

* Données de la base de données Adobe Campaign
* Segments liés à l’identifiant visiteur dans Adobe Target uniquement si les données utilisées ne sont pas soumises à des restrictions légales
* données d&#39;Adobe Target : user agent, adresse IP, données de géolocalisation.

## Insertion d’un contenu dynamique

Dans l’exemple ci-dessous, vous allez apprendre à intégrer **une offre dynamique** d’Adobe Target dans un email Adobe Campaign.

Nous souhaitons créer un message contenant une image qui change dynamiquement en fonction du pays du destinataire. Les données sont envoyées avec chaque demande de mbox et dépendent de l’adresse IP du visiteur.

Dans cet email, nous souhaitons que les images changent dynamiquement en fonction des expériences utilisateur suivantes :

* L’email est ouvert en France.
* L’email est ouvert aux États-Unis.
* Si aucune de ces conditions n’est remplie, une image par défaut s’affiche.

![](assets/target_4.png)

Les étapes suivantes doivent être complétées dans Adobe Campaign et Adobe Target :

1. [Insertion de l’offre dynamique dans un e-mail](#inserting-dynamic-offer)
1. [Création d’offres de redirection](#create-redirect-offers)
1. [Création d’audiences](#audiences-target)
1. [Création d’une activité de ciblage d’expérience](#creating-targeting-activity)
1. [Prévisualisation et envoi du message](#preview-send-email)

### Insertion de l’offre dynamique dans un e-mail {#inserting-dynamic-offer}

Dans Adobe Campaign, définissez la cible et le contenu de votre e-mail. Vous pouvez insérer une image dynamique à partir d’Adobe Target.

Pour ce faire, spécifiez l’URL de l’image par défaut, le nom de l’emplacement et les champs que vous souhaitez transférer à Adobe Target.

Dans Adobe Campaign, vous pouvez insérer une image dynamique de Target dans un email de deux manières différentes :

* Si vous utilisez l’éditeur Digital Content Editor, choisissez une image existante, puis sélectionnez **[!UICONTROL Insérer]** > **[!UICONTROL Image dynamique servie par Adobe Target]** depuis la barre d’outils.

   ![](assets/target_5.png)

* Si vous utilisez l’éditeur standard, placez le curseur à l’endroit où vous souhaitez insérer l’image et sélectionnez **[!UICONTROL Inclure]** > **[!UICONTROL Image dynamique servie par Adobe Target...]** dans le menu déroulant de personnalisation.

   ![](assets/target_12.png)

Vous pouvez ensuite définir les paramètres de l’image :

* L’URL de l’**[!UICONTROL image par défaut]** correspond à l’image affichée lorsqu’aucune des conditions n’est remplie. Vous pouvez également sélectionner une image dans votre bibliothèque de ressources.
* L’**[!UICONTROL emplacement de la cible]** correspond au nom de l’emplacement de votre offre dynamique. Vous devrez sélectionner cet emplacement dans votre activité Adobe Target.
* La **[!UICONTROL Landing Page]** vous permet de rediriger l’image par défaut vers une landing page par défaut. Cette URL s’applique uniquement lorsque l’image par défaut est affichée dans l’e-mail final. Elle est facultative.
* Les **[!UICONTROL Paramètres de décision additionnels]** définissent le mappage entre les champs définis dans les segments d’Adobe Target et les champs d’Adobe Campaign. Les champs d’Adobe Campaign utilisés doivent avoir été spécifiés au niveau du « rawbox ». Dans notre exemple, nous avons ajouté le champ Pays.

Si vous utilisez les permissions d’Enterprise pour les paramètres d’Adobe Target, ajoutez la propriété correspondante dans ce champ. Pour en savoir plus sur les permissions de Target Enterprise, voir [cette page](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=fr#administer).

![](assets/target_13.png)

### Création d’offres de redirection {#create-redirect-offers}

Dans Adobe Target, vous pouvez créer différentes versions de votre offre. Selon chaque expérience utilisateur, vous pouvez créer une offre de redirection et spécifier l&#39;image qui sera affichée.

Dans notre cas, nous avons besoin de deux offres de redirection, la troisième (celle par défaut) étant définie dans Adobe Campaign.

1. Pour créer une offre de redirection dans Target Standard, cliquez sur **[!UICONTROL Offres (code)]** dans l’onglet **[!UICONTROL Contenu]**.

1. Cliquez sur **[!UICONTROL Créer]**, puis sur **[!UICONTROL Offre de redirection]**.

   ![](assets/target_9.png)

1. Saisissez le nom de votre offre et l’URL de votre image.

   ![](assets/target_6.png)

1. Suivez la même procédure pour l’offre de redirection restante. Voir à ce propos [cette page](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=fr#experiences).

### Création d’audiences {#audiences-target}

Dans Adobe Target, vous devez créer les deux audiences dans lesquelles les visiteurs de votre offre seront classés selon les différents contenus à diffuser. Pour chaque audience, ajoutez une règle pour définir qui pourra visualiser l’offre.

1. Pour créer une audience avec Target, dans l’onglet **[!UICONTROL Audiences]**, cliquez sur **[!UICONTROL Créer une audience]**.

   ![](assets/audiences_1.png)

1. Ajoutez un nom à l’audience.

   ![](assets/audiences_2.png)

1. Cliquez sur **[!UICONTROL Ajouter une règle]** et sélectionnez une catégorie. La règle utilise des critères spécifiques pour cibler les visiteurs. Vous pouvez affiner les règles en ajoutant des conditions ou en créant des règles dans d’autres catégories.

1. Suivez la même procédure pour les audiences restantes.

### Création d’une activité de ciblage d’expérience {#creating-targeting-activity}

Dans Adobe Target, il est nécessaire de créer une activité de ciblage d’expérience, définir les différentes expériences et les associer aux offres correspondantes.

Vous devez d’abord définir l’audience :

1. Pour créer une activité de ciblage d’expérience, dans l’onglet **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer une activité]**, puis sur **[!UICONTROL Ciblage d’expérience]**.

   ![](assets/target_10.png)

1. Sélectionnez **[!UICONTROL Formulaire]** comme **[!UICONTROL compositeur d’expérience]**.

1. Choisissez une audience en cliquant sur le bouton **[!UICONTROL Changer l’audience]**.

   ![](assets/target_10_2.png)

1. Sélectionnez l’audience créée aux étapes précédentes.

   ![](assets/target_10_3.png)

1. Créez une autre expérience en cliquant sur **[!UICONTROL Ajouter le ciblage d’expérience]**.

Ensuite, ajoutez un contenu pour chaque audience :

1. Sélectionnez le nom de l’emplacement choisi lors de l’insertion de l’offre dynamique dans Adobe Campaign.

   ![](assets/target_15.png)

1. Cliquez sur le bouton de liste déroulante et sélectionnez **[!UICONTROL Modifier l’offre de redirection]**.

   ![](assets/target_content.png)

1. Sélectionnez l’offre de redirection précédemment créée.

   ![](assets/target_content_2.png)

1. Suivez la même procédure pour la deuxième expérience.

La fenêtre **[!UICONTROL Target]** résume votre activité. Au besoin, vous pouvez ajouter d’autres expériences.

![](assets/target_experience.png)

La fenêtre **[!UICONTROL Objectif et paramètres]** permet de personnaliser votre activité en définissant une priorité, un objectif ou une durée.

La section **[!UICONTROL Paramètres de création de rapports]** permet de sélectionner une action et d’éditer les paramètres qui déterminent à quel moment votre objectif est atteint.

![](assets/target_experience_2.png)

## Prévisualisation et envoi du message {#preview-send-email}

Dans Adobe Campaign, vous pouvez désormais prévisualiser votre e-mail et en tester le rendu pour différents destinataires.

Vous pouvez constater que l’image change selon les différentes expériences créées.

Votre e-mail comprenant une offre dynamique provenant de Target peut maintenant être envoyé.

![](assets/target_20.png)
