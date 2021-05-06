---
solution: Campaign Classic
product: campaign
title: Campaign comptes externes
description: Campaign comptes externes
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 38%

---

# Configuration de vos comptes externes

Un ensemble de comptes externes prédéfinis est livré avec Adobe Campaign. Pour établir des connexions avec des systèmes externes, vous pouvez créer des comptes externes.

Les comptes externes sont utilisés par les processus techniques comme les workflows techniques ou de campagne. Par exemple, lors de la configuration d’un transfert de fichier dans un workflow ou d’un échange de données avec une autre application (Adobe Target, Experience Manager, etc.), vous devez sélectionner un compte externe.

:flèche_supérieur_droite : Découvrez comment créer et configurer des comptes externes dans la [documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts.html)

Un compte externe spécifique gère la connexion entre la base de données locale Campaign et la base de données Cloud ([!DNL Snowflake]).

:speak_bulon: En tant qu’utilisateur Cloud Services géré, le compte externe [!DNL Snowflake] est configuré pour votre instance par Adobe.

Vous pouvez accéder à ce compte externe pour vérifier les paramètres et exécuter les workflows de réplication. Pour ce faire, suivez les étapes ci-après :

1. Dans Campaign **[!UICONTROL Explorateur]**, cliquez sur **[!UICONTROL Administration > Plateforme > Comptes externes]**.

1. Sélectionnez le compte externe **[!UICONTROL FDA complète]**.

![](assets/snowflake-ext-account.png)

Les paramètres globaux s&#39;affichent dans l&#39;onglet **[!UICONTROL Général]**.

Utilisez l&#39;onglet **[!UICONTROL Paramètres]**, puis le bouton **[!UICONTROL Déployer les fonctions]** pour créer des fonctions.

![](assets/snowflake-parameters.png)

**AJOUTER LES PARAMÈTRES DESC ICI**

Utilisez l&#39;onglet **[!UICONTROL FDA complète]** pour forcer l&#39;exécution du processus de réplication.

![](assets/snowflake-full-fda.png)

**AJOUTER LES DÉTAILS ICI**

