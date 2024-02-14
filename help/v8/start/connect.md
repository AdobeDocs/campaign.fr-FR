---
title: Connexion à Campaign avec la console cliente
description: Découvrez comment installer la console cliente Campaign sur votre ordinateur et vous connecter à Adobe Campaign
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 9df599ec0a898a1af16cb92d334d50375fde86ba
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 70%

---

# Connexion à Campaign avec la console cliente{#gs-ac-connect}

Pour vous connecter à Campaign à l&#39;aide de la console cliente, vous devez d&#39;abord l&#39;installer et le configurer.

Avant de commencer, vous devez :

* Vérifier la compatibilité de votre système et de vos outils avec Adobe Campaign dans la [matrice de compatibilité](compatibility-matrix.md)
* Obtenir l&#39;URL du serveur Campaign
* Créer votre Adobe ID ou obtenir vos informations d’identification utilisateur de votre société
* Installez le runtime de Microsoft Edge Webview2 sur votre système. [En savoir plus](#webview)


>[!NOTE]
>
>Vous pouvez également vous connecter à l&#39;interface utilisateur Web de Campaign à l&#39;aide d&#39;un navigateur Web. En savoir plus sur la nouvelle interface utilisateur web de Campaign dans [cette documentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.


## Installation de la console client{#download-ac-console}

### du runtime de Microsoft Edge Webview2 {#webview}

À partir de la version de build 8.4 de Campaign Classic, l’installation du runtime Microsoft Edge Webview 2 est requise pour toute installation de la console cliente.

Web View est installé par défaut dans le cadre du système d’exploitation Windows 11. S&#39;il n&#39;est pas déjà présent sur votre système, le programme d&#39;installation de la console cliente Campaign vous invite à le télécharger à partir de [Site web du développeur Microsoft](http://www.adobe.com/go/acc-ms-webview2-runtime-download_fr){target="_blank"}. Notez que le lien de téléchargement ne fonctionne pas dans le navigateur Internet Explorer 11, car Microsoft ne le prend plus en charge. Assurez-vous d’utiliser un autre navigateur pour accéder au lien.

### Télécharger la console{#install-ac-console}

Lorsque vous utilisez Campaign pour la première fois, vous devez télécharger la console cliente et l’installer.

Deux options sont disponibles pour télécharger la console cliente :

1. En tant qu’administrateur/administratrice de Campaign, connectez-vous à la [distribution logicielle Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"}.

1. En tant qu’utilisateur final, votre administrateur Campaign déploie la console cliente pour vous et la rend disponible via une URL dédiée.

Une fois le programme d’installation de la console cliente téléchargé, installez-le sur votre ordinateur local.

Notez que vous ne pouvez pas modifier la langue de la console cliente une fois installée.

## Créer votre connexion{#create-your-connection}

Une fois la console cliente installée, procédez comme suit pour créer la connexion au serveur applicatif :

1. Démarrez la console et parcourez le lien situé dans le coin droit pour accéder à l’écran de configuration de la connexion.

1. Cliquez sur le menu **[!UICONTROL Ajouter > Connexion]** et saisissez le libellé et l&#39;URL du serveur applicatif Adobe Campaign.

1. Définissez une connexion vers votre serveur applicatif Adobe Campaign à partir d&#39;une URL. Utilisez soit un DNS ou un alias de la machine, soit votre adresse IP.

   Par exemple, vous pouvez utiliser une URL de type [`https://<machine>.<domain>.com`](https://myserver.adobe.com).

1. Cochez l&#39;option **[!UICONTROL Se connecter avec un Adobe ID]**.

1. Cliquez sur **[!UICONTROL OK]** pour enregistrer vos paramètres.

Vous pouvez ajouter autant de connexions que nécessaire pour vous connecter, par exemple, à vos environnements de test, d&#39;évaluation et de production.

>[!NOTE]
>
>Le bouton **[!UICONTROL Ajouter]** permet de créer des **[!UICONTROL dossiers]** dans lesquels vous pourrez classer vos différentes connexions par des opérations de glisser-déposer.

## Connexion à Adobe Campaign {#logon-to-ac}

Les utilisateurs de Campaign se connectent à la console Adobe Campaign à l&#39;aide de leur Adobe ID, via le système IMS (Adobe Identity Management System). Ils peuvent utiliser le même identifiant pour toutes les solutions d&#39;Adobe. La connexion est enregistrée lors de l&#39;utilisation d&#39;Adobe Campaign avec d&#39;autres solutions. Pour en savoir plus sur l&#39;IMS d&#39;Adobe, consultez [cette page](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"}.

Pour vous connecter à une instance, procédez comme suit :

1. Démarrez la console et parcourez le lien situé dans le coin droit pour accéder à l’écran de configuration de la connexion.

   ![](assets/connectToCampaign.png)

1. Sélectionnez l&#39;instance de Campaign à laquelle vous devez vous connecter.

1. Cliquez sur **[!UICONTROL Ok]**.

Vous pouvez ensuite vous connecter à Campaign à l’aide de votre Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Comme Microsoft Edge Webview2 n’enregistre pas les informations d’identification du proxy, la console peut vous demander de vous authentifier deux fois lors de votre première connexion.

## Mettre à niveau votre console cliente{#upgrade-ac-console}

Lorsque votre système est mis à niveau vers une version plus récente, vous devez mettre à jour votre console cliente vers la même version. Il s’agit d’une bonne pratique. Pour certaines versions, cette mise à niveau est obligatoire. Dans ce cas, cela est mentionné dans les [Notes de mise à jour](release-notes.md).

En tant qu’utilisateur de Cloud Service gérés, Adobe déploie la console cliente pour vous. Lorsque vous vous connectez à votre environnement mis à niveau, vous êtes invité à télécharger la dernière version de la console cliente dans une fenêtre contextuelle. Vous devez accepter cette mise à niveau et mettre à jour la console cliente selon vos besoins.

>[!CAUTION]
>
>Adobe recommande de désélectionner l’option **[!UICONTROL Ne plus poser cette question]** pour que tous les utilisateurs et utilisatrices soient informés de la disponibilité d’une nouvelle version de la console. Si cette option est sélectionnée, l’utilisateur ou l’utilisatrice n’est pas informé(e) qu’une mise à niveau de la console est requise.
>



## Octroyer l’accès aux utilisateurs{#grant-access}

Adobe Campaign permet de définir et de gérer les droits attribués aux différents opérateurs.

En tant qu’administrateur/administratrice Campaign, vous êtes chargé(e) de créer les opérateurs et de partager leurs informations d’identification avec les utilisateurs.

En savoir plus sur les utilisateurs et la définition des autorisations adéquates dans [cette section](gs-permissions.md).


## Accès web{#web-access}

Certaines parties de l&#39;application sont accessibles via un navigateur web à l&#39;aide d&#39;une interface utilisateur HTML : reporting, validation des diffusions, surveillance des instances, etc.

L&#39;accès web présente une interface similaire à celle de la console, mais permet d&#39;accéder à un jeu de fonctionnalités réduit.

Par exemple, pour un même opérateur, une opération sera affichée dans la console avec les options suivantes :

![](assets/campaign-from-console.png)

Dans le contexte d&#39;un accès web, les options seront en revanche principalement consultatives :

![](assets/campaign-from-web.png)

L&#39;accès web est également utilisé pour le processus de validation : les opérateurs peuvent cliquer sur l&#39;e-mail de demande de validation et se connecter à Campaign via leur navigateur web pour valider ou refuser le contenu ou le budget d&#39;une diffusion.

Pour accéder à votre instance Campaign à partir du web, l&#39;URL est : `https://<your adobe campaign server>:<port number>/view/home`.
