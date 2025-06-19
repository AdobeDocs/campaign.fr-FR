---
title: Comptes externes de Campaign
description: Comptes externes de Campaign
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 42241364c1a23ae75d8f0aaf18a2cb1c04ce5b0c
workflow-type: ht
source-wordcount: '1135'
ht-degree: 100%

---


# Configuration de vos comptes externes {#config-external-accounts}

Un ensemble de comptes externes prédéfinis est livré avec Adobe Campaign. Pour établir des connexions avec des systèmes externes, vous pouvez créer des comptes externes.

Les comptes externes sont utilisés par les processus techniques comme les workflows techniques ou de campagne. Par exemple, lors de la configuration d&#39;un transfert de fichier dans un workflow ou d&#39;un échange de données avec une autre application (Adobe Target, Experience Manager, etc.), vous devez sélectionner un compte externe.

Vous pouvez accéder aux comptes externes à partir de l&#39;**[!UICONTROL Explorateur]** Adobe Campaign : accédez à **[!UICONTROL Administration]** `>` **[!UICONTROL Plateforme]** `>` **[!UICONTROL Comptes externes]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* En tant qu’utilisateur ou utilisatrice Managed Cloud Services, les comptes externes sont configurés par Adobe pour votre instance et ne doivent pas être modifiés.
>
>* Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), un compte externe **[!UICONTROL Full FDA]** (ffda) gère la connexion entre la base de données locale Campaign et la base de données Cloud ([!DNL Snowflake]).
>

## Comptes externes spécifiques à Campaign {#ac-external-accounts}

Adobe Campaign utilise les comptes techniques suivants pour activer et exécuter des processus spécifiques.

### Mails rebonds {#bounce-mails-external-account}

>[!NOTE]
>
>L’authentification OAuth 2.0 de Microsoft Exchange Online pour la fonctionnalité POP3 est disponible à partir de Campaign v8.3. Pour vérifier votre version, consultez [cette section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

Le compte externe **Mails rebonds** spécifie le compte externe POP3 à utiliser pour se connecter au service de messagerie. Tous les serveurs configurés pour l&#39;accès POP3 peuvent être utilisés pour recevoir les retours d&#39;e-mail.

Pour en savoir plus sur les e-mails entrants, consultez [cette page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html?lang=fr){target="_blank"}.

![](assets/bounce_external_1.png)

Pour configurer le compte externe **[!UICONTROL Mails rebonds (defaultPopAccount)]** :

* **[!UICONTROL Serveur]** - URL du serveur POP3.

* **[!UICONTROL Port]** : numéro de port de la connexion POP3. Le port par défaut est 110.

* **[!UICONTROL Compte]** : nom de l’utilisateur ou de l’utilisatrice.

* **[!UICONTROL Mot de passe]** : mot de passe du compte d’utilisateur.

* **[!UICONTROL Chiffrement]** : type de chiffrement choisi entre **[!UICONTROL Par défaut]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** ou **[!UICONTROL POP3S]**.

  Le compte externe **Mails rebonds** spécifie le compte externe POP3 à utiliser pour se connecter au service de messagerie. Tous les serveurs configurés pour l&#39;accès POP3 peuvent être utilisés pour recevoir les retours d&#39;e-mail.

* **[!UICONTROL Fonction]** : e-mail entrant ou routeur SOAP.

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Avant de configurer votre compte externe POP3 à l’aide de Microsoft OAuth 2.0, vous devez enregistrer votre application sur le portail Azure. Pour en savoir plus à ce sujet, consultez cette [page](https://docs.microsoft.com/fr-fr/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Pour configurer un environnement externe POP3 à l’aide de Microsoft OAuth 2.0, cochez la case **[!UICONTROL Microsoft OAuth 2.0]** et renseignez les champs suivants :

* **[!UICONTROL Locataire Azure]** - L’identifiant Azure (ou identifiant de répertoire, ou de locataire) se trouve dans le menu déroulant **Essentiels** de la vue d’ensemble de votre application dans le portail Azure.

* **[!UICONTROL ID du client Azure]** : ID du client (ou ID d’application (cliente)) se trouvant dans le menu déroulant **Essentiels** de la présentation de votre application dans le portail Azure.

* **[!UICONTROL Secret du client Azure]** : ID du secret du client se trouvant dans la colonne **Secrets des clients** du menu **Certificats et secrets** de votre application dans le portail Azure.

* **[!UICONTROL URL de redirection Azure]** : URL de redirection se trouvant dans le menu **Authentification** de votre application dans le portail Azure. Elle doit se terminer par la syntaxe suivante : `nl/jsp/oauth.jsp`, par exemple `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

  Après avoir saisi les différentes informations d’identification, vous pouvez cliquer sur **[!UICONTROL Configurer la connexion]** pour terminer la configuration de votre compte externe.

### Routage  {#routing}

Le compte externe **[!UICONTROL Routage]** vous permet de configurer chaque canal disponible dans Adobe Campaign en fonction des packages installés.

En savoir plus sur la gestion des comptes externes et l’exécution des diffusions dans [cette section](../architecture/architecture.md#split).

### Instance d&#39;exécution {#execution-instance}

Dans le contexte des messages transactionnels, les instances d’exécution sont liées à l’instance de pilotage et les connectent. Les modèles de messages transactionnels sont déployés vers l’instance d’exécution. Pour en savoir plus sur l’architecture de Message Center, consultez [cette page](../architecture/architecture.md#transac-msg-archi).

## Accès aux comptes externes de systèmes externes {#external-syst-external-accounts}

* **Base de données externe (FDA)** - Le compte externe de type **Base de données externe** permet de se connecter à une base de données externe via Federated Data Access (FDA). En savoir plus sur l’option Federated Data Access (FDA) dans [cette section](../connect/fda.md).

  Les bases de données externes compatibles avec Adobe Campaign v8 sont répertoriées dans la [matrice de compatibilité](../start/compatibility-matrix.md).

* **X (anciennement Twitter)** : le compte externe de type **Twitter** permet de connecter Campaign à votre compte X, afin de publier des messages en votre nom. En savoir plus sur l’intégration X dans [cette section](../connect/ac-tw.md).

## Comptes externes d’intégration de solutions Adobe {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - Le compte externe **[!UICONTROL Adobe Experience Cloud]** permet d’implémenter Adobe Identity Management Service (IMS) pour se connecter à Adobe Campaign. Apprenez-en davantage sur le service Identity Management (IMS) d’Adobe dans [cette section](../start/connect.md#logon-to-ac).

* **Web Analytics** : compte externe **[!UICONTROL Web Analytics (Adobe Analytics)]** permettant de configurer le transfert de données d’Adobe Analytics vers Adobe Campaign. Pour en savoir plus sur l’intégration Adobe Campaign - Adobe Analytics, consultez [cette page](../connect/ac-aa.md).

* **Adobe Experience Manager** : compte externe **[!UICONTROL AEM]** permettant de gérer le contenu de vos diffusions e-mail, ainsi que vos formulaires directement dans Adobe Experience Manager. Pour en savoir plus sur l’intégration Adobe Campaign - Adobe Analytics, consultez [cette page](../connect/ac-aem.md).


## Comptes externes du connecteur CRM {#crm-external-accounts}

* **Microsoft Dynamics CRM** : compte externe **[!UICONTROL Microsoft Dynamics CRM]** permettant d’importer et d’exporter des données Microsoft Dynamics vers Adobe Campaign. Pour en savoir plus sur l’intégration Adobe Campaign - Microsoft Dynamics CRM, [consultez cette page](../connect/ac-ms-dyn.md).

* **Salesforce.com** : compte externe **[!UICONTROL Salesforce CRM]** permettant d’importer et d’exporter des données Salesforce vers Adobe Campaign. Pour en savoir plus sur l’intégration Adobe Campaign - Salesforce.com CRM, [consultez cette page](../connect/ac-sfdc.md).

## Comptes externes de transfert de données {#transfer-data-external-accounts}

Ces comptes externes peuvent être utilisés pour importer ou exporter des données vers Adobe Campaign à l’aide d’une activité de workflow **[!UICONTROL Transfert de fichier.]** Pour en savoir plus sur le **transfert de fichiers** dans les workflows, consultez [cette page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html?lang=fr){target="_blank"}.

* **FTP et SFTP** : compte externe **FTP** permettant de configurer et de tester l’accès à un serveur en dehors d’Adobe Campaign. Pour configurer des connexions avec des systèmes externes comme des serveurs SFTP ou FTP 898 utilisés pour les transferts de fichiers, vous pouvez créer vos propres comptes externes.

  Pour ce faire, spécifiez dans ce compte externe l’adresse et les informations d’identification utilisées pour établir la connexion au serveur SFTP ou FTP.

  >[!NOTE]
  >
  >À partir de la version 8.5, vous pouvez désormais vous authentifier en toute sécurité à l’aide d’une clé privée lors de la configuration de votre compte externe SFTP. [En savoir plus sur la gestion des clés](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=fr){target="_blank"}.

* **Amazon Simple Storage Service (S3)** - Le connecteur **AWS S3** peut être utilisé pour importer ou exporter des données vers Adobe Campaign à l’aide d’une activité de workflow **[!UICONTROL Transfert de fichier]**. Lors de la configuration de ce nouveau compte externe, vous devez indiquer les informations suivantes :

   * **[!UICONTROL Serveur de compte AWS S3]** : l’URL de votre serveur, renseignée comme suit : `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL ID de la clé d’accès AWS]** : découvrez comment trouver votre ID de clé d’accès AWS dans la [documentation Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Clé d&#39;accès secrète à AWS]** : apprenez à trouver votre clé d&#39;accès secrète à AWS en consultant la [documentation Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL Région AWS]** : pour en savoir plus sur les régions AWS, consultez la [documentation Amazon](https://aws.amazon.com/fr/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * La case à cocher **[!UICONTROL Utiliser le chiffrement coté serveur]** vous permet de stocker votre fichier en mode chiffré dans S3. Apprenez à trouver l&#39;ID de clé d&#39;accès et la clé d&#39;accès secrète en consultant la [documentation Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Stockage Blob Azure** : compte externe **Azure** pouvant être utilisé pour importer ou exporter des données vers Adobe Campaign à l’aide d’une activité de workflow **[!UICONTROL Transfert de fichier]**. Pour configurer le compte externe **Azure** afin de l&#39;utiliser avec Adobe Campaign, vous devez fournir les informations suivantes :

   * **[!UICONTROL Serveur]** : URL de votre serveur de stockage Azure Blob.

   * **[!UICONTROL Chiffrement]** : type de chiffrement, **[!UICONTROL Aucun]** ou **[!UICONTROL SSL]**.

   * **[!UICONTROL Clé d&#39;accès]** : apprenez à trouver votre **[!UICONTROL clé d&#39;accès]** en consultant la [documentation Microsoft](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
