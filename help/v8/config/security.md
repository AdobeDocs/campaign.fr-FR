---
title: Bonnes pratiques de sécurité de Campaign
description: Prise en main des bonnes pratiques de sécurité de Campaign
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '2280'
ht-degree: 90%

---

# Bonnes pratiques de sécurité de Campaign {#ac-security}

Chez Adobe, nous prenons la sécurité de votre expérience digitale très au sérieux. Les bonnes pratiques de sécurité sont profondément ancrées dans nos processus internes de développement et d&#39;exploitation de logiciels ainsi que dans nos outils. Nos équipes transverses suivent scrupuleusement ces différentes règles afin d&#39;éviter les incidents, mais aussi de pouvoir les détecter et y répondre rapidement.

De plus, notre travail en collaboration avec des partenaires, des chercheurs de premier plan, des instituts de recherche en sécurité et d&#39;autres organisations du secteur nous aide à nous tenir informés des dernières menaces et vulnérabilités. Nous incorporons ainsi régulièrement des techniques de sécurité avancées à nos produits et services.

## Confidentialité

Pour gérer correctement la confidentialité et les données personnelles, travaillez dans le cadre des législations applicables aux zones géographiques où vous intervenez. Les fonctionnalités d’Adobe Campaign vous aident à vous conformer aux réglementations répertoriées dans [cette page](../start/privacy.md)

### Confidentialité d&#39;Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign fait partie des solutions Adobe Experience Cloud. La façon dont la confidentialité est gérée dans Campaign obéit aux principes généraux d’Experience Cloud, tels que :

* **Informations collectées lors de l&#39;utilisation d&#39;Adobe Experience Cloud**

  En tant que société utilisant les solutions Adobe Experience Cloud, vous choisissez les informations à collecter et à envoyer à votre compte Adobe Experience Cloud. Parmi les types d&#39;informations pouvant être collectées, citons les activités de navigation sur le Web, les adresses IP, les informations de localisation des appareils mobiles, les taux de succès des campagnes, les articles achetés ou placés dans un panier, etc.

  >[!NOTE]
  >
  >Comme pour tous les produits Adobe, Campaign collecte des informations relatives aux utilisateurs d&#39;applications et de sites web. Pour plus d’informations, consultez la [Politique de confidentialité d&#39;Adobe](https://www.adobe.com/fr/privacy/policy.html).

* **Modalités de collecte des informations dans Adobe Experience Cloud**

   * Les solutions Adobe Experience Cloud utilisent des cookies et des technologies similaires, telles que les balises web (également appelées pixels), pour vous permettre de collecter des informations. Pour plus d’informations sur les cookies et les fonctionnalités de tracking avec Adobe Campaign, consultez [cette section](#tracking-capabilities).
   * Vous pouvez également utiliser les technologies Adobe Experience Cloud dans vos applications mobiles. Pour plus d’informations sur l’envoi de diffusions mobiles avec Campaign, voir [Canal SMS](../send/sms/sms-channel.md) et Canal des applications mobiles.

* **Choix de confidentialité de vos utilisateurs concernant votre utilisation d&#39;Adobe Experience Cloud**

  Adobe vous demande de fournir à vos clients des politiques de confidentialité décrivant :

   * Vos pratiques de confidentialité en rapport avec Adobe Experience Cloud
   * La manière dont les utilisateurs peuvent définir leurs préférences pour la collecte ou l&#39;utilisation de leurs informations en rapport avec Adobe Experience Cloud

  >[!NOTE]
  >
  >Pour tous les produits Adobe, les utilisateurs de Campaign peuvent s&#39;opposer (opt-out) au partage des informations collectées à leur sujet par le biais d&#39;applications et de sites web. Pour plus d’informations, consultez le [FAQ sur les informations d’utilisation d’Adobe Experience Cloud](https://www.adobe.com/fr/privacy/experience-cloud-usage-info-faq.html).

Pour plus d’informations sur la confidentialité dans Adobe Experience Cloud, consultez [cette page](https://www.adobe.com/fr/privacy/marketing-cloud.html).

## Données personnelles et personnes concernées {#personal-data}

Pour la gestion des informations personnelles, il est important de définir les données à traiter avec soin et par qui.
* **Les données personnelles** sont des informations qui permettent d&#39;identifier directement ou indirectement un individu vivant.
* Les **données personnelles sensibles** sont des informations relatives à l’origine, aux points de vue politiques, aux croyances religieuses, aux antécédents criminels, aux informations génétiques, aux données sur la santé, aux préférences sexuelles, aux renseignements biométriques, ainsi qu’à l’appartenance syndicale.

Lors de l’intégration de Campaign à d’autres solutions Experience Cloud dans lesquelles des audiences peuvent être transférées d’un système à un autre, comme [Adobe Analytics](../connect/ac-aa.md), [Experience Cloud Audiences](../start/shared-audiences.md), Campaign Standard ou avec d’autres solutions par l’intermédiaire de [Connecteur CRM](../../automation/workflow/crm-connector.md), vous devez veiller à la protection des données personnelles.

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
* Grâce à la gestion des droits et du consentement, vous pouvez tracker les préférences de vos destinataires et gérer les données correspondantes et les utilisateurs de votre organisation qui peuvent y accéder. Pour plus d’informations, consultez [cette section](#consent).
* Faciliter et gérer les demandes d&#39;accès à des informations personnelles de vos destinataires. Pour plus d’informations, consultez [cette section](#privacy-requests).

## Gestion de la confidentialité {#privacy-management}

La gestion de la confidentialité fait référence à tous les processus et outils qui peuvent vous aider à vous conformer aux règlements sur la confidentialité (RGPD, CCPA, etc.).

Adobe Campaign vous propose divers ensembles de fonctionnalités dédiées à la gestion de la confidentialité :
* Gestion du consentement, conservation des données et rôles utilisateur. Voir [cette section](#consent).
* Demandes d&#39;accès à des informations personnelles (droit d&#39;accès et droit à l&#39;oubli). Voir [cette section](#privacy-requests).
* Droit d’opposition (opt-out) à la vente des informations personnelles (spécifique au CCPA).

Les principales fonctionnalités de confidentialité relatives à Campaign et un exemple des acteurs impliqués sont présentés dans [cette section](https://helpx.adobe.com/fr/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).

### Consentement, conservation des données et rôles {#consent}

Depuis l’origine, Adobe Campaign dispose de fonctions importantes, essentielles pour la confidentialité :

* **Gestion du consentement** : grâce au processus de gestion des abonnements, vous pouvez gérer vos préférences de destinataires et déterminer quels destinataires ont choisi quel type d&#39;abonnement. Pour plus d’informations, consultez la section [À propos des abonnements](../../automation/workflow/subscription-services.md).
* **Conservation des données** : toutes les tables de journalisation standard natives comportent des périodes de rétention prédéfinies, limitant généralement le stockage de leurs données à 6 mois maximum. Il est possible de définir des périodes de conservation supplémentaires à l&#39;aide de workflows. Pour en savoir plus, contactez les consultants Adobe ou les administrateurs techniques.
* **Gestion des droits** : Adobe Campaign permet de gérer les droits affectés aux divers opérateurs Campaign par l’intermédiaire de différents rôles préconfigurés ou personnalisés. Vous pouvez ainsi gérer qui, dans votre entreprise, peut accéder à différents types de données, les modifier ou les exporter. Pour plus d’informations à ce sujet, consultez la section [À propos de la gestion des accès](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}.

### Demandes d&#39;accès à des informations personnelles {#privacy-requests}

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

* Ainsi, vous devez informer les utilisateurs de vos sites soumis au tracking web via une zone de demande de consentement (par exemple en surimpression de la page) proposant une case à cocher pour autoriser l&#39;utilisation de cookies, ou afficher une bannière en haut de la première page visitée, etc.
* Les fenêtres de type pop-up sont à éviter car elles sont souvent bloquées par les navigateurs.

### Tracking des messages {#message-tracking}

Adobe Campaign vous permet de suivre les emails envoyés et le comportement de vos destinataires de diffusion : ouverture, clics sur des liens, désinscriptions, etc. Pour plus d&#39;informations, consultez la section [À propos des messages](../start/gs-message.md).

Pour ce faire, ajoutez des liens suivis à vos messages afin de mesurer l&#39;impact de votre diffusion et du comportement du destinataire dans l&#39;onglet Tracking du tableau de bord de la diffusion. Les données de tracking sont interprétées dans le rapport Indicateurs de tracking . Pour en savoir plus sur le tracking, consultez [cette page](../start/tracking.md).

### Tracking web {#web-tracking}

Adobe Campaign vous permet également de contrôler la manière dont les destinataires naviguent sur votre site web : insérez des balises de tracking pour collecter des informations et mesurer les visites sur les pages d’applications web.

La configuration du tracking web est expliquée dans [cette section](../start/tracking.md).

Pour mieux gérer le tracking, Adobe Campaign vous permet d’afficher une bannière d’opt-out afin d’arrêter le tracking des comportements web des utilisateurs finaux qui se sont désinscrits du tracking comportemental. Pour plus d’informations, consultez la section [Désinscription (opt-out) du tracking des applications web](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out){target=_blank}.

<!--
Privacy configuration and hardening is a key element of security optimization. Here are some best practices to follow regarding privacy:

* Protect your customer Personal Information (PI) by using HTTPS instead of HTTP
* Use [PI view restriction](../dev/restrict-pi-view.md) to protect privacy and prevent data from being misused
* Make sure that encrypted passwords are restricted
* Protect the pages that might contain personal information such as mirror pages, web applications, etc.
-->

>[!NOTE]
>
>En tant qu’utilisateur ou utilisatrice Managed Cloud Services, Adobe vous accompagne dans l’implémentation de ces configurations dans votre environnement.


## Gestion des accès

La gestion des accès joue un rôle important dans le renforcement de la sécurité. Vous trouverez ci-dessous quelques-unes des principales bonnes pratiques à appliquer.

* Créez suffisamment de groupes de sécurité.
* Vérifiez que chaque opérateur dispose des droits d&#39;accès adéquats.

Pour en savoir plus sur les autorisations, consultez [cette section](../start/gs-permissions.md)

## Instructions de codage

Lorsque vous effectuez des tâches de développement dans Adobe Campaign (workflows, Javascript, JSSP, autres), suivez toujours ces instructions :

* **Scripts** : évitez si possible d&#39;utiliser des instructions SQL. Utilisez des fonctions paramétrables plutôt que la concaténation de chaîne et évitez toute injection SQL en ajoutant les fonctions SQL à utiliser à la liste autorisée.

* **Sécurisation du modèle de données** : utilisez des droits nommés pour limiter les actions des opérateurs et ajoutez des filtres système (sysFilter).

* **Ajout de captchas dans les applications web** : ajoutez des captchas dans vos pages d&#39;abonnement et landing pages publiques.

En savoir plus dans la documentation de [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=fr#installing-campaign-classic){target="_blank"}.


## Personnalisation

Lorsque vous ajoutez des liens personnalisés à votre contenu, évitez toujours toute personnalisation dans la partie du nom d&#39;hôte de l&#39;URL afin d&#39;éviter des failles de sécurité potentielles. Les exemples suivants ne doivent jamais être utilisés dans tous les attributs d&#39;URL &lt;`a href="">` ou `<img src="">` :

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restriction des données

Vous devez vous assurer que les mots de passe chiffrés ne sont pas accessibles par un utilisateur authentifié avec de faibles privilèges. Pour ce faire, il existe deux méthodes : restreindre l&#39;accès aux champs de mots de passe uniquement ou à l&#39;entité entière.

Cette restriction vous permet de supprimer les champs de mots de passe. Le compte externe reste toutefois accessible par tous les utilisateurs dans l&#39;interface. Apprenez-en davantage en consultant [cette page](../dev/restrict-pi-view.md).

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


## Gestion des accès

La gestion des accès joue un rôle important dans le renforcement de la sécurité. Vous trouverez ci-dessous quelques-unes des principales bonnes pratiques à appliquer.

* Créez suffisamment de groupes de sécurité.
* Vérifiez que chaque opérateur dispose des droits d&#39;accès adéquats.

En savoir plus sur les autorisations [dans cette section](../start/gs-permissions.md).

## Instructions de codage

Lorsque vous effectuez des tâches de développement dans Adobe Campaign (workflows, Javascript, JSSP, autres), suivez toujours ces instructions :

* **Scripts** : évitez si possible d&#39;utiliser des instructions SQL. Utilisez des fonctions paramétrables plutôt que la concaténation de chaîne et évitez toute injection SQL en ajoutant les fonctions SQL à utiliser à la liste autorisée.

* **Sécurisation du modèle de données** : utilisez des droits nommés pour limiter les actions des opérateurs et ajoutez des filtres système (sysFilter).

* **Ajout de captchas dans les applications web** : ajoutez des captchas dans vos pages d&#39;abonnement et landing pages publiques.

En savoir plus dans la documentation de [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=fr#installing-campaign-classic){target="_blank"}.
