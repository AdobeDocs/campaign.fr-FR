---
title: Utilisation de Campaign et Adobe Analytics
description: Découvrez comment intégrer Campaign et Analytics
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 11370fb6-e192-4626-944e-b80a7496e50d
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1284'
ht-degree: 100%

---

# Utilisation de Campaign et d&#39;Adobe Analytics

Vous pouvez également configurer Adobe Analytics pour intégrer Campaign et Analytics.

Cette intégration permet à Adobe Campaign et Adobe Analytics d&#39;interagir par le biais du module complémentaire des **connecteurs Web Analytics**. Cette intégration envoie des indicateurs et des attributs de campagnes par e-mail diffusées par Adobe Campaign à Adobe Analytics.

![](../assets/do-not-localize/speech.png)En tant qu’utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour connecter Campaign aux services et solutions Adobe Experience Cloud. Le module complémentaire de connecteur Web Analytics doit être installé sur votre environnement, via le package dédié.

Avec le connecteur Adobe Analytics, Adobe Campaign permet de mesurer l&#39;audience Internet (Web Analytics). Les outils Web Analytics permettent à Adobe Campaign de transférer des indicateurs et des attributs de campagne vers Analytics.

Le périmètre d&#39;action de chaque outil est le suivant :

* **Adobe Analytics** marque les campagnes e-mail lancées avec Adobe Campaign

* **Adobe Campaign** envoie les indicateurs et les attributs de la campagne vers le connecteur qui les transfère vers l&#39;outil Web Analytics


>[!CAUTION]
>
>Le connecteur Adobe Analytics n&#39;est pas compatible avec les messages transactionnels (Message Center).

Pour configurer la connexion Campaign-Analytics, vous devez effectuer les opérations suivantes :

1. [Création de votre suite de rapports dans Adobe Analytics](#report-suite-analytics)
1. [Configuration des variables de conversion et des événements de succès](#configure-conversion-success)
1. [Configuration de votre compte externe dans Adobe Campaign](#external-account-ac)

## Création de votre suite de rapports Analytics {#report-suite-analytics}

Pour créer votre **[!UICONTROL suite de rapports]** dans [!DNL Adobe Analytics], procédez comme suit :

1. Dans [!DNL Adobe Analytics], sélectionnez l&#39;**[!UICONTROL onglet Admin]** puis cliquez sur **[!UICONTROL Tous les administrateurs]**.

   ![](assets/analytics_connnector_1.png)

1. Cliquez sur **[!UICONTROL Suites de rapports]**.

   ![](assets/analytics_connnector_2.png)

1. Sur la page **[!UICONTROL Responsable des suites de rapports]**, cliquez sur **[!UICONTROL Créer]**, puis sur **[!UICONTROL Suite de rapports]**.

   Pour la procédure détaillée de création de **[!UICONTROL suites de rapports]**, consultez cette [section](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html?lang=fr#prerequisites).

   ![](assets/analytics_connnector_3.png)

1. Choisissez un modèle.

1. Configurez votre nouvelle suite de rapports avec les informations suivantes :

   * **[!UICONTROL Identifiant de suite de rapports]**
   * **[!UICONTROL Titre du site]**
   * **[!UICONTROL Fuseau horaire]**
   * **[!UICONTROL Date de mise en ligne]**
   * **[!UICONTROL Estimation du nombre de pages vues par jour]**

   ![](assets/analytics_connnector_4.png)

1. Une fois la configuration terminée, cliquez sur **[!UICONTROL Créer une suite de rapports]**.

## Configuration des variables de conversion et des événements de succès {#configure-conversion-success}

Après avoir créé votre **[!UICONTROL suite de rapports]**, vous devez configurer vos **[!UICONTROL variables de conversion]** et **[!UICONTROL événements de succès]** comme suit :

1. Sélectionnez la **[!UICONTROL suite de rapports]** précédemment configurée.

1. À partir du bouton **[!UICONTROL Modifier les paramètres]**, sélectionnez **[!UICONTROL Conversion]** > **[!UICONTROL Variables de conversion]**.

   ![](assets/analytics_connnector_5.png)

1. Cliquez sur **[!UICONTROL Ajouter]** pour créer les identifiants nécessaires à la mesure de l&#39;impact de la campagne par e-mail, c&#39;est-à-dire le nom interne de la campagne (cid) et l&#39;identifiant de la table iNmsBroadlog (bid).

   Pour découvrir comment modifier les **[!UICONTROL variables de conversion]**, consultez cette [section](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html?lang=fr#admin-tools).

   ![](assets/analytics_connnector_6.png)

1. Cliquez sur **[!UICONTROL Enregistrer]** lorsque vous avez terminé.

1. Ensuite, pour créer vos **[!UICONTROL Événements de succès]**, sélectionnez **[!UICONTROL Conversion]** > **[!UICONTROL Événements de succès]** à partir du bouton **[!UICONTROL Modifier les paramètres]**.

   ![](assets/analytics_connnector_7.png)

1. Cliquez sur **[!UICONTROL Ajouter]** pour configurer les **[!UICONTROL événements de succès]** suivants :

   * **[!UICONTROL Ont cliqué]**
   * **[!UICONTROL Ayant ouvert]**
   * **[!UICONTROL Personnes ayant cliqué]**
   * **[!UICONTROL Traités]**
   * **[!UICONTROL Différés]**
   * **[!UICONTROL Envoyés]**
   * **[!UICONTROL Nombre total de rebonds]**
   * **[!UICONTROL Clics uniques]**
   * **[!UICONTROL Ouvertures uniques]**
   * **[!UICONTROL Désabonnement]**

   Pour découvrir comment configurer les **[!UICONTROL événements de succès]**, reportez-vous à cette [section](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/t-success-events.html?lang=fr#admin-tools).

   ![](assets/analytics_connnector_8.png)

1. Cliquez sur **[!UICONTROL Enregistrer]** lorsque vous avez terminé.

Une fois votre suite de rapports configurée, vous devez configurer les **[!UICONTROL comptes externes]** dans Adobe Campaign.

## Configuration de votre compte externe Campaign {#external-account-ac}

Vous devez alors configurer votre compte externe **[!UICONTROL Web Analytics]** dans Adobe Campaign pour activer la synchronisation entre les deux solutions.

Veuillez noter que si l&#39;une de vos **[!UICONTROL suites de rapports]**, **[!UICONTROL variables de conversion]** ou **[!UICONTROL événements de succès]** n&#39;est pas visible lors de la configuration de votre compte externe, cela signifie que vous ne disposez pas d&#39;une autorisation pour ce nouveau composant dans le **[!UICONTROL profil de produit]** associé à l&#39;utilisateur.

Pour plus d’informations, consultez la page [Profils de produit pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=fr#product-profile-admins).

1. Dans l&#39;arborescence Adobe Campaign, accédez au dossier **[!UICONTROL Administration**[!UICONTROL  > ]**Plateforme**[!UICONTROL  > ]**Comptes externes]** et cliquez sur le bouton **[!UICONTROL Nouveau]**.

   ![](assets/analytics_connnector_9.png)

1. Utilisez la liste déroulante pour sélectionner le type **[!UICONTROL Web Analytics]** et **[!UICONTROL Adobe Analytics]** dans la liste déroulante **[!UICONTROL Intégration]**.

   ![](assets/analytics_connnector_10.png)

1. Cliquez sur **[!UICONTROL Configurer]** en regard de la liste déroulante **[!UICONTROL Intégration]**.

1. Dans la fenêtre **[!UICONTROL Configurer l&#39;intégration d&#39;Analytics]**, associez votre compte externe à la suite de rapports créée précédemment en fournissant les informations suivantes :

   * **[!UICONTROL E-mail]**
   * **[!UICONTROL Org. IMS]**
   * **[!UICONTROL Société Analytics]**
   * **[!UICONTROL Suite de rapports]**


1. Dans la catégorie **[!UICONTROL eVars]**, mappez les deux **[!UICONTROL variables de conversion]** configurées dans [!DNL Adobe Analytics].

   ![](assets/analytics_connnector_11.png)

1. Dans la catégorie **[!UICONTROL Événements]**, mappez les dix **[!UICONTROL événements de succès]** configurés dans [!DNL Adobe Analytics].

1. Cliquez sur **[!UICONTROL Soumettre]** lorsque vous avez terminé. Adobe Campaign va créer une **[!UICONTROL source de données]**, des **[!UICONTROL mesures calculées]**, des **[!UICONTROL segments de remarketing]** et des **[!UICONTROL classifications]** dans la **[!UICONTROL suite de rapports]** mappée.

   Une fois cette synchronisation entre [!DNL Adobe Analytics] et Adobe Campaign effectuée, vous pouvez fermer la fenêtre.

1. Les paramètres sont visibles dans l&#39;onglet **[!UICONTROL Paramètres des données]** de la fenêtre **[!UICONTROL Configurer l&#39;intégration d&#39;Analytics]**.

   À l&#39;aide du bouton **[!UICONTROL Synchroniser]**, [!DNL Adobe Campaign] synchronise les modifications de nom effectuées dans [!DNL Adobe Analytics]. Si le composant est supprimé dans [!DNL Adobe Analytics], il est barré dans [!DNL Adobe Campaign] ou affiché avec le message **introuvable**.

   ![](assets/analytics_connnector_12.png)

   >[!NOTE]
   >
   > Vous ne pouvez pas ajouter ni supprimer de segments dans cette version de Campaign v8.

1. Depuis votre **[!UICONTROL compte externe]**, cliquez sur le lien **[!UICONTROL Enrichir la formule...]** pour modifier la formule de calcul des URL afin de spécifier les informations d&#39;intégration pour l&#39;outil de Web Analytics (soit les identifiants de campagne) et les domaines des sites dont l&#39;activité doit faire l&#39;objet d&#39;un tracking.

   ![](assets/analytics_connnector_13.png)

1. Indiquez le ou les noms de domaine des sites.

   ![](assets/analytics_connnector_14.png)

1. Cliquez sur **[!UICONTROL Suivant]** et vérifiez que les noms de domaines ont bien été enregistrés.

   ![](assets/analytics_connnector_15.png)

1. Au besoin, vous pouvez surcharger la formule de calcul. Pour cela, cochez la case et modifiez la formule directement dans la fenêtre.

   >[!IMPORTANT]
   >
   >Ce type de paramétrage s&#39;adresse à des utilisateurs experts : toute erreur dans cette formule risque de bloquer la diffusion des e-mails.

1. L&#39;onglet **[!UICONTROL Avancé]** vous permet de modifier des paramètres plus techniques.

   * **[!UICONTROL Durée de vie]** : permet de définir un délai (en jours) après lequel les événements web récupérés dans Adobe Campaign par les workflows techniques. Par défaut : 180 jours.
   * **[!UICONTROL Persistance]** : permet de définir la période pendant laquelle tout événement web (un achat par exemple) peut être attribué à une opération de remarketing. Par défaut : 7 jours.

>[!NOTE]
>
>Si vous utilisez plusieurs outils de mesure d&#39;audience, vous pouvez sélectionner la valeur **[!UICONTROL Autre]** dans la liste déroulante **[!UICONTROL Partenaire]** lors de la création du compte externe. Un seul compte externe peut être référencé dans les propriétés des diffusions : vous devrez donc adapter la formule des URL trackées en ajoutant les paramètres attendus par Adobe ou tout autre outil de mesure utilisé.

## Workflow technique des processus Web Analytics {#technical-workflows-of-web-analytics-processes}

L&#39;échange des données entre Adobe Campaign et Adobe Analytics est géré par un workflow technique qui s&#39;exécute en tâche de fond.

Ce workflow est disponible à partir de l&#39;arborescence de l&#39;explorateur Campaign, sous le dossier **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Workflows techniques]** > **[!UICONTROL Processus Web Analytics]**.

![](assets/webanalytics_workflows.png)

Le workflow **[!UICONTROL Envoi des indicateurs et des attributs de campagne]** permet d&#39;envoyer les indicateurs des campagnes e-mail depuis Adobe Campaign vers Adobe Experience Cloud à l&#39;aide du connecteur Adobe Analytics. Ce workflow est déclenché à 4 heures du matin tous les jours et peut prendre 24 heures pour que les données soient envoyées à Analytics.

Veuillez noter que ce workflow ne devrait pas être redémarré. Dans le cas contraire, il renverrait toutes les données précédentes, ce qui peut fausser les résultats d&#39;Analytics.

Les indicateurs concernés sont les suivants :

* **[!UICONTROL Messages à envoyer]** (@toDeliver)
* **[!UICONTROL Traités]** (@processed)
* **[!UICONTROL Succès]** (@success)
* **[!UICONTROL Nombre total d&#39;ouvertures]** (@totalRecipientOpen)
* **[!UICONTROL Destinataires ayant ouvert]** (@recipientOpen)
* **[!UICONTROL Nombre total de destinataires ayant cliqué]** (@totalRecipientClick)
* **[!UICONTROL Personnes ayant cliqué]** (@personClick)
* **[!UICONTROL Nombre de clics distincts]** (@recipientClick)
* **[!UICONTROL Désinscription (opt-out)]** (@optOut)
* **[!UICONTROL Erreurs]** (@error)

>[!NOTE]
>
>Les données envoyées correspondent au delta basé sur la dernière prise de photo, ce qui peut générer une valeur négative dans les données de mesure.

Les attributs envoyés sont les suivants :

* **[!UICONTROL Nom interne]** (@internalName)
* **[!UICONTROL Libellé]** (@label)
* **[!UICONTROL Libellé]** (operation/@label) : uniquement si le package **Campaign** est installé
* **[!UICONTROL Nature]** (operation/@nature) : uniquement si le package **Campaign** est installé
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Date de contact]** (scheduling/@contactDate)

## Suivi des diffusions {#tracking-deliveries-in-adobe-campaign}

Afin qu&#39;Adobe Experience Cloud puisse suivre l&#39;activité sur les sites après l&#39;envoi de diffusions par Adobe Campaign, il est nécessaire de référencer le connecteur correspondant dans les propriétés de la diffusion. Pour cela, procédez comme suit :

1. Ouvrez la diffusion de la campagne destinée à être suivie.

   ![](assets/webanalytics_delivery_properties_003.png)

1. Ouvrez les propriétés de la diffusion.
1. Dans l&#39;onglet **[!UICONTROL Web Analytics]**, sélectionnez le compte externe créé précédemment. Voir [Configuration de votre compte externe dans Adobe Campaign](#external-account-ac).

   ![](assets/webanalytics_delivery_properties_002.png)

1. Vous pouvez maintenant envoyer votre diffusion et accéder au rapport correspondant dans Adobe Analytics.


**Rubriques connexes**

* [Intégration Campaign - Triggers Experience Cloud](ac-triggers.md)
