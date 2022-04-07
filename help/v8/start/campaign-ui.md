---
title: Découvrir l'espace de travail de Campaign
description: Découvrez comment parcourir et utiliser l’espace de travail de Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: b54a39ee6d106d68446878815c068571e310aaa3
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 32%

---

# Interface utilisateur de Discover Campaign

## Accès à l’interface utilisateur de Campaign

L&#39;espace de travail de Campaign est disponible via la [console cliente](../dev/general-architecture.md).

Découvrez comment installer et configurer la console cliente Campaign dans [cette section](../start/connect.md).

![](assets/home-page.png)

Vous pouvez également utiliser un navigateur web pour accéder à Campaign. Dans ce contexte, seul un sous-ensemble des fonctionnalités de Campaign est disponible. [En savoir plus](#web-browser)

## Parcourir l’interface utilisateur

Une fois connecté à Campaign, vous accédez à la page d&#39;accueil. Parcourez les liens pour accéder aux fonctionnalités. L’ensemble des fonctionnalités disponibles dans l’interface utilisateur dépend de vos options et autorisations.

Depuis la section centrale de la page d&#39;accueil, utilisez les liens pour accéder au matériel d&#39;aide de Campaign, à la communauté et au site web d&#39;assistance.

Utilisez les onglets de la section supérieure pour parcourir les fonctionnalités clés de Campaign :

![](assets/overview-home.png)

>[!NOTE]
>
>La liste des fonctionnalités de base auxquelles vous pouvez accéder dépend de vos autorisations et de votre mise en oeuvre.

Pour chaque fonctionnalité, vous pouvez accéder à l’ensemble des fonctionnalités clés de la **[!UICONTROL Navigation]** . Le **[!UICONTROL Plus]** permet d&#39;accéder à tous les autres composants.

Par exemple, lorsque vous accédez à la variable **[!UICONTROL Profils et cibles]** vous pouvez accéder aux listes de destinataires, services d&#39;abonnement, workflows de ciblage existants, ainsi qu&#39;aux raccourcis pour créer tous ces composants.

![](assets/overview-list.png)

Lorsque vous sélectionnez un élément dans l’écran, il est chargé dans un nouvel onglet afin que vous puissiez facilement parcourir le contenu.

![](assets/new-tab.png)

## Création d’un élément {#create-an-element}

Utilisez les raccourcis dans la variable **[!UICONTROL Créer]** pour ajouter de nouveaux éléments. Vous pouvez également utiliser la variable **[!UICONTROL Créer]** au-dessus de la liste pour ajouter de nouveaux éléments à la liste en cours.

Par exemple, au niveau de la page des diffusions, utilisez le bouton **[!UICONTROL Créer]** pour créer une nouvelle diffusion.

![](assets/new-recipient.png)

## Utilisation d’un navigateur web {#web-browser}

Vous pouvez également accéder à un sous-ensemble de fonctionnalités de Campaign à partir d’un navigateur web.

L’interface d’accès web est similaire à l’interface de la console. Depuis un navigateur, vous pouvez utiliser les mêmes fonctionnalités de navigation et d’affichage que dans la console, mais vous ne pouvez exécuter qu’un ensemble réduit d’actions sur les campagnes. Par exemple, vous pouvez afficher et annuler des campagnes, mais vous ne pouvez pas les modifier.

![](../assets/do-not-localize/glass.png) [En savoir plus sur l&#39;accès web dans Campaign](../start/connect.md#web-access).

## Accès à l’Explorateur Campaign {#ac-explorer-ui}

Parcourez l’Explorateur Campaign pour accéder à l’ensemble des fonctionnalités et paramètres d’Adobe Campaign.

![](assets/explorer.png)

Cet espace de travail vous permet d&#39;accéder à l&#39;arborescence de l&#39;Explorateur pour parcourir toutes les fonctionnalités et options.

La section gauche affiche l&#39;arborescence de l&#39;Explorateur Campaign et vous permet de parcourir tous les composants et paramètres de votre instance, en fonction de vos autorisations.

La section supérieure affiche la liste des enregistrements du dossier actif. Ces listes sont entièrement personnalisables. [En savoir plus](customize-ui.md)

La section inférieure affiche les détails de l’enregistrement sélectionné.


## Langues

L&#39;interface utilisateur de Campaign v8 est disponible dans les langues suivantes :

* Anglais (Royaume-Uni)
* Anglais (États-Unis)
* Français
* Allemand
* Japonais

La langue est sélectionnée lors du processus d&#39;installation.

>[!CAUTION]
>
>La langue ne peut pas être modifiée après la création de l&#39;instance.

La langue affecte les dates et les formats d’heure.


Les principales différences entre l&#39;anglais américain et l&#39;anglais britannique sont les suivantes :

<table> 
 <thead> 
  <tr> 
   <th> Formats<br /> </th> 
   <th> Anglais (États-Unis)<br /> </th> 
   <th> Anglais (UK)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Date<br /> </td> 
   <td> La semaine commence le dimanche<br /> </td> 
   <td> La semaine commence le lundi<br /> </td> 
  </tr> 
  <tr> 
   <td> Date courte<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>ex : 09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>ex : 25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Date courte avec heure<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>ex : 09/25/2018 10:47:25 PM</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>ex : 25/09/2018 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
