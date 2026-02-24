---
title: Bonnes pratiques de sécurité de Campaign
description: Conseils de configuration sécurisée recommandés pour Campaign
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: 04dff810f5a838b2468280519948c88e29acf221
workflow-type: tm+mt
source-wordcount: '2875'
ht-degree: 67%

---

# Bonnes pratiques de sécurité de Campaign {#ac-security}

Chez Adobe, nous prenons la sécurité de votre expérience digitale très au sérieux. Les bonnes pratiques de sécurité sont profondément ancrées dans nos processus internes de développement et d&#39;exploitation de logiciels ainsi que dans nos outils. Nos équipes transverses suivent scrupuleusement ces différentes règles afin d&#39;éviter les incidents, mais aussi de pouvoir les détecter et y répondre rapidement.

De plus, notre travail en collaboration avec des partenaires, des chercheurs de premier plan, des instituts de recherche en sécurité et d&#39;autres organisations du secteur nous aide à nous tenir informés des dernières menaces et vulnérabilités. Nous incorporons ainsi régulièrement des techniques de sécurité avancées à nos produits et services.

>[!NOTE]
>
>**Managed Cloud Services de Campaign v8 : l’infrastructure** (réseau, serveur, TLS, application de correctifs) est gérée par Adobe. Cette page porte sur la configuration au niveau du client et de l’application que vous contrôlez : la gestion des accès, l’authentification, les paramètres d’instance, la protection des données, le codage et les pratiques opérationnelles.


## Liste de contrôle de sécurité {#security-checklist}

Utilisez cette liste de contrôle pour aligner votre configuration avec les valeurs par défaut sécurisées recommandées :

* [Gestion des accès](#access-management) : créez des groupes de sécurité, attribuez les droits appropriés, limitez l’utilisation par l’administrateur, un opérateur par utilisateur, vérifiez régulièrement
* [Authentification et session](#authentication-and-session) : utiliser Adobe IMS, politique d’identité forte, délai d’expiration de la session
* [Sécurité des instances et du réseau](#instance-and-network-security) : place sur la liste autorisée IP, autorisations d’URL, clés GPG par Panneau de Contrôle
* [Protection des données et des PII](#data-and-pii-protection) : HTTPS, limitation de l’affichage des PII, restriction des mots de passe, protection des pages sensibles
* [Instructions de codage &#x200B;](#coding-guidelines) : aucun secret codé en dur, validation de l’entrée, SQL paramétré, captchas
* [Restriction des données](#data-restriction) : limitez l’accès aux champs de mot de passe et de secret dans les comptes externes
* [Opérationnel et conformité](#operational-and-compliance) : comparez régulièrement cette ligne de base et utilisez le journal d’audit

### Où trouver ces conseils ? {#public-guidance}

Actuellement, Adobe Campaign ne fournit pas de conseils de configuration sécurisée recommandés dans un format lisible par machine. Vous pouvez utiliser la documentation suivante pour comparer vos paramètres actuels aux paramètres sécurisés par défaut recommandés :

* **Cette page** - [Bonnes pratiques de sécurité de Campaign](#ac-security) (liste de contrôle et sections détaillées)
* **[Paramètres de Campaign (FAQ)](../start/campaign-faq-comprehensive.md#settings)** - Comparez les paramètres aux paramètres sécurisés par défaut recommandés
* **[Module complémentaire de sécurité renforcée](enhanced-security.md)** - Intégration CMK sécurisée et tunneling VPN sécurisé
* **[Prise en main des autorisations](../start/gs-permissions.md)** - Accès et profils de produits
* **[Limitation de l’affichage des PII](../dev/restrict-pi-view.md)** - Limitation de l’accès aux champs sensibles
* **[Instructions d’implémentation](../start/implement.md)** - Sécurité et confidentialité avant de commencer

## Confidentialité

Pour gérer correctement la confidentialité et les données personnelles, travaillez dans le cadre des législations applicables aux zones géographiques où vous intervenez. Les fonctionnalités d’Adobe Campaign vous aident à vous conformer aux réglementations répertoriées sur [cette page](../start/privacy.md).

### Confidentialité d&#39;Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign fait partie des solutions Adobe Experience Cloud. La façon dont la confidentialité est gérée dans Campaign obéit aux principes généraux d’Experience Cloud, tels que :

* **Informations collectées lors de l&#39;utilisation d&#39;Adobe Experience Cloud**

  En tant que société utilisant les solutions Adobe Experience Cloud, vous choisissez les informations à collecter et à envoyer à votre compte Adobe Experience Cloud. Parmi les types d&#39;informations pouvant être collectées, citons les activités de navigation sur le Web, les adresses IP, les informations de localisation des appareils mobiles, les taux de succès des campagnes, les articles achetés ou placés dans un panier, etc.

  >[!NOTE]
  >
  >Comme pour tous les produits Adobe, Campaign collecte des informations relatives aux utilisateurs d&#39;applications et de sites web. Pour plus d’informations, consultez la [Politique de confidentialité d&#39;Adobe](https://www.adobe.com/fr/privacy/policy.html).

* **Modalités de collecte des informations dans Adobe Experience Cloud**

   * Les solutions Adobe Experience Cloud utilisent des cookies et des technologies similaires, telles que les balises web (également appelées pixels), pour vous permettre de collecter des informations. Pour plus d’informations sur les cookies et les fonctionnalités de tracking avec Adobe Campaign, consultez [cette section](#tracking-capabilities).
   * Vous pouvez également utiliser les technologies Adobe Experience Cloud dans vos applications mobiles. Pour plus d’informations sur l’envoi de diffusions mobiles avec Campaign, consultez [canal SMS](../send/sms/sms-channel.md) et canal d’application mobile.

* **Choix de confidentialité de vos utilisateurs concernant votre utilisation d&#39;Adobe Experience Cloud**

  Adobe vous demande de fournir à vos clients des politiques de confidentialité décrivant :

   * Vos pratiques de confidentialité en rapport avec Adobe Experience Cloud
   * La manière dont les utilisateurs peuvent définir leurs préférences pour la collecte ou l&#39;utilisation de leurs informations en rapport avec Adobe Experience Cloud

Pour plus d’informations sur la confidentialité dans Adobe Experience Cloud, consultez [cette page](https://www.adobe.com/fr/privacy/marketing-cloud.html).

## Données personnelles et personnes concernées {#personal-data}

Pour la gestion des informations personnelles, il est important de définir les données à traiter avec soin et par qui.
* **Les données personnelles** sont des informations qui permettent d&#39;identifier directement ou indirectement un individu vivant.
* Les **données personnelles sensibles** sont des informations relatives à l’origine, aux points de vue politiques, aux croyances religieuses, aux antécédents criminels, aux informations génétiques, aux données sur la santé, aux préférences sexuelles, aux renseignements biométriques, ainsi qu’à l’appartenance syndicale.

Lors de l’intégration de Campaign à d’autres solutions Experience Cloud dans lesquelles des audiences peuvent être transférées d’un système à un autre, telles qu’[Adobe Analytics](../connect/ac-aa.md), [Audiences Experience Cloud](../start/shared-audiences.md), Campaign Standard, ou à d’autres solutions par l’intermédiaire d’un [connecteur CRM](../../automation/workflow/crm-connector.md), vous devez porter une attention particulière à la protection des données personnelles.

Les [principaux règlements](#privacy-regulations) se réfèrent de la manière suivante aux différentes entités chargées des données :

* Un **contrôleur de données** est l&#39;autorité qui détermine les moyens et les objectifs de la collecte, de l&#39;utilisation et du partage des données personnelles.

* Un **responsable du traitement des données** est un individu ou une partie qui collecte, utilise ou partage des données personnelles selon les instructions du contrôleur de données.

* Un **titulaire de données** est une personne vivante dont les données à caractère personnel sont collectées, utilisées ou partagées et qui peut être identifiée, directement ou indirectement, par référence à ces données à caractère personnel.

Ainsi, en tant qu’entreprise qui collecte et partage des données personnelles, vous êtes le contrôleur de données, vos clients sont les titulaires de données et Adobe Campaign agit comme un responsable du traitement des données lors du traitement des données personnelles des clients selon vos instructions. Notez qu’en tant que contrôleur de données, il vous appartient de gérer les relations avec les titulaires de données, par exemple lors de la gestion des [demandes d’accès à des informations personnelles](#privacy-requests). 

### Scénario d’utilisation {#use-case-scenario}

Pour illustrer l’interaction entre les différentes personnes, voici un exemple général de cas d’utilisation d’expérience client de RGPD de haut niveau.

Dans cet exemple, une compagnie aérienne est le client Adobe Campaign. Cette société est le **contrôleur de données** et tous les clients de la compagnie aérienne sont **titulaires de données**. Dans ce cas particulier, Laura est une cliente de la compagnie aérienne.

Voici les différentes personnes utilisées dans cet exemple :

* **Laura** est la **titulaire de données**. Elle reçoit les messages de la compagnie aérienne. Laura voyage peut-être fréquemment, mais elle peut décider à un moment donné de ne pas recevoir de publicité personnalisée ou de messages marketing de la part de la compagnie aérienne. Elle demandera à la compagnie aérienne (selon leur processus) de supprimer son numéro de vol fréquent.

* **Anne** est le **contrôleur de données** de la compagnie aérienne. Elle reçoit la demande de Laura, récupère les identifiants utiles requis pour identifier la personne titulaire de données et soumet la demande dans Adobe Campaign.

* **Adobe Campaign** est le **responsable du traitement des données**.

![](assets/privacy-gdpr-flow.png)

Voici le flux général de ce cas pratique :

1. La **titulaire de données** (Laura) envoie une demande RGPD au **contrôleur de données**, par le biais d’un e-mail, de l’assistance clientèle ou d’un portail web.

1. Le **contrôleur de données** (Anne) transmet la demande RGPD à Campaign via l’interface ou à l’aide d’une API.

1. Lorsque la personne **responsable du traitement des données** (Adobe Campaign) reçoit les informations, elle traite la demande RGPD et envoie une réponse ou un accusé de réception à la personne en charge du **contrôle des données** (Anne).

1. Le **contrôleur de données** (Anne) examine ensuite les informations et les renvoie au **titulaire de données** (Laura).

## Acquisition de données {#data-acquisition}

Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel de recevoir et surveiller le consentement de vos destinataires.

* Demandez toujours aux destinataires d&#39;accepter de recevoir des communications. Pour ce faire, continuez à honorer les demandes d&#39;opt-out le plus rapidement possible et vérifiez le consentement par le biais d&#39;un processus de double opt-in. Pour plus d&#39;informations à ce sujet, voir [Créer un formulaire d&#39;abonnement avec double opt-in](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}.
* N&#39;importez pas de listes frauduleuses et utilisez des adresses de contrôle pour vérifier que votre fichier client n&#39;est pas utilisé de façon frauduleuse. Pour plus d’informations à ce sujet, voir [À propos des adresses de contrôle](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank}.
* Grâce à la gestion des droits et du consentement, vous pouvez tracker les préférences de vos destinataires et gérer les données correspondantes et les utilisateurs de votre organisation qui peuvent y accéder. Voir à ce propos [cette section](#consent).
* Faciliter et gérer les demandes d&#39;accès à des informations personnelles de vos destinataires. Voir à ce propos [cette section](#privacy-requests).

## Gestion de la confidentialité {#privacy-management}

La gestion de la confidentialité se rapporte à tous les processus et outils qui peuvent vous aider à vous conformer aux règlements relatifs à la confidentialité (RGPD, CCPA, etc.).

Adobe Campaign vous propose divers ensembles de fonctionnalités dédiées à la gestion de la confidentialité :
* Gestion du consentement, conservation des données et rôles utilisateur. Voir [cette section](#consent).
* Demandes d&#39;accès à des informations personnelles (droit d&#39;accès et droit à l&#39;oubli). Voir [cette section](#privacy-requests).
* Droit d’opposition (opt-out) à la vente des informations personnelles (spécifique au règlement CCPA).

Les principales fonctionnalités de confidentialité relatives à Campaign et un exemple des acteurs impliqués sont présentés dans [cette section](https://helpx.adobe.com/fr/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).

### Consentement, conservation des données et rôles {#consent}

Depuis l’origine, Adobe Campaign dispose de fonctions importantes, essentielles pour la confidentialité :

* **Gestion du consentement** : grâce au processus de gestion des abonnements, vous pouvez gérer vos préférences de destinataires et déterminer quels destinataires ont choisi quel type d&#39;abonnement. Pour plus d’informations, consultez la section [À propos des abonnements](../../automation/workflow/subscription-services.md).
* **Conservation des données** : toutes les tables de journalisation standard natives comportent des périodes de rétention prédéfinies, limitant généralement le stockage de leurs données à 6 mois maximum. Il est possible de définir des périodes de conservation supplémentaires à l&#39;aide de workflows. Pour en savoir plus, contactez les consultants Adobe ou les administrateurs techniques.
* **Gestion des droits** : Adobe Campaign permet de gérer les droits affectés aux divers opérateurs Campaign par l’intermédiaire de différents rôles préconfigurés ou personnalisés. Vous pouvez ainsi gérer qui, dans votre entreprise, peut accéder à différents types de données, les modifier ou les exporter. Pour plus d’informations à ce sujet, consultez la section [À propos de la gestion des accès](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}.

### Demandes d&#39;accès à des informations personnelles  {#privacy-requests}

Adobe Campaign dispose de fonctionnalités supplémentaires pour vous aider à vous préparer, en tant que contrôleur de données, à certaines demandes d’accès à des informations personnelles :

* Le **droit d’accès** permet au titulaire de données de demander au contrôleur de données si les données personnelles le concernant sont traitées ou non, et lorsqu’elles le sont, où et à quelles fins.

* Le **Droit à l’oubli** (demande de suppression) autorise le titulaire de données à demander au contrôleur de données d’effacer ses données personnelles.

Les demandes d&#39;**accès** et de **suppression** sont présentées dans [cette section](../start/privacy.md).

La procédure de création de ces demandes est pour sa part détaillée sur [cette page](../start/privacy.md).

## Fonctionnalités de tracking {#tracking-capabilities}

### Cookies {#cookies}

Grâce à ses fonctionnalités de suivi, Adobe Campaign vous permet de suivre la navigation de vos destinataires de diffusion en utilisant trois types de cookies : un cookie de session et deux cookies permanents.

* Un cookie de **session** : le cookie **nlid** contient l&#39;identifiant de l&#39;email envoyé au contact (**broadlogId**) et l&#39;identifiant du modèle de message (**deliveryId**). Il est déposé lorsque le contact clique sur une URL contenue dans un e-mail envoyé par Adobe Campaign et permet de suivre son comportement sur le web. Ce cookie de session est effacé automatiquement à la fermeture du navigateur. Le contact a la possibilité d&#39;en interdire le dépôt en adaptant les paramètres de son navigateur.

* Deux cookies **permanents** :
   * Le cookie **UUID** (Universal Unique IDentifier) est partagé entre les solutions Adobe Experience Cloud. Il est défini une fois jusqu’à ce qu’il disparaisse du navigateur client lorsqu’une nouvelle valeur est générée. Il permet d&#39;identifier un internaute qui interagit avec les solutions Experience Cloud lors de ses visites sur un site web. Il peut être déposé par une landing page (pour associer des activités de clients inconnues à un destinataire) ou par une diffusion. La description de ce cookie est disponible dans [cette page](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html?lang=fr#ec-cookies).
   * Le cookie **nllastdelid** (introduit dans Campaign Classic 20.3) est un cookie permanent qui contient l&#39;identifiant **deliveryId** de la dernière diffusion d&#39;où l&#39;utilisateur a cliqué sur le lien. Ce cookie est utilisé - lorsque le cookie de session est manquant - pour identifier la table de tracking qui sera utilisée.

Des règlements, tels que le Règlement général sur la protection des données (RGPD), imposent aux entreprises d’obtenir l’accord des utilisateurs du site web avant d’installer des cookies.

* Les fenêtres de type pop-up sont à éviter car elles sont souvent bloquées par les navigateurs.

### Tracking des messages {#message-tracking}

Adobe Campaign vous permet de suivre les e-mails envoyés et le comportement de vos destinataires de diffusion : ouverture, clics sur des liens, désinscriptions, etc. Pour obtenir davantage de renseignements, consultez la section [À propos des messages](../start/gs-message.md).

Pour ce faire, ajoutez des liens suivis à vos messages afin de mesurer l’impact de votre diffusion et le comportement de la personne destinataire dans l’onglet Tracking du tableau de bord de diffusion. Les données de suivi sont interprétées dans le rapport des indicateurs de tracking. Pour en savoir plus sur le tracking, reportez-vous à [cette page](../send/tracking.md).

### Tracking web {#web-tracking}

>[!AVAILABILITY]
>
>Le tracking web n’est pas disponible dans Campaign v8. En savoir plus sur les fonctionnalités non disponibles sur [cette page](../start/v7-to-v8.md#gs-unavailable-features).

## Protection des données et des PII {#data-and-pii-protection}

La configuration et le renforcement de la confidentialité sont des éléments clés en matière d&#39;optimisation de la sécurité. Suivez ces bonnes pratiques :

* **Utiliser HTTPS pour tous les points d’entrée** - Assurez-vous que tous les points d’entrée utilisés par Campaign (suivi, page miroir, applications web, API) sont diffusés via HTTPS.
* **Limitation de l’affichage des PII** - Utilisez la fonction [Limitation de l’affichage des PII](../dev/restrict-pi-view.md) afin que seuls les opérateurs autorisés puissent voir les champs sensibles (par exemple, e-mail, téléphone) dans les schémas et les écrans.
* **Restreindre l’accès aux mots de passe chiffrés** - Restreignez l’accès aux champs de mot de passe et de secret dans les comptes externes et autres schémas afin que seuls les administrateurs ou un ensemble minimal d’opérateurs puissent les afficher. Voir [Restriction des données](#data-restriction) ci-dessous.
* **Protection des pages sensibles** - Limitez l’accès aux pages miroir, aux applications web et aux pages de destination qui affichent ou collectent des informations d’identification personnelles ; utilisez des autorisations d’opérateur et de dossier et, le cas échéant, captchas et consentement.

>[!NOTE]
>
>En tant qu’utilisateur ou utilisatrice Managed Cloud Services, Adobe vous accompagne dans l’implémentation de ces configurations dans votre environnement.

## Gestion des accès {#access-management}

La gestion des accès est un aspect important du renforcement de la sécurité. Les bonnes pratiques principales sont les suivantes :

* **Créer suffisamment de groupes de sécurité** - Définissez des groupes d’opérateurs correspondant aux rôles et attribuez uniquement les droits dont chaque rôle a besoin.
* **Vérifier que chaque opérateur dispose des droits d&#39;accès adéquats** - Appliquer le principe de moindre privilège ; éviter d&#39;accorder par défaut des droits d&#39;ADMINISTRATION ou autres droits étendus.
* **Évitez d’utiliser l’opérateur administrateur et d’avoir trop d’opérateurs dans le groupe administrateur** - Ne partagez pas le compte administrateur intégré ; créez un opérateur par utilisateur physique pour la responsabilité et l’audit.
* **Un opérateur par utilisateur physique** - Ne partagez pas de comptes. Créez un opérateur Campaign (Adobe ID) par personne pour que les journaux d’audit et les logs soient attribuables.
* **Limiter les droits nommés à privilège élevé** - N’accordez les **ADMINISTRATION**, **EXÉCUTION DU PROGRAMME** (createProcess) et **SQL** qu’à un petit nombre d’opérateurs approuvés ; indiquez qui les possède et pourquoi.
* **Consulter régulièrement l’accès** - Consulter régulièrement les opérateurs, les groupes d’opérateurs et les autorisations de dossiers ; supprimer ou réduire l’accès lorsque les rôles changent ou que des personnes quittent.
* **Utiliser les profils de produit de manière cohérente** - Préférez l’affectation d’utilisateurs aux profils de produit (groupes d’opérateurs) dans Admin Console ; veillez à la cohérence des noms (par exemple, `campaign - <instance> - <group>`). Voir [Prise en main des autorisations](../start/gs-permissions.md).
* **Accès au Panneau de Contrôle** - Dans Campaign v8, les profils de produit ou les droits nommés dont le nom contient « admin » peuvent accorder l’accès au Panneau de Contrôle Campaign. Évitez d’utiliser « admin » dans les noms de profil ou de groupe, sauf si ces utilisateurs doivent disposer d’un accès en Panneau de Contrôle.

Pour en savoir plus sur les autorisations, consultez [cette section](../start/gs-permissions.md).

## Authentification et session {#authentication-and-session}

* **Utilisation d’Adobe IMS** - Tous les utilisateurs doivent se connecter avec leur Adobe ID (IMS) ; ne vous fiez pas aux comptes de connexion/mot de passe hérités pour les opérateurs quotidiens.
* **Fiez-vous à une politique d’identité et de mot de passe forte** - Utilisez Admin Console ou votre fournisseur d’identité pour la politique d’authentification multifacteur et de mot de passe. Assurez-vous que seuls les utilisateurs autorisés sont affectés aux profils de produits Campaign.
* **Configurer le délai d’expiration de la session** - Lorsqu’il est configurable (par exemple, la console cliente), définissez un délai d’expiration de session raisonnable et verrouillez l’écran lorsque vous quittez la station de travail.

## Sécurité des instances et du réseau {#instance-and-network-security}

En tant qu’administrateur ou administratrice de produit Campaign v8, utilisez [Panneau de Contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr){target="_blank"} pour gérer la sécurité au niveau de l’instance :

* **place sur la liste autorisée IP** - Gérez la liste autorisée IP pour l&#39;accès aux instances ; limitez-la aux réseaux connus (par exemple bureau, VPN) et évitez autant que possible les plages trop larges.
* **Autorisations d’URL** - Restreignez les autorisations d’URL aux domaines que votre instance doit appeler (API, tracking, services externes) pour réduire le risque d’utilisation abusive des requêtes côté serveur.
* **Clés GPG** - Si vous utilisez le chiffrement pour les transferts de fichiers ou d’autres cas d’utilisation, gérez les clés GPG par Panneau de Contrôle et faites-les pivoter en fonction de votre politique de sécurité.

## Instructions de codage {#coding-guidelines}

Lorsque vous effectuez des tâches de développement dans Adobe Campaign (workflows, Javascript, JSSP, autres), suivez toujours ces instructions :

* **Scripts** - Essayez d’éviter le SQL brut ; utilisez des fonctions paramétrées au lieu de la concaténation de chaîne. Évitez l’injection SQL en ajoutant uniquement les fonctions SQL nécessaires à la liste autorisée de données.
* **Sécuriser le modèle de données** - Utilisez des droits nommés pour limiter les actions des opérateurs et ajouter des filtres système (sysFilter).
* **Ajout de captchas dans les applications web** - Ajoutez des captchas aux pages d’abonnement et aux pages de destination publiques.
* **Ne pas coder en dur les secrets** - Ne codez pas en dur les mots de passe, les clés API ou les jetons dans les workflows, JavaScript ou JSSP. Utilisez des comptes externes ou une configuration sécurisée.
* **Valider et assainir l’entrée** - Validez et assainissez l’entrée utilisateur dans les applications web et les paramètres de workflow pour réduire les risques d’injection et XSS.
* **Utiliser la liste autorisée pour SQL** - Lorsque l’exécution de code SQL ou de script est requise, utilisez la liste autorisée pour les fonctions SQL autorisées et évitez de créer des requêtes à partir d’une entrée utilisateur via la concaténation de chaîne.

En savoir plus dans la [documentation d’Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=fr#installing-campaign-classic){target="_blank"}.


## Personnalisation

Lorsque vous ajoutez des liens personnalisés à votre contenu, évitez toujours toute personnalisation dans la partie du nom d&#39;hôte de l&#39;URL afin d&#39;éviter des failles de sécurité potentielles. Les exemples suivants ne doivent jamais être utilisés dans tous les attributs d’URL &lt;`a href="">` ou `<img src="">` :

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restriction des données {#data-restriction}

Vous devez vous assurer que les mots de passe chiffrés ne sont pas accessibles par une personne authentifiée disposant de privilèges restreints. Pour ce faire, il existe deux méthodes : restreindre l&#39;accès aux champs de mots de passe uniquement ou à l&#39;entité entière.

Cette restriction vous permet de supprimer les champs de mots de passe. Le compte externe reste toutefois accessible par tous les utilisateurs dans l&#39;interface. En savoir plus à ce propos sur [cette page](../dev/restrict-pi-view.md).

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Schémas de données]**.

1. Créez une **[!UICONTROL Extension d&#39;un schéma]**.

1. Sélectionnez **[!UICONTROL Compte externe]** (extAccount).

1. Dans le dernier écran, vous pouvez modifier le nouveau srcSchema afin de restreindre l&#39;accès à tous les champs de mots de passe :

   Vous pouvez remplacer l&#39;élément principal (`<element name="extAccount" ... >`) par :

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   Le srcSchema étendu peut ressembler à ceci :

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >Vous pouvez remplacer `$(loginId) = 0 or $(login) = 'admin'` par `hasNamedRight('admin')` pour autoriser tous les utilisateurs disposant du droit admin à voir ces mots de passe.

## Opérationnel et conformité {#operational-and-compliance}

* **Comparer à la ligne de base sécurisée** - Comparez régulièrement vos groupes d’opérateurs, vos droits nommés et vos autorisations de dossiers aux recommandations de cette page (et, le cas échéant, du [module complémentaire de sécurité renforcée](enhanced-security.md)) pour vous aligner sur les valeurs par défaut sécurisées recommandées.
* **Utiliser le journal d’audit** - Fiez-vous au journal d’audit de Campaign pour les modifications importantes (par exemple, les workflows, les diffusions, la configuration des clés) ; conservez et examinez les journaux comme l’exige votre politique de conformité et de conservation.
