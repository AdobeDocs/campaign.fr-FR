---
title: Gestion des demandes d’accès à des informations personnelles dans Campaign
description: Découvrez comment gérer les demandes d’accès à des informations personnelles dans Campaign
feature: Audiences
role: Data Engineer
level: Beginner
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 49%

---

# Gestion des demandes d’accès à des informations personnelles dans Campaign {#privacy}

<!--Adobe Campaign is a powerful tool for collecting and processing large volume of data, including personal information and sensitive data. It is therefore essential that you receive and monitor consent from your recipients.-->

>[!NOTE]
>
>Cette fonctionnalité est disponible à partir de Campaign v8.3. Pour vérifier votre version, reportez-vous à la section [cette section](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

Pour faciliter la préparation à la protection des données, Adobe Campaign permet désormais de gérer les demandes d’accès et de suppression.

![](../assets/do-not-localize/speech.png) En savoir plus sur les **Droit d’accès** et le **Droit à l&#39;oubli** (requête de suppression) dans [Documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#right-access-forgotten){target=&quot;_blank&quot;}.

Pour effectuer ces demandes, vous devez utiliser l&#39;intégration de **Privacy Core Service**. Les demandes d&#39;accès à des informations personnelles transmises par Privacy Core Service à toutes les solutions Experience Cloud sont automatiquement traitées par Campaign via un workflow dédié. [En savoir plus](#create-privacy-request)

Adobe offre aux contrôleurs de données les outils nécessaires pour créer et traiter des demandes d’accès à des informations personnelles pour les données stockées dans Campaign. Cependant, il vous incombe, en tant que contrôleur de données, de vérifier l’identité du titulaire de données qui effectue la demande et de confirmer que les données renvoyées au demandeur concernent le titulaire de données. En savoir plus sur les données personnelles et les différentes entités qui gèrent les données dans [Documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#personal-data){target=&quot;_blank&quot;}.

## Définition d’un espace de noms {#namespaces}

Avant de créer une demande d’accès à des informations personnelles, vous devez : **Définition de l’espace de noms** vous utiliserez. L&#39;espace de noms est la clé qui sera utilisée pour identifier le titulaire de données dans la base de données Adobe Campaign.

>[!NOTE]
>
>Pour en savoir plus sur les espaces de noms d’identité, voir [Documentation Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html){target=&quot;_blank&quot;}.

Actuellement, Adobe Campaign ne prend pas en charge l’importation d’espaces de noms à partir du service d’espace de noms d’identité Experience Platform. Par conséquent, une fois que vous avez créé un espace de noms sur le service Identity Namespace, vous devez créer manuellement l’espace de noms correspondant dans l’interface Adobe Campaign. Pour ce faire, suivez les étapes ci-après.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Créez un espace de noms sur le [Service Identity Namespace](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target=&quot;_blank&quot;}.

1. When [liste des espaces de noms d’identité](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target=&quot;_blank&quot;} disponible pour votre organisation, vous obtiendrez l’espace de noms suivant, par exemple :

   ```
   {
           "updateTime": 1632903236731,
           "code": "lumanamespace",
           "status": "ACTIVE",
           "description": "new namespace for Luma privacy requests",
           "id": 10998717,
           "createTime": 1632903236731,
           "idType": "Email",
           "namespaceType": "Custom",
           "name": "Luma Namespace",
           "custom": true
   }
   ```

1. Dans Adobe Campaign, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Espaces de noms]** et sélectionnez **[!UICONTROL Nouveau]**.

   ![](assets/privacy-namespaces-new.png)

1. Saisissez un **[!UICONTROL Libellé]**.

1. Renseignez les détails du nouvel espace de noms pour qu’il corresponde à l’espace de noms que vous avez créé dans le service Identité - Espace de noms :

   * la valeur **[!UICONTROL Identifiant d’espace de noms AEC]** doit correspondre à l’attribut &quot;id&quot; ;
   * la valeur **[!UICONTROL Nom interne]** doit correspondre à l’attribut &quot;code&quot; ;
   * la valeur **[!UICONTROL Reconciliation key]** doit correspondre à l’attribut &quot;idType&quot;.

   ![](assets/privacy-namespaces-details.png)

   Le **[!UICONTROL Reconciliation key]** sera utilisé pour identifier le titulaire de données dans la base de données Adobe Campaign.

1. Sélectionner un mapping de ciblage <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)--> pour spécifier comment l’espace de noms sera réconcilié dans Adobe Campaign.

   >[!NOTE]
   >
   >    Si vous souhaitez utiliser plusieurs mappings de ciblage, vous devez créer un espace de noms par mapping.

1. Enregistrez vos modifications.

Vous pouvez maintenant créer des demandes d&#39;accès à des informations personnelles basées sur votre nouvel espace de noms. Si vous utilisez plusieurs espaces de noms, créez une demande d’accès à des informations personnelles par espace de noms pour la même valeur de réconciliation.

## Créer une demande d’accès à des informations personnelles {#create-privacy-request}

Le **Privacy Core Service** L’intégration vous permet d’automatiser vos demandes d’accès à des informations personnelles dans un contexte multisolution par le biais d’un seul appel API JSON. Adobe Campaign gère automatiquement les demandes transmises par Privacy Core Service via un workflow dédié.

>[!CAUTION]
>
>Pour que les demandes d’accès à des informations personnelles soient traitées, vous devez créer sur votre instance Adobe Campaign un espace de noms correspondant à l’espace de noms que vous avez créé dans le service Espace de noms d’identité Experience Platform.

Reportez-vous à la section [Privacy Service Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr)Documentation {target=&quot;_blank&quot;} pour apprendre à créer des demandes d’accès à des informations personnelles à partir de Privacy Core Service.

Chaque tâche Privacy Core Service est divisée en plusieurs demandes d’accès à des informations personnelles dans Adobe Campaign en fonction du nombre d’espaces de noms utilisés, une demande correspondant à un espace de noms.

En outre, un traitement peut être exécuté sur plusieurs instances. C&#39;est pourquoi plusieurs fichiers sont créés pour un seul traitement. Par exemple, si une demande contient deux espaces de noms et est exécutée sur trois instances, six fichiers sont envoyés. Soit un fichier par espace de noms et par instance.

Le modèle d&#39;un nom de fichier est le suivant : `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **NomInstance** : nom de l&#39;instance dans Campaign
* **IdEspaceDeNoms** : identifiant de l&#39;espace de noms du service d&#39;identités utilisé
* **CléRéconciliation** : clé de réconciliation encodée

>[!CAUTION]
>
>Pour soumettre une requête à l’aide du type d’espace de noms personnalisé, réutilisez la [méthode JSON](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=fr#json){target=&quot;_blank&quot;} et ajoutez l’identifiant d’espace de noms à la requête, ou utilisez l’[appel API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=fr#access-delete){target=&quot;_blank&quot;} pour effectuer la requête.
>
>N’utilisez que l’[Interface utilisateur Accès à des informations personnelles](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=fr#request-builder){target=&quot;_blank&quot;} pour envoyer des requêtes à l’aide du type d’espace de nom standard.

### Tableaux recherchés lors des demandes de traitement {#list-of-tables}

Lors de l’exécution d’une demande d’accès ou de suppression de données personnelles, Adobe Campaign recherche toutes les données du titulaire des données en fonction de la **[!UICONTROL Valeur de réconciliation]** dans toutes les tables ayant un lien avec la table du destinataire (type own).

Voici la liste des tables d&#39;usine qui sont prises en compte lors de l&#39;exécution des demandes d&#39;accès à des données personnelles :

* Destinataires (recipient)
* Log de diffusion des destinataires (broadLogRcp)
* Log de suivi des destinataires (trackingLogRcp)
* Log de diffusion d&#39;un événement historisé (broadLogEventHisto)
* Contenu des listes de destinataires (rcpGrpRel)
* Proposition d&#39;offre d&#39;un visiteur (propositionVisitor)
* Visiteurs (visitor)
* Historique d&#39;abonnement (subHisto)
* Abonnements (subscription)
* Proposition d&#39;offre d&#39;un destinataire (propositionRcp)

Si vous avez créé des tables personnalisées ayant un lien avec la table du destinataire (type own), celles-ci sont également prises en compte. Par exemple, si une table de transaction est liée à la table du destinataire et si une table de détails de transaction est liée à la table de transaction, elles sont toutes deux prises en compte.
<!--
>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.-->

### États des demandes d&#39;accès à des informations personnelles {#privacy-request-statuses}

Voici les différents statuts des demandes d&#39;accès à des informations personnelles dans Adobe Campaign :

* **[!UICONTROL Nouveau]**/**[!UICONTROL Reprise en attente]** : en cours, le workflow n&#39;a pas encore traité la demande.
* **[!UICONTROL Traitement]**/**[!UICONTROL Reprise en cours]** : le workflow traite la demande.
* **[!UICONTROL Suppression en attente]** : le workflow a identifié toutes les données du destinataire à supprimer.
* **[!UICONTROL Suppression en cours]** : le workflow traite la suppression.
* **[!UICONTROL Terminé]** : le traitement de la demande s&#39;est terminé sans erreur.
* **[!UICONTROL Erreur]** : le workflow a rencontré une erreur. La raison apparaît dans la colonne **[!UICONTROL État de la demande]** de la liste des demandes d&#39;accès à des informations personnelles. Par exemple, le statut **[!UICONTROL Erreur : données introuvables]** indique qu&#39;aucune donnée du destinataire correspondant à la **[!UICONTROL Valeur de réconciliation]** du titulaire de données n&#39;a été trouvée dans la base de données.

**Rubriques connexes** dans la documentation de Campaign Classic v7 :

* [Confidentialité et consentement](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target=&quot;_blank&quot;}

* [Prise en main de la gestion de la confidentialité](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html){target=&quot;_blank&quot;}

* [Règlements relatifs à la gestion de la confidentialité](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#privacy-management-regulations){target=&quot;_blank&quot;} (RGPD, CCPA, PDPA et LGPD)

* [Droit d’opposition (opt-out) à la vente des informations personnelles](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html){target=&quot;_blank&quot;} (spécifique au CCPA)