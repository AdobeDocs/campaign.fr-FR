---
product: Adobe Campaign
title: Comptes externes de Campaign
description: Comptes externes de Campaign
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: ff2c49a2b4f22cde7ebb798d9f565e133c0268fc
workflow-type: ht
source-wordcount: '1124'
ht-degree: 100%

---


# Configuration de vos comptes externes

Un ensemble de comptes externes prédéfinis est livré avec Adobe Campaign. Pour établir des connexions avec des systèmes externes, vous pouvez créer des comptes externes.

Les comptes externes sont utilisés par les processus techniques comme les workflows techniques ou de campagne. Par exemple, lors de la configuration d&#39;un transfert de fichier dans un workflow ou d&#39;un échange de données avec une autre application (Adobe Target, Experience Manager, etc.), vous devez sélectionner un compte externe.

Vous pouvez accéder aux comptes externes à partir de l&#39;**[!UICONTROL Explorateur]** Adobe Campaign : accédez à **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL Comptes externes]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Un compte **[!UICONTROL Full FDA]** (FFDA) externe spécifique gère la connexion entre la base de données locale de Campaign et la base de données cloud ([!DNL Snowflake]).
>
>En tant qu&#39;utilisateur Managed Cloud Services, ce compte externe est configuré pour votre instance par Adobe. Il ne doit pas être modifié.


## Comptes externes spécifiques à Campaign

Adobe Campaign utilise les comptes techniques suivants pour activer et exécuter des processus spécifiques.

[!DNL :speech_balloon:] En tant qu&#39;utilisateur Managed Cloud Services, Adobe configure tous les comptes externes spécifiques à Campaign pour vous.

* **Mails rebonds (POP3)**

   Le compte externe **Mails rebonds** spécifie le compte externe POP3 à utiliser pour se connecter au service de messagerie. Tous les serveurs configurés pour l&#39;accès POP3 peuvent être utilisés pour recevoir les retours d&#39;e-mail.

   [!DNL :arrow_upper_right:] Apprenez-en davantage sur les e-mails entrants dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html?lang=fr)

* **Routage**

   Le compte externe **[!UICONTROL Routage]** vous permet de configurer chaque canal disponible dans Adobe Campaign en fonction des packages installés.

   >[!CAUTION]
   >
   >Le compte externe **[!UICONTROL Routage e-mail intégré]** (defaultEmailBulk) **ne doit pas** être activé dans Adobe Campaign v8.

* **Instance d&#39;exécution**

   Dans le contexte des messages transactionnels, les instances d&#39;exécution sont liées à l&#39;instance de pilotage et les connectent. Les modèles de messages transactionnels sont déployés vers l&#39;instance d&#39;exécution.

   [!DNL :bulb:] Pour en savoir plus sur l&#39;architecture de Message Center, consultez [cette page](../dev/architecture.md#transac-msg-archi).

## Accès aux comptes externes de systèmes externes

* **Base de données externe (FDA)**

   Utilisez le compte externe de type **Base de données externe** pour vous connecter à une base de données externe via FDA.

   Les bases de données externes compatibles avec Adobe Campaign v8 sont répertoriées dans la [matrice de compatibilité](../start/compatibility-matrix.md)

   [!DNL :bulb:] Apprenez-en davantage sur l&#39;option Federated Data Access (FDA) dans [cette section](../connect/fda.md).

## Comptes externes d&#39;intégration de solutions Adobe

* **Adobe Experience Cloud**

   Pour vous connecter à la console Adobe Campaign à l&#39;aide d&#39;un Adobe ID, vous devez configurer le compte externe **[!UICONTROL Adobe Experience Cloud]**.

   [!DNL :bulb:] Apprenez-en davantage sur le service Identity Management (IMS) d&#39;Adobe dans [cette section](../start/connect.md#connect-ims).

   [!DNL :speech_balloon:] En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour implémenter Adobe IMS avec Campaign.

* **Web Analytics**

   Utilisez le compte externe **[!UICONTROL Web Analytics (Adobe Analytics)]** pour configurer le transfert de données d&#39;Adobe Analytics vers Adobe Campaign.

   [!DNL :bulb:] Pour en savoir plus sur l&#39;intégration Adobe Campaign - Adobe Analytics, consultez [cette page](../connect/ac-aa.md).

   [!DNL :speech_balloon:] En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour intégrer Adobe Analytics à Campaign.

   * **Adobe Experience Manager**
   Le compte externe **[!UICONTROL AEM]** permet de gérer le contenu de vos diffusions e-mail, ainsi que vos formulaires directement dans Adobe Experience Manager.

   [!DNL :bulb:] Pour en savoir plus sur l&#39;intégration Adobe Campaign - Adobe Analytics, consultez [cette page](../connect/ac-aem.md).

   [!DNL :speech_balloon:] En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour intégrer Adobe Experience Manager à Adobe Campaign.


## Comptes externes du connecteur CRM

* **Microsoft Dynamics CRM**

   Le compte externe **[!UICONTROL Microsoft Dynamics CRM]** vous permet d&#39;importer et d&#39;exporter des données Microsoft Dynamics vers Adobe Campaign.

   [!DNL :bulb:]Pour en savoir plus sur l&#39;intégration Adobe Campaign - Microsoft Dynamics CRM, [consultez cette page](../connect/crm.md).

   Avec le type de déploiement **[!UICONTROL Web API]** et l&#39;authentification **[!UICONTROL Mot de passe]**, vous devez fournir les informations suivantes :

   * **[!UICONTROL Compte]** : compte utilisé pour se connecter à Microsoft CRM

   * **[!UICONTROL Serveur]** : URL de votre serveur Microsoft CRM.

   * **[!UICONTROL Identifiant client]** : ID du client qui se trouve sur le portail de gestion Microsoft Azure au niveau de la catégorie **[!UICONTROL Mettre à jour votre code]**, dans le champ **[!UICONTROL Identifiant du client]**.

   * **[!UICONTROL Version du CRM]** : version du CRM, **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** ou **[!UICONTROL Dynamics CRM 2016]**.
   Avec le type de déploiement **[!UICONTROL Web API]** et l&#39;authentification **[!UICONTROL Certificat]**, vous devez fournir les informations suivantes :

   * **[!UICONTROL Serveur]** : URL de votre serveur Microsoft CRM.

   * **[!UICONTROL Clé privée (encodée en Base64)]** : clé privée encodée en Base64

   * **[!UICONTROL Identifiant de clé personnalisé]**

   * **[!UICONTROL ID de clé]**

   * **[!UICONTROL Identifiant du client]** : ID du client qui se trouve sur le portail de gestion Microsoft Azure au niveau de la catégorie **[!UICONTROL Mettre à jour votre code]**, dans le champ **[!UICONTROL ID du client]**.

   * **[!UICONTROL Version du CRM]** : version du CRM, **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** ou **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   Le compte externe **[!UICONTROL Salesforce CRM]** vous permet d&#39;importer et d&#39;exporter des données Salesforce vers Adobe Campaign.

   Pour configurer le compte externe Salesforce CRM afin de l&#39;utiliser avec Adobe Campaign, vous devez fournir les détails suivants :

   * **[!UICONTROL Compte]** : compte utilisé pour se connecter à Salesforce CRM

   * **[!UICONTROL Mot de passe]** : mot de passe utilisé pour se connecter à Salesforce CRM.

   * **[!UICONTROL Identifiant du client]** : apprenez à trouver votre identifiant client en consultant [cette page](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Jeton de sécurité]** : apprenez à trouver votre jeton de sécurité en consultant [cette page](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Version de l&#39;API]** : sélectionnez la version de l&#39;API. Pour ce compte externe, vous devez configurer votre Salesforce CRM à l&#39;aide de l&#39;assistant de configuration.

## Comptes externes de transfert de données

Ces comptes externes peuvent être utilisés pour importer ou exporter des données vers Adobe Campaign à l&#39;aide d&#39;une activité de workflow **[!UICONTROL Transfert de fichier]**.

[!DNL :arrow_upper_right:] Apprenez-en davantage sur le transfert de fichier dans les workflows dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html?lang=fr)

* **FTP et SFTP**

   Le compte externe **FTP** vous permet de configurer et de tester l&#39;accès à un serveur en dehors d&#39;Adobe Campaign. Pour configurer des connexions avec des systèmes externes comme des serveurs SFTP ou FTP 898 utilisés pour les transferts de fichiers, vous pouvez créer vos propres comptes externes.
Pour ce faire, spécifiez dans ce compte externe l&#39;adresse et les informations de connexion utilisées pour établir la connexion au serveur SFTP ou FTP.

* **Amazon Simple Storage Service (S3)**

   Le connecteur **AWS S3** peut être utilisé pour importer ou exporter des données vers Adobe Campaign à l&#39;aide d&#39;une activité de workflow **[!UICONTROL Transfert de fichier]**. Lors de la configuration de ce nouveau compte externe, vous devez indiquer les informations suivantes :

   * **[!UICONTROL Serveur du compte AWS S3]** : URL de votre serveur, renseignée comme suit :   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL ID de la clé d&#39;accès AWS]** : apprenez à trouver votre ID de clé d&#39;accès AWS en consultant la [documentation Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

   * **[!UICONTROL Clé d&#39;accès secrète à AWS]** : apprenez à trouver votre clé d&#39;accès secrète à AWS en consultant la [documentation Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL Région AWS]** : pour en savoir plus sur les régions AWS, consultez la [documentation Amazon](https://aws.amazon.com/fr/about-aws/global-infrastructure/regions_az/).

   * La case à cocher **[!UICONTROL Utiliser le cryptage coté serveur]** vous permet de stocker votre fichier en mode crypté dans S3. Apprenez à trouver l&#39;ID de clé d&#39;accès et la clé d&#39;accès secrète en consultant la [documentation Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Stockage Azure Blob**

   Le compte externe **Azure** peut être utilisé pour importer ou exporter des données vers Adobe Campaign à l&#39;aide d&#39;une activité de workflow **[!UICONTROL Transfert de fichier]**. Pour configurer le compte externe **Azure** afin de l&#39;utiliser avec Adobe Campaign, vous devez fournir les informations suivantes :

   * **[!UICONTROL Serveur]** : URL de votre serveur de stockage Azure Blob.

   * **[!UICONTROL Chiffrement]** : type de chiffrement, **[!UICONTROL Aucun]** ou **[!UICONTROL SSL]**.

   * **[!UICONTROL Clé d&#39;accès]** : apprenez à trouver votre **[!UICONTROL clé d&#39;accès]** en consultant la [documentation Microsoft](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).

