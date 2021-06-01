---
product: Adobe Campaign
title: Comptes externes de Campaign
description: Comptes externes de Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: ff2c49a2b4f22cde7ebb798d9f565e133c0268fc
workflow-type: tm+mt
source-wordcount: '1124'
ht-degree: 35%

---


# Configuration de vos comptes externes

Un ensemble de comptes externes prédéfinis est livré avec Adobe Campaign. Pour établir des connexions avec des systèmes externes, vous pouvez créer des comptes externes.

Les comptes externes sont utilisés par les processus techniques comme les workflows techniques ou de campagne. Par exemple, lors de la configuration d’un transfert de fichier dans un workflow ou d’un échange de données avec une autre application (Adobe Target, Experience Manager, etc.), vous devez sélectionner un compte externe.

Vous pouvez accéder aux comptes externes à partir de l’**[!UICONTROL Explorateur]** Adobe Campaign : Accédez à **[!UICONTROL Administration]** `>` **[!UICONTROL Plateforme]** `>` **[!UICONTROL Comptes externes]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Un compte externe **[!UICONTROL FDA]** (ffda) spécifique gère la connexion entre la base de données locale Campaign et la base de données Cloud ([!DNL Snowflake]).
>
>En tant qu’utilisateur Cloud Services géré, ce compte externe est configuré par Adobe pour votre instance. Il ne doit pas être modifié.


## Comptes externes spécifiques à une campagne

Adobe Campaign utilise les comptes techniques suivants pour activer et exécuter des processus spécifiques.

[!DNL :speech_balloon:] En tant qu’utilisateur Cloud Services géré, Adobe configurez tous les comptes externes spécifiques à Campaign pour vous.

* **Emails bounce (POP3)**

   Le compte externe **Mails rebonds** spécifie le compte externe POP3 à utiliser pour se connecter au service de messagerie. Tous les serveurs configurés pour l&#39;accès POP3 peuvent être utilisés pour recevoir les retours d&#39;email.

   [!DNL :arrow_upper_right:] En savoir plus sur les emails entrants dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html)

* **Routage**

   Le compte externe **[!UICONTROL Routage]** vous permet de configurer chaque canal disponible dans Adobe Campaign en fonction des packages installés.

   >[!CAUTION]
   >
   >Le **[!UICONTROL compte externe de routage de diffusion email interne]** (defaultEmailBulk) **ne doit pas** être activé dans Adobe Campaign v8.

* **Instance d’exécution**

   Dans le contexte des messages transactionnels, les instances d&#39;exécution sont liées à l&#39;instance de pilotage et connectent-les. Les modèles de messages transactionnels sont déployés sur l’instance d’exécution.

   [!DNL :bulb:] Pour en savoir plus sur l&#39;architecture de Message Center, consultez  [cette page](../dev/architecture.md#transac-msg-archi).

## Accès aux comptes externes des systèmes externes

* **Base de données externe (FDA)**

   Utilisez le compte externe de type **Base externe** pour vous connecter à une base externe via FDA.

   Les bases de données externes compatibles avec Adobe Campaign v8 sont répertoriées dans la [matrice de compatibilité](../start/compatibility-matrix.md)

   [!DNL :bulb:] En savoir plus sur l&#39;option Federated Data Access (FDA) dans [cette section](../connect/fda.md).

## Comptes externes d’intégration de solution Adobe

* **Adobe Experience Cloud**

   Pour vous connecter à la console Adobe Campaign à l’aide d’un Adobe ID, vous devez configurer le compte externe **[!UICONTROL Adobe Experience Cloud]**.

   [!DNL :bulb:] En savoir plus sur Adobe Identity Management Service (IMS) dans  [cette section](../start/connect.md#connect-ims).

   [!DNL :speech_balloon:] En tant qu’utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour implémenter Adobe IMS avec Campaign.

* **Web Analytics**

   Utilisez le compte externe **[!UICONTROL Web Analytics (Adobe Analytics)]** pour configurer le transfert de données d’Adobe Analytics vers Adobe Campaign.

   [!DNL :bulb:] Pour en savoir plus sur l’intégration Adobe Campaign - Adobe Analytics, consultez  [cette page](../connect/ac-aa.md).

   [!DNL :speech_balloon:] En tant qu’utilisateur Cloud Services géré,  [contactez ](../start/campaign-faq.md#support) Adobe pour intégrer Adobe Analytics à Campaign.

   * **Adobe Experience Manager**
   Le compte externe **[!UICONTROL AEM]** vous permet de gérer le contenu de vos diffusions email, ainsi que vos formulaires directement dans Adobe Experience Manager.

   [!DNL :bulb:] Pour en savoir plus sur l’intégration Adobe Campaign - Adobe Analytics, consultez  [cette page](../connect/ac-aem.md).

   [!DNL :speech_balloon:] En tant qu’utilisateur Cloud Services géré,  [contactez ](../start/campaign-faq.md#support) Adobe pour intégrer Adobe Experience Manager à Adobe Campaign.


## Comptes externes du connecteur CRM

* **Microsoft Dynamics CRM**

   Le compte externe **[!UICONTROL Microsoft Dynamics CRM]** vous permet d&#39;importer et d&#39;exporter des données Microsoft Dynamics vers Adobe Campaign.

   [!DNL :bulb:] En savoir plus sur l&#39;intégration Adobe Campaign - Microsoft Dynamics CRM dans  [cette page](../connect/crm.md).

   Avec le type de déploiement **[!UICONTROL Web API]** et l&#39;authentification **[!UICONTROL Informations de connexion et mot de passe]**, vous devez fournir les détails suivants :

   * **[!UICONTROL Compte]** : Compte utilisé pour se connecter à Microsoft CRM.

   * **[!UICONTROL Serveur]** : URL de votre serveur Microsoft CRM.

   * **[!UICONTROL Identifiant]** du client : Identifiant du client qui se trouve sur le portail de gestion Microsoft Azure dans le champ  **[!UICONTROL Mettre à jour votre]** catégorie de codecategory,  **** identifiant du client .

   * **[!UICONTROL Version]** CRM : Version du CRM entre  **[!UICONTROL Dynamics CRM 2007]**,  **[!UICONTROL Dynamics CRM 2015]**  ou  **[!UICONTROL Dynamics CRM 2016]**.
   Avec le type de déploiement **[!UICONTROL Web API]** et l&#39;authentification **[!UICONTROL Certificat]**, vous devez fournir les détails suivants :

   * **[!UICONTROL Serveur]** : URL de votre serveur Microsoft CRM.

   * **[!UICONTROL Clé privée (encodée en Base64)]** : Clé privée encodée en Base64

   * **[!UICONTROL Identifiant de clé personnalisé]**

   * **[!UICONTROL ID de clé]**

   * **[!UICONTROL Identifiant du client]**: ID du client qui se trouve sur le portail de gestion Microsoft Azure au niveau de la catégorie **[!UICONTROL Mettre à jour votre code]**, dans le champ **[!UICONTROL ID du client]**.

   * **[!UICONTROL Version]** CRM : Version du CRM entre  **[!UICONTROL Dynamics CRM 2007]**,  **[!UICONTROL Dynamics CRM 2015]**  ou  **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   Le compte externe **[!UICONTROL Salesforce CRM]** vous permet d&#39;importer et d&#39;exporter des données Salesforce vers Adobe Campaign.

   Pour configurer le compte externe Salesforce CRM afin de l&#39;utiliser avec Adobe Campaign, vous devez fournir les détails suivants :

   * **[!UICONTROL Compte]** : Compte utilisé pour se connecter à Salesforce CRM.

   * **[!UICONTROL Mot de passe]** : Mot de passe utilisé pour se connecter à Salesforce CRM.

   * **[!UICONTROL Identifiant]** du client : Découvrez comment trouver votre identifiant client dans  [cette page](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Jeton]** de sécurité : Découvrez comment trouver votre jeton de sécurité dans  [cette page](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Version]** de l’API : Sélectionnez la version de l’API. Pour ce compte externe, vous devez configurer votre Salesforce CRM à l&#39;aide de l&#39;assistant de configuration.

## Transfert des comptes externes de données

Ces comptes externes peuvent être utilisés pour importer ou exporter des données vers Adobe Campaign à l’aide d’une activité de workflow **[!UICONTROL Transfert de fichier]** .

[!DNL :arrow_upper_right:] En savoir plus sur le transfert de fichier dans les workflows dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html)

* **FTP et SFTP**

   Le compte externe **FTP** vous permet de configurer et de tester l’accès à un serveur en dehors d’Adobe Campaign. Pour configurer des connexions à des systèmes externes tels que des serveurs SFTP ou FTP 898 utilisés pour les transferts de fichiers, vous pouvez créer vos propres comptes externes.
Pour ce faire, indiquez dans ce compte externe l’adresse et les informations d’identification utilisées pour établir la connexion au serveur SFTP ou FTP.

* **Amazon Simple Storage Service (S3)**

   Le connecteur **AWS S3** peut être utilisé pour importer ou exporter des données vers Adobe Campaign à l’aide d’une activité de workflow **[!UICONTROL Transfert de fichier]**. Lors de la configuration de ce nouveau compte externe, vous devez indiquer les informations suivantes :

   * **[!UICONTROL Serveur du compte AWS S3]**: URL de votre serveur, renseignée comme suit :   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL ID]** de la clé d&#39;accès AWS : Découvrez comment trouver votre ID de clé d’accès AWS dans la documentation  [Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Clé d’accès secrète à AWS]** : Découvrez comment trouver votre clé d’accès secrète à AWS dans la documentation  [Amazon](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL Région]** AWS : Pour en savoir plus sur les régions AWS, consultez la documentation  [Amazon](https://aws.amazon.com/fr/about-aws/global-infrastructure/regions_az/).

   * La case à cocher **[!UICONTROL Utiliser le cryptage coté serveur]** vous permet de stocker votre fichier en mode crypté dans S3. Découvrez comment trouver l’ID de clé d’accès et la clé d’accès secrète dans la [documentation Amazon](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Stockage Azure Blob**

   Le compte externe **Azure** peut être utilisé pour importer ou exporter des données vers Adobe Campaign à l’aide d’une activité de workflow **[!UICONTROL Transfert de fichier]**. Pour configurer le **** compte externe Azure afin de l’utiliser avec Adobe Campaign, vous devez fournir les détails suivants :

   * **[!UICONTROL Serveur]** : URL de votre serveur de stockage Azure Blob.

   * **[!UICONTROL Chiffrement]** : Type de chiffrement entre  **** Non ou  **[!UICONTROL SSL]**.

   * **[!UICONTROL Clé]** d’accès : Découvrez comment trouver votre  **[!UICONTROL clé]** d’accès dans la documentation  [Microsoft](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).

