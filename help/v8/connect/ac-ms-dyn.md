---
title: Work with Campaign and Microsoft Dynamics
description: Learn how to work with Campaign and Microsoft Dynamics
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '1400'
ht-degree: 46%

---

# Work with Campaign and Microsoft Dynamics 365{#crm-ms-dynamics}

****

Once configuration is done, data synchronization between systems is carried out via a dedicated workflow activity. [En savoir plus](crm-data-sync.md).

>[!NOTE]
>
>[](../start/compatibility-matrix.md)

Follow the steps below to configure a dedicated external account to import and export Microsoft Dynamics 365 data into Adobe Campaign.

Pour chaque système, ces étapes doivent être exécutées par un administrateur.

>[!CAUTION]
> Les étapes de cette documentation vous guideront tout au long de la création des intégrations/inscriptions impliquant l&#39;attribution d&#39;autorisations et/ou d&#39;accès administrateur. Vous êtes tenu de vous assurer que ces étapes sont conformes aux politiques de votre entreprise avant de les exécuter, et de les exécuter avec précaution.

## Configuration de Microsoft Dynamics 365 {#config-crm-microsoft}

****[](https://portal.azure.com)****

1. Get your Dynamics 365 Application (client) ID. [En savoir plus](#get-client-id-microsoft)
1. Génération de l’identifiant de clé de certificat Microsoft Dynamics et de l’ID de clé. [En savoir plus](#config-certificate-key-id)
1. Configuration des autorisations. [En savoir plus](#config-permissions-microsoft)
1. Création d&#39;un utilisateur d&#39;application. [En savoir plus](#create-app-user-microsoft)
1. Codage de la clé privée. [En savoir plus](#configure-acc-for-microsoftt)


### Get Dynamics 365 Client ID {#get-client-id-microsoft}

To get the Application (client) ID, you need to register an App in Azure Active Directory.

1. ********
1. **`<instance identifier>`**

**** You will need this ID later on in configuring Dynamics 365 in Adobe Campaign.

[](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory)

### Génération de l’identifiant de clé de certificat Microsoft Dynamics et de l’ID de clé {#config-certificate-key-id}

******** Certificates can be used as secrets to prove the application’s identity when requesting a token. Also can be referred to as public keys.

Procédez comme suit :

1. ****
1. ****
1. ********
1. Upload your public certificate.
1. ************

************

+++ How to generate the public certificate

To generate the certificate, you can use openssl.

Par exemple :

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>Vous pouvez modifier le nombre de jours, ici `-days 365`, dans l’exemple de code pour une période de validité du certificat plus longue.

You must then encode the certificate in base64. Pour cela, vous pouvez utiliser l&#39;aide d&#39;un encodeur Base64 ou utiliser la ligne de commande `base64 -w0 private.key` sous Linux.

+++

### Configuration des autorisations {#config-permissions-microsoft}

**Étape 1** : configurez les **autorisations obligatoires** pour l&#39;application qui a été créée.

1. Accédez à **Azure Active Directory > Enregistrements des applications** et sélectionnez l&#39;application qui a été créée précédemment.
1. Cliquez sur **Paramètres** en haut à gauche.
1. Sur **Autorisations obligatoires**, cliquez sur **Ajouter** et **Sélectionner une API > Dynamics CRM Online**.
1. Cliquez sur **Sélectionner**, activez la case **Accéder à Dynamics 365 en tant qu’utilisateurs de l’organisation** et cliquez sur **Sélectionner**.
1. Ensuite, dans l’application, sélectionnez le **Manifest** sous le menu **Gérer**.
1. Dans l’éditeur **Manifest**, définissez la propriété `allowPublicClient` de `null` sur `true` et cliquez sur **Enregistrer**.

**Étape 2** : autorisez le consentement administrateur

1. Accédez à **Répertoire actif Azure > Applications d’entreprise**.
1. Sélectionnez l’application à laquelle vous souhaitez accorder le consentement administrateur à l’échelle du client.
1. Dans le menu du volet de gauche, sélectionnez **Autorisations** sous **Sécurité**.
1. Cliquez sur **Accorder le consentement administrateur**.

Pour plus d&#39;informations à ce propos, consultez la [documentation Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Création d&#39;un utilisateur d&#39;application {#create-app-user-microsoft}

>[!NOTE]
>
> Cette étape est facultative avec l’authentification **[!UICONTROL Mots de passe]**.

L&#39;utilisateur de l&#39;application est l&#39;utilisateur que l&#39;application enregistrée ci-dessus utilisera. Toute modification apportée à Microsoft Dynamics à l&#39;aide de l&#39;application enregistrée ci-dessus sera effectuée via cet utilisateur.

**Étape 1** : Création d&#39;un utilisateur non interactif sur Azure Active Directory

1. Cliquez sur **Azure Active Directory > Utilisateurs** et sur **Nouvel utilisateur**.
1. Donnez un nom adapté que vous souhaitez utiliser et le nom d&#39;utilisateur doit être au format d&#39;un email.
1. Sélectionnez **Administrateur Dynamics 365** dans le **Rôle de répertoire**.

**Étape 2** : Attribuer une licence appropriée à l&#39;utilisateur créé

1. Dans [Microsoft Azure](https://portal.azure.com), cliquez sur **Application d&#39;administration**.
1. Accédez à **Utilisateurs > Utilisateurs actifs** et cliquez sur l&#39;utilisateur qui vient d&#39;être créé.
1. Cliquez sur **Modifier les licences de produit** et sélectionnez **Dynamics 365 Customer Engagement Plan**.
1. Cliquez sur **Fermer**.

**Étape 3** : Création d&#39;un utilisateur d&#39;application sur Dynamics CRM

1. Depuis [Microsoft Azure](https://portal.azure.com), accédez à **Paramètres > Sécurité > Utilisateurs**.
1. ********
1. Utilisez le même nom d&#39;utilisateur que celui créé dans Active Directory ci-dessus.
1. Affectez l&#39;**ID de l&#39;application** à [l&#39;application que vous avez créée précédemment](#get-client-id-microsoft).
1. Cliquez sur **Gérer les rôles** et sélectionnez le rôle **Administrateur système** pour l&#39;utilisateur.

## Configuration de Campaign {#configure-acc-for-microsoft}

### Création de la connexion{#new-ms-dyn-external-account}

First, you must create the Microsoft Dynamics 365 external account.

1. ****
1. ********
1. ****

   ![](assets/ms-dyn-external-account.png)

   1. ****

      * **Serveur** : URL de votre serveur Microsoft CRM. Pour trouver votre URL de serveur Microsoft CRM, accédez à votre compte Microsoft Dynamics CRM, puis cliquez sur Dynamics 365 et sélectionnez votre application. You can then find your Server URL in the address bar of your browser, e.g. https://myserver.crm.dynamics.com/.
      * **Compte** : compte utilisé pour se connecter à Microsoft CRM
      * ****
      * ****
      * ****
   1. ****

      * **Serveur** : URL de votre serveur Microsoft CRM. Pour trouver votre URL de serveur Microsoft CRM, accédez à votre compte Microsoft Dynamics CRM, puis cliquez sur Dynamics 365 et sélectionnez votre application. You can then find your Server URL in the address bar of your browser, e.g. https://myserver.crm.dynamics.com/.
      * ****[](#config-certificate-key-id)
      * ********[](#config-certificate-key-id)
      * ********[](#config-certificate-key-id)
      * ****[](#get-client-id-microsoft)
      * ****


1. ****

>[!NOTE]
>
>To approve the setup, log off and back on to the Adobe Campaign console.

### Select tables to synchronize{#ms-dyn-create-tables}

You can now configure tables to synchronize.

1. ****
1. Select the tables to synchronize and start the process.
1. Vérifiez le schéma généré dans Adobe Campaign, sous le noeud **[!UICONTROL Administration > Paramétrage > Schéma de données]**.

>[!NOTE]
>
>`login.microsoftonline.com` To perform this, contact your Adobe representative.

## Synchronisation des énumérations{#sfdc-enum-sync}

Once the schema is created, you can synchronize enumerations automatically from Dynamics 365 to Adobe Campaign.

1. ****
1. Select the Adobe Campaign enumeration that matches the Dynamics 365 enumeration.
Vous pouvez remplacer toutes les valeurs d&#39;une énumération Adobe Campaign par celles du CRM : pour cela, sélectionnez **[!UICONTROL Oui]** dans la colonne **[!UICONTROL Remplacer]**.
1. ********
1. ****

Adobe Campaign and Microsoft Dynamics 365 are now connected. Vous pouvez configurer la synchronisation des données entre les deux systèmes.

****

Pour en savoir plus sur la synchronisation des données, consultez [cette page](crm-data-sync.md).

### Types de données de champ pris en charge {#ms-dyn-supported-types}

Pour Microsoft Dynamics 365, les types d&#39;attribut pris en charge/non pris en charge sont répertoriés ci-dessous :


| Type d&#39;attribut | Pris en charge |
| --------------------------------------------------------------------------------- | --------- |
| Types simples : booléen, date et heure, nombre décimal, nombre à virgule flottante, doublon, nombre entier, entier long, chaîne | Oui |
| Devise (en tant que doublon) | Oui |
| mémo, nom de l&#39;entité, clé primaire, identifiant unique (en tant que chaînes) | Oui |
| Statut, liste de sélection (les valeurs possibles sont stockées dans des énumérations), état (chaîne) | Oui |
| propriétaire (comme chaîne) | Oui |
| Recherche (seules les recherches de référence d&#39;entité unique) | Oui |
| client | Non |
| Concernant | Non |
| PartyList | Non |
| ManagedProperty | Non |
