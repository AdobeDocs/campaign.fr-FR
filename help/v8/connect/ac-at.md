---
solution: Campaign Classic
product: campaign
title: Travailler avec Campaign et Adobe Target
description: Découvrez comment travailler avec Campaign et Adobe Target
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 57%

---

# Travailler avec Campaign et Adobe Target

Connectez Campaign et la Cible pour inclure une offre de Adobe Target dans une diffusion de messagerie Adobe Campaign.

Cette intégration vous aide à mettre en oeuvre les cas d’utilisation comme suit : lorsqu’un destinataire ouvre un courrier électronique envoyé via Adobe Campaign, un appel à Adobe Target vous permet d’afficher une version dynamique du contenu. Cette version dynamique est calculée en fonction des règles définies en amont lors de la création de l&#39;email.

>[!NOTE]
>L&#39;intégration supporte uniquement les images statiques. Le reste du contenu n&#39;est pas personnalisable.

:speak_bulon: En tant qu’utilisateur Cloud Services géré, [contactez l’Adobe](../start/support.md#support) pour mettre en oeuvre des déclencheurs Experience Cloud avec Campaign.

Les types de données suivants peuvent être utilisés par Adobe Target :

* données provenant du datamart Adobe Campaign ;
* segments associés à l&#39;identifiant visiteur dans Adobe Target, si les données utilisées ne sont pas soumises à des limitations légales ;
* données d&#39;Adobe Target : user agent, adresse IP, données de géolocalisation.

## Insertion d’un contenu dynamique

Dans l’exemple ci-dessous, vous apprendrez comment intégrer une offre dynamique de Adobe Target dans un courriel Adobe Campaign.

Nous voulons créer un message avec une image qui changera dynamiquement selon le destinataire. Les données sont envoyées avec chaque demande de mbox et dépendent de l’adresse IP du visiteur.

Dans cet email, nous souhaitons que les images changent dynamiquement en fonction des expériences utilisateur suivantes :

* L’email est ouvert en France.
* L’email est ouvert aux États-Unis.
* Si aucune de ces conditions n’est remplie, une image par défaut s’affiche.

![](assets/target_4.png)

Les étapes suivantes doivent être franchies en Adobe Campaign et en Adobe Target :

1. [Insérer l’offre dynamique dans un courrier électronique](#inserting-dynamic-offer)
1. [Créer des offres de redirection](#create-redirect-offers)
1. [Créer des audiences](#audiences-target)
1. [Création d’une Activité de ciblage d’expérience](#creating-targeting-activity)
1. [Prévisualisation et envoi du message](#preview-send-email)

### Insérez l’offre dynamique dans un courrier électronique {#inserting-dynamic-offer}.

Dans Adobe Campaign, définissez la cible et le contenu de votre courrier électronique. Vous pouvez insérer une image dynamique à partir d’Adobe Target.

Pour ce faire, spécifiez l’URL de l’image par défaut, le nom de l’emplacement et les champs à transférer vers Adobe Target.

Dans Adobe Campaign, vous pouvez insérer une image dynamique de Target dans un email de deux manières différentes :

* Si vous utilisez l’éditeur Digital Content Editor, choisissez une image existante, puis sélectionnez **[!UICONTROL Insérer]** > **[!UICONTROL Image dynamique servie par Adobe Target]** depuis la barre d’outils.

   ![](assets/target_5.png)

* Si vous utilisez l’éditeur standard, placez le curseur à l’endroit où vous souhaitez insérer l’image et sélectionnez **[!UICONTROL Inclure]** > **[!UICONTROL Image dynamique servie par Adobe Target...]** dans le menu déroulant de personnalisation.

   ![](assets/target_12.png)

Vous pouvez ensuite définir les paramètres d’image :

* L&#39;URL de l&#39;**[!UICONTROL image par défaut]** est l&#39;image qui s&#39;affiche lorsqu&#39;aucune des conditions n&#39;est remplie. Vous pouvez également sélectionner une image dans votre bibliothèque Assets.
* L&#39;**[!UICONTROL emplacement de la Cible]** est le nom de l&#39;emplacement de votre offre dynamique. Vous devrez sélectionner cet emplacement dans votre activité Adobe Target.
* Le **[!UICONTROL Landing page]** vous permet de rediriger l’image par défaut vers un landing page par défaut. Cette URL s’applique uniquement lorsque l’image par défaut est affichée dans le message électronique final. Elle est facultative.
* **[!UICONTROL Les paramètres de décision supplémentaires]** définissent le mappage entre les champs définis dans les segments Adobe Target et les champs Adobe Campaign. Les champs d’Adobe Campaign utilisés doivent avoir été spécifiés au niveau du « rawbox ». Dans notre exemple, nous avons ajouté le champ Pays.

Si vous utilisez les permissions d’Enterprise pour les paramètres d’Adobe Target, ajoutez la propriété correspondante dans ce champ. Pour en savoir plus sur les permissions de Target Enterprise, voir [cette page](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=en#administer).

![](assets/target_13.png)

### Créer des offres de redirection {#create-redirect-offers}

En Adobe Target, vous pouvez créer différentes versions de votre offre. Selon chaque expérience utilisateur, vous pouvez créer une offre de redirection et spécifier l&#39;image qui sera affichée.

Dans notre cas, nous avons besoin de deux offres de redirection, la troisième (celle par défaut) étant définie dans Adobe Campaign.

1. Pour créer une offre de redirection dans Target Standard, cliquez sur **[!UICONTROL Offres (code)]** dans l’onglet **[!UICONTROL Contenu]**.

1. Cliquez sur **[!UICONTROL Créer]**, puis sur **[!UICONTROL Offre de redirection]**.

   ![](assets/target_9.png)

1. Saisissez le nom de votre offre et l’URL de votre image.

   ![](assets/target_6.png)

1. Suivez la même procédure pour l’offre de redirection restante. Voir à ce propos [cette page](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=en#experiences).

### Créer des audiences {#audiences-target}

En Adobe Target, vous devez créer les deux audiences dans lesquelles les personnes qui visitent votre offre seront catégorisées pour les différents contenus à diffuser. Pour chaque audience, ajoutez une règle pour définir qui pourra visualiser l’offre.

1. Pour créer une audience avec Target, dans l’onglet **[!UICONTROL Audiences]**, cliquez sur **[!UICONTROL Créer une audience]**.

   ![](assets/audiences_1.png)

1. Ajoutez un nom à l’audience.

   ![](assets/audiences_2.png)

1. Cliquez sur **[!UICONTROL Ajouter une règle]** et sélectionnez une catégorie. La règle utilise des critères spécifiques pour cibler les visiteurs. Vous pouvez affiner les règles en ajoutant des conditions ou en créant des règles dans d’autres catégories.

1. Suivez la même procédure pour les audiences restantes.

### Création d’une Activité de ciblage d’expérience {#creating-targeting-activity}

En Adobe Target, nous devons créer une activité de ciblage d’expérience, définir les différentes expériences et les associer aux offres correspondantes.

Vous devez d’abord définir l’audience :

1. Pour créer une activité de ciblage d’expérience, dans l’onglet **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer une activité]**, puis sur **[!UICONTROL Ciblage d’expérience]**.

   ![](assets/target_10.png)

1. Sélectionnez **[!UICONTROL Formulaire]** comme **[!UICONTROL compositeur d’expérience]**.

1. Choisissez une audience en cliquant sur le bouton **[!UICONTROL Changer l’audience]**.

   ![](assets/target_10_2.png)

1. Sélectionnez l’audience créée aux étapes précédentes.

   ![](assets/target_10_3.png)

1. Créez une autre expérience en cliquant sur **[!UICONTROL Ajouter le ciblage d’expérience]**.

Ajoutez ensuite un contenu pour chaque audience :

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

Dans Adobe Campaign, vous pouvez à présent prévisualiser l&#39;email et tester le rendu pour différents destinataires.

Vous pouvez constater que l&#39;image change selon les différentes expériences créées.

Votre email comprenant une offre dynamique provenant de Target peut maintenant être envoyé.

![](assets/target_20.png)
