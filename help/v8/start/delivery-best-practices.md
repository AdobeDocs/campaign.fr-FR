---
title: Bonnes pratiques relatives à la diffusion
description: Découvrez les bonnes pratiques lors de la conception et de l’envoi de diffusions avec Adobe Campaign.
feature: Email, Push, SMS, Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: cb6094eb-0010-4c62-9589-3b52fd60c2c2
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '2959'
ht-degree: 100%

---

# Bonnes pratiques relatives à la diffusion {#delivery-best-practices}

Découvrez les bonnes pratiques suivantes avec les fonctionnalités de diffusion de Campaign.

## Optimiser votre diffusion {#optimize-delivery}

Avant même de commencer à créer des diffusions, vous pouvez prendre des mesures pour sécuriser et optimiser le processus d’envoi en amont. La section suivante présente les bonnes pratiques et les procédures recommandées pour optimiser la configuration d’Adobe Campaign.

### Performances de la plateforme

Plusieurs facteurs peuvent avoir une incidence directe sur les performances du serveur et ralentir votre plateforme Campaign :

* Nombre et type d’éléments de [personnalisation](../send/personalize.md) : dans les e-mails, la personnalisation extrait les données de la base de données pour chaque destinataire. Dans le cas de nombreux éléments de personnalisation, la quantité de données nécessaires à la préparation de la diffusion est plus élevée. Cela peut ralentir votre plateforme. Découvrez les mécanismes de sécurisation de la personnalisation dans [cette section](../send/personalize.md#perso-guardrails).

* Charge du serveur : lorsque le serveur marketing gère simultanément trop de tâches différentes, cela peut diminuer les performances. Le serveur marketing doit coordonner toutes les données entrantes et sortantes pour l’ensemble des diffusions afin de s’assurer que les données sont correctes et disponibles à temps.
Pour éviter cette situation, coordonnez la planification des diffusions avec les autres membres de votre équipe afin d’optimiser les performances.

* Exécution du workflow : la surveillance de vos workflows est essentielle pour éviter tout problème de performances de la plateforme. Suivez les directives répertoriées [dans ce document](../../automation/workflow/workflow-best-practices.md#execution-and-performance).

* Connectez-vous à vos [fonctionnalités du panneau de contrôle de Campaign](https://experienceleague.adobe.com/fr/docs/control-panel/using/discover-control-panel/key-features){target="_blank"} pour surveiller votre plateforme à l’aide des fonctionnalités de [surveillance des performances](https://experienceleague.adobe.com/fr/docs/control-panel/using/performance-monitoring/about-performance-monitoring){target="_blank"}.

#### Gestion des quarantaines {#quarantine-management}

Vous avez tout intérêt à mettre en place et à conserver de bons processus de gestion des quarantaines.

Lorsque vous commencez à envoyer des emails sur une nouvelle plateforme, vous pouvez utiliser une liste d’adresses qui ne sont pas entièrement qualifiées. Or l’envoi à des adresses non valides ou à des adresses pièges (boîtes mails créées dans le but de piéger les spammeurs) contribue à abaisser la réputation de la plateforme. De bons processus de gestion des quarantaines permettent de conserver la qualité des adresses, d&#39;éviter la mise sur liste bloquée de la part des FAI et de réduire le taux d&#39;erreur, tout en augmentant la vitesse des diffusions et le débit.


Découvrez comment démarrer une nouvelle plateforme dans le [Guide Adobe des bonnes pratiques en matière de délivrabilité](https://experienceleague.adobe.com/fr/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform){target="_blank"}.

Les recommandations techniques sont répertoriées dans [cette section](https://experienceleague.adobe.com/fr/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations){target="_blank"}.


+++ **Lire quelques bonnes pratiques**

* Si vous disposez d&#39;une liste d&#39;adresses invalides, Adobe recommande de l&#39;importer dans la table des quarantaines, par le biais de **[!UICONTROL Administration]** > **[!UICONTROL Gestion de campagne]** > **[!UICONTROL Gestion des NP@I]** > **[!UICONTROL NP@I et Adresses]**.

* Les destinataires dont l’adresse est en quarantaine sont par défaut exclus lors de l’analyse d’une diffusion : ils ne seront pas ciblés. Le taux d’erreur ayant une incidence importante sur la vitesse de diffusion, les envois sont ainsi accélérés. Une adresse e-mail peut être mise en quarantaine par exemple lorsque la boîte de réception est pleine ou si l’adresse n’existe pas.
Le mode de gestion des adresses en erreur par Adobe Campaign dépend du type d’erreur retourné. [En savoir plus sur les quarantaines](../send/quarantines.md)

* Certains fournisseurs d&#39;accès à internet considèrent automatiquement les e-mails comme du spam si le taux d&#39;adresses non valides est trop élevé. La quarantaine permet donc d&#39;éviter d&#39;être ajouté à une liste bloquée par ces fournisseurs.

+++



### Mécanisme de double opt-in {#double-opt-in}

Pour éviter d&#39;envoyer des messages à des adresses invalides, limiter les communications abusives et améliorer la réputation de l&#39;expéditeur ou de l’expéditrice, Adobe recommande de mettre en place un mécanisme de double opt-in pour une confirmation après inscription. Cela vous permet de vous assurer que la personne destinataire est bien à l&#39;origine de l&#39;abonnement.

## Utiliser des modèles {#use-templates}

Les modèles de diffusion accroissent l’efficacité en offrant des configurations prêtes à l’emploi pour les types d’activité les plus courants. Grâce aux modèles, les spécialistes marketing peuvent déployer plus rapidement de nouvelles campagnes avec une personnalisation minimale. [En savoir plus sur les modèles de diffusion](../send/create-templates.md).

### Sous-domaines et branding {#subdomains-and-branding}

Si vous gérez plusieurs marques dans Adobe Campaign, Adobe recommande de disposer d’un sous-domaine par marque. Une banque peut, par exemple, avoir plusieurs sous-domaines qui correspondent à chacune de ses agences régionales. Si une banque détient le domaine bluebank.com, ses sous-domaines peuvent être @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, etc. Disposer d’un modèle de diffusion par sous-domaine vous permet de toujours utiliser les paramètres préconfigurés adéquats pour chaque marque et d’éviter ainsi des erreurs tout en gagnant du temps. En savoir plus sur le branding de sous-domaines dans la [documentation du Panneau de contrôle de Campaign](https://experienceleague.adobe.com/fr/docs/control-panel/using/subdomains-and-certificates/subdomains-branding){target="_blank"}.

### Configurer les adresses {#configure-addresses}

Veillez à appliquer les directives suivantes :

* L’adresse de l’expéditeur ou de l’expéditrice est obligatoire pour permettre l’envoi d’un e-mail. Certains FAI vérifient la validité de l’adresse de l’expéditeur avant d’accepter les messages.
* Une adresse erronée peut causer un refus de la part du serveur receveur. Vous devez vous assurer qu’une adresse correcte est bien renseignée.
* L&#39;adresse doit identifier explicitement l&#39;expéditeur. Le domaine doit appartenir à l&#39;expéditeur et être enregistré auprès de lui.
* Adobe recommande de créer des comptes email qui correspondent aux adresses indiquées pour les envois et les réponses. Parlez-en avec votre administrateur du système de messagerie.

+++ **Étapes de configuration des adresses dans l’interface utilisateur de Campaign**

Pour configurer les adresses dans l’interface de Campaign, procédez comme suit :

1. Dans le [modèle de diffusion](../send/create-templates.md), cliquez sur le lien **[!UICONTROL De]**. Dans la fenêtre **[!UICONTROL Paramètres d’en-tête des e-mails]**, saisissez les paramètres.

1. Dans le champ **[!UICONTROL Adresse de l’expéditeur]**, assurez-vous que le domaine d’adresse est identique au sous-domaine que vous avez délégué à Adobe. Vous pouvez modifier la partie qui précède le signe « @ », mais pas l’adresse du domaine.

1. Dans le champ **[!UICONTROL De]**, utilisez un nom facilement identifiable par les destinataires, tel que le nom de votre marque, pour augmenter le taux d’ouverture de vos diffusions. Pour améliorer davantage l’expérience des destinataires, vous pouvez ajouter le nom d’une personne, par exemple « Emma de Megastore ».

1. Dans le champ **[!UICONTROL Texte de l’adresse de réponse]**, l’adresse de l’expéditeur est utilisée par défaut pour les réponses. Adobe recommande toutefois d’utiliser une adresse réelle existante, comme l’assistance clientèle de votre marque. Ainsi, si un destinataire envoie une réponse, l’assistance clientèle sera en mesure de la traiter.

### Configurer une population témoin {#set-up-control-group}

Une fois que la diffusion est envoyée, vous pouvez comparer le comportement des destinataires exclus à celui des destinataires qui ont reçu la diffusion. Vous pouvez ensuite mesurer l’efficacité de vos campagnes. En savoir plus sur les populations témoins dans [cette section](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Utiliser des typologies pour appliquer des filtres ou des règles de contrôle {#create-typologies}

Une typologie contient les règles de vérification qui sont appliquées lors de la phase d’analyse, avant tout envoi.

Dans l’onglet **[!UICONTROL Typologie]** des propriétés du modèle, vous pouvez sélectionner une typologie personnalisée si nécessaire.

Pour mieux contrôler le trafic sortant, par exemple, vous pouvez définir quelles adresses IP peuvent être utilisées en spécifiant une affinité par sous-domaine et en créant une typologie par affinité. Les affinités sont définies directement dans le fichier de configuration de l&#39;instance. Contactez votre administrateur Adobe Campaign.

Pour plus d’informations sur les typologies, consultez [cette section](../../automation/campaign-opt/campaign-typologies.md).

## Optimiser votre contenu {#optimize-content}

### Créer du contenu personnalisé {#perso-content}

Pour personnaliser vos messages, vous pouvez utiliser les données des destinataires stockées dans la base de données ou collectées par le biais du tracking, des pages de destination, des abonnements, etc. Les principes de base de la personnalisation sont présentés dans [cette section](../send/personalize.md).

+++ **Lire quelques bonnes pratiques**

* Vérifier vos paramètres de personnalisation : vérifiez que le contenu de votre message est correctement conçu pour éviter toute erreur, qui pourrait être liée à la personnalisation. Une balise de personnalisation Adobe Campaign a toujours la forme suivante : `<%=table.field%>`. L&#39;utilisation incorrecte des paramètres dans les blocs de personnalisation peut entraîner des problèmes. Par exemple, les variables en JavaScript doivent être utilisées comme suit :

  ``
  <%
  var brand = "xxx"
  %>
  ``

  Pour plus d&#39;informations sur les blocs de personnalisation, consultez [cette section](../send/personalization-blocks.md).

* Préparer les données de personnalisation : vous pouvez préparer les données de personnalisation dans un workflow afin d’améliorer l’analyse de préparation des diffusions. Vous devez effectuer cette opération tout particulièrement si les données de personnalisation proviennent d&#39;une table externe via Federated Data Access (FDA). Cette option est décrite dans [cette section](../send/personalization-data.md#optimize-personalization)
+++

### Créer du contenu optimisé {#build-optimized-content}

Lorsque vous créez vos e-mails, appliquez les bonnes pratiques générales pour le contenu des e-mails.

+++ **Lire quelques bonnes pratiques**

* Gardez le design de vos e-mails simple

* Gardez les utilisateurs d&#39;appareils mobiles à l&#39;esprit

* Évitez les e-mails basés entièrement sur des images

* Utilisez des polices sécurisées pour les e-mails

* Encodez les caractères spéciaux

+++


### Objet  {#subject-line-check}

Travaillez sur la [ligne d’objet](../send/personalization-fields.md#personalization-fields-uc) pour améliorer les taux d’ouverture.


+++ **Lire quelques bonnes pratiques**


* Évitez les objets trop longs. Utilisez 50 caractères au maximum

* Évitez de répéter des mots tels que &quot;gratuit&quot; ou &quot;offre&quot; qui peuvent être considérés comme des messages indésirables

* Évitez les lettres majuscules.

* N’utilisez pas de caractères spéciaux tels que « ! », « £ », « € » et « $ ».

+++

### Page miroir {#mirror-page-check}

Incluez toujours un lien de page miroir. La partie supérieure de l&#39;e-mail constitue la position idéale. En savoir plus sur la page miroir dans [cette section](../send/mirror-page.md).

### Lien de désabonnement {#unsub-link-check}

Le lien de désabonnement est indispensable. Il doit être visible, valide et le formulaire fonctionnel. Par défaut, lorsque le message est analysé, une [règle de typologie](../../automation/campaign-opt/control-rules.md) intégrée **[!UICONTROL Approbation du lien de désabonnement]** vérifie si un lien d’exclusion a été inclus et génère un avertissement en cas d’absence.

Découvrez comment insérer un lien d&#39;exclusion [dans cette section](../send/personalization-blocks.md).

+++ **Appliquer cette bonne pratique**

Comme une erreur humaine est toujours possible, vérifiez que le lien d’exclusion fonctionne correctement avant chaque envoi. Par exemple, lors de l’envoi du BAT, vérifiez que le lien est valide, que le formulaire est en ligne et que la valeur du champ `No longer contact this recipient ` est définie sur `Yes`.

+++

### Taille des emails {#email-size-check}

Pour éviter des problèmes de performances ou de délivrabilité, la taille maximale recommandée d’un email est d’environ **35 Ko**. Pour vérifier la taille du message, accédez à l’onglet **[!UICONTROL Aperçu]** et choisissez un profil de test. Une fois le message généré, sa taille s’affiche en haut à droite.


+++ **Lire quelques bonnes pratiques**

* Supprimer les styles redondants ou inutilisés

* Déplacer une partie du contenu de l’email vers une landing page

* Minimiser votre code

Veillez à tester toutes les modifications avant l’envoi final.

+++


### Longueur des SMS {#sms-length-check}

Par défaut, le nombre de caractère d&#39;un SMS respecte la norme de téléphonie mobile GSM (Global System for Mobile Communications). Les SMS utilisant l&#39;encodage GSM sont limités à 160 caractères, ou 153 caractères par SMS pour les messages envoyés en plusieurs parties.


+++ **Lire quelques bonnes pratiques**

* Pour conserver tous les caractères de vos SMS, afin de ne pas altérer les noms propres par exemple, n’activez pas la translittération.

* En revanche, si vos SMS contiennent beaucoup de caractères qui ne sont pas pris en charge par la norme GSM, activez la translittération afin de limiter le coût de vos envois. En savoir plus [dans cette section](../send/sms/smpp-external-account.md#smpp-transliteration).

* Vous pouvez appliquer la translittération aux SMS. Celle-ci consiste à remplacer un caractère d’un SMS par un autre lorsque ce caractère n’est pas pris en charge par la norme GSM. Notez que l’insertion de champs de personnalisation dans le contenu du SMS peut introduire des caractères non pris en charge par l’encodage GSM. En tant qu’administrateur ou administratrice Campaign, vous pouvez activer la translittération des caractères en cochant la case correspondante dans l’onglet des paramètres du canal SMPP du **[!UICONTROL compte externe]** correspondant. [En savoir plus](../send/sms/smpp-external-account.md#smpp-transliteration)

+++

### Éviter les pièces jointes

Les pièces jointes restent l’un des vecteurs les plus courants de la prolifération des logiciels malveillants, surtout lorsqu’elles sont envoyées en masse. Incluez un lien sécurisé vers le document au lieu de le joindre au message. Une couche de sécurité supplémentaire est ainsi garantie pour empêcher toute redistribution involontaire. De plus, les risques que le message soit rejeté au niveau des passerelles de messagerie entrantes pour des raisons de taille ou de sécurité sont considérablement réduits.

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).-->

## Gestion des images {#manage-images}

Voici quelques instructions spécifiques pour optimiser les images de votre campagne de marketing par e-mail.

### Empêcher le blocage des images {#image-blocking}

Certains clients de messagerie bloquent les images par défaut, et les utilisateurs et utilisatrices peuvent modifier leurs paramètres pour bloquer les images afin de réduire l’utilisation des données. Dans ce cas, si les images ne sont pas téléchargées, il est possible que l’ensemble du message soit perdu.

+++ Pour éviter cela, vous pouvez appliquer les bonnes pratiques suivantes :

* Évitez les e-mails basés entièrement sur des images. Équilibrez le contenu entre image et texte.

* Si le texte doit être contenu dans une image, utilisez du texte de titre et du texte alternatif pour vous assurer que votre message passe bien. Mettez en forme votre texte de titre et alternatif pour améliorer son aspect.

* Évitez d’utiliser des images d’arrière-plan, car elles ne sont pas prises en charge par certains clients de messagerie.
+++

### Rendre les images réactives {#responsive-images}

Essayez de rendre les images réactives et redimensionnables afin de les rendre visibles dans tous les contextes et appareils. Notez que cela peut avoir un impact sur les coûts, car la création prend plus de temps.

### Utiliser des références absolues pour l&#39;accès à l&#39;image {#absolute-images}

Pour être accessibles depuis l&#39;extérieur, les images utilisées dans les e-mails et les ressources publiques associées aux opérations doivent être présentes sur un serveur accessible de l&#39;extérieur.

* Dans l’assistant de diffusion, vous pouvez importer une page HTML contenant des images ou insérer des images directement depuis l’éditeur HTML à l’aide de l’icône **[!UICONTROL Image]**.

* Si les images ne sont pas affichées, vérifiez qu&#39;elles sont disponibles sur le serveur. Pour ce faire, accédez à l’onglet **Source** de votre diffusion. Recherchez vos images, copiez l&#39;URL de chaque image et collez-la dans un navigateur web. Si les images ne sont toujours pas affichées, contactez votre administrateur ou administratrice informatique ou le fournisseur tiers du contenu de votre diffusion.

### Prévisualiser et tester votre message {#preview-msg}

Adobe recommande de prévisualiser votre message afin de vérifier sa personnalisation et l&#39;affichage de la diffusion par vos destinataires.

Dans l’assistant de diffusion, le sous-onglet **[!UICONTROL Prévisualisation]** vous permet de visualiser le rendu de chaque contenu pour une personne destinataire. Les champs de personnalisation et les éléments conditionnels du contenu sont remplacés par les informations correspondantes pour le profil sélectionné. [En savoir plus](../send/preview-and-proof.md).


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## Définition de lʼaudience appropriée {#define-the-right-audience}

La population ciblée est essentielle : créez soigneusement vos listes, testez vos emails sur les clients de messagerie et les appareils mobiles les plus utilisés et vérifiez que vos listes email sont à jour (sans adresses inconnues ou obsolètes). Vous pouvez également envoyer des BAT permettant de configurer un cycle de validation complet. Pour en savoir plus sur les audiences, consultez [cette section](../audiences/gs-audiences.md).

### Cibler la bonne audience {#target-the-right-audience}

Lorsque votre contenu est prêt, vous devez soigneusement définir qui recevra votre message.

Pour réussir votre diffusion, vous devez envoyer le contenu personnalisé le plus pertinent aux bons destinataires. Adobe Campaign vous permet de créer la cible la plus précise qui soit : vous pouvez sélectionner les destinataires selon leur âge, leur emplacement géographique, leurs achats ou selon qu’ils ont cliqué ou non sur un lien dans une diffusion précédente, par exemple. Avec Adobe Campaign, vous pouvez également définir des profils de test, des populations témoins et des adresses de contrôle pour vérifier que votre cible est correcte.

### Mappings de ciblage {#target-mappings}

Par défaut, dans Campaign, les modèles de diffusion ciblent les **Destinataires**. Adobe Campaign propose d’autres mappings de ciblage pour vos diffusions, que vous pouvez modifier selon vos besoins. Vous pouvez, par exemple, envoyer votre diffusion à des visiteurs dont le profil a été collecté par le biais des réseaux sociaux ou à des visiteurs qui se sont abonnés à un service d&#39;information.

Ces mappings sont présentés [dans cette section](../audiences/target-mappings.md).

### Destinataires externes {#external-recipients}

Vous pouvez effectuer une diffusion aux destinataires qui sont stockés dans un fichier externe plutôt qu&#39;enregistrés dans la base de données. En savoir plus dans [cette section](create-message.md#select-external-recipients-selecting-external-recipients).

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### Tester les destinataires {#test-recipients-seed-addresses}

Pour tester votre diffusion, utilisez des bons à tirer avant l&#39;envoi à la cible principale.

Veillez à sélectionner les destinataires du BAT appropriés, car ils valident le formulaire et le contenu du message. Les étapes de définition des destinataires du BAT sont présentées [dans cette section](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target).


### Dédupliquer les adresses {#deduplicate-addresses}

Il est important d’éviter d’avoir des adresses e-mail en double, car cela peut avoir un impact sur votre cible :

* Un même message peut être envoyé plusieurs fois lorsqu&#39;une une cible est partagée.

* Si une personne se désabonne suite à la réception d&#39;un message, son profil en double recevra toujours les prochains messages.

Pour garantir votre réputation et assurer une bonne gestion des quarantaines, dédupliquez les adresses.

**Rubriques connexes :**

* [Activité Déduplication](../../automation/workflow/deduplication.md).
* [Cas d’utilisation : utilisation de la fonctionnalité de fusion de l’activité Déduplication](../../automation/workflow/deduplication-merge.md).


## Effectuer toutes les vérifications avant l’envoi {#perform-all-checks}

Une fois que votre message est prêt, vérifiez que le contenu s’affiche correctement sur tous les appareils et qu’il ne contient aucune erreur, comme des liens rompus ou une personnalisation incorrecte. Avant d’envoyer votre message, vérifiez également que les paramètres et la configuration sont cohérents par rapport à la diffusion.

Les étapes de validation d&#39;une diffusion sont présentées [dans cette section](../send/preview-and-proof.md).

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### Messages de BAT {#proof-messages}

L’envoi de BAT permet de vérifier le lien d’exclusion, la page miroir et d’autres liens, de valider le message, de vérifier le bon affichage des images, de détecter les erreurs possibles, etc. Vous souhaiterez peut-être également vérifier votre conception et le rendu sur différents appareils.

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### Vérifiez que votre message est bien délivré.  {#make-sure-your-message-is-delivered}

En dernier lieu, tirez parti des fonctionnalités d&#39;Adobe Campaign et augmentez vos chances que votre message soit délivré aux bonnes personnes destinataires.

#### Suivre un processus de validation

Vous pouvez définir un processus de validation complet, impliquant des opérateurs et des groupes Adobe Campaign, afin de valider la cible et le contenu du message. Cela assurera une surveillance et un contrôle complet des différents traitements de l&#39;opération : ciblage, contenu, budget, extraction et envoi d&#39;un BAT. En fonction de leurs autorisations, les utilisateurs seront avertis, ils recevront les BAT et ils pourront valider ou refuser le message. En savoir plus à ce sujet dans [cette section](../../automation/campaigns/marketing-campaign-approval.md).

#### Utiliser des vagues

Vous pouvez augmenter progressivement le volume envoyé à l&#39;aide de vagues. Cela évitera que les emails soient marqués comme spam ou pour limiter le nombre de messages par jour. Grâce aux vagues, vous pouvez répartir les envois en plusieurs lots au lieu d’envoyer de gros volumes de messages en même temps. En savoir plus à ce sujet dans [cette section](../send/configure-and-send.md#sending-using-multiple-waves).

#### Définir la priorité des messages

Vous pouvez définir l&#39;ordre d&#39;envoi de vos diffusions en indiquant leur niveau de priorité. Pour ce faire :

1. Modifiez les propriétés de la diffusion et sélectionnez l&#39;onglet **[!UICONTROL Diffusion]**.

1. Définissez le niveau de priorité de la diffusion sur une échelle allant de **[!UICONTROL Très basse]** à **[!UICONTROL Très haute]**.

>[!NOTE]
>
>Il n&#39;est pas possible de définir l&#39;ordre d&#39;envoi des messages au sein d&#39;une diffusion.

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### Utiliser des typologies

Vous pouvez utiliser des règles de typologie pour exclure une partie de la cible en fonction de critères spécifiques. Elles permettent de s’assurer que les messages envoyés répondent le mieux possible aux attentes ou aux besoins du client, dans le respect des politiques de communication de l’entreprise. Vous pouvez, par exemple, filtrer les destinataires mineurs du public cible de votre newsletter. En savoir plus [dans cet exemple](../../automation/campaign-opt/filtering-rules.md).


## Tracker et suivre vos diffusions {#track-and-monitor}

Vous avez cliqué sur le bouton **Envoyer** ? Voyons maintenant ce qui se passe. Une fois la diffusion envoyée, Adobe Campaign vous permet de conserver une trace des messages envoyés et de découvrir la réaction des destinataires face à votre diffusion. Vous pourrez ainsi améliorer les prochains envois et optimiser vos campagnes suivantes.

## Surveillance des diffusions {#monitoring-deliveries}

Pour contrôler vos campagnes, vous devez vérifier que le message a bien été délivré à vos destinataires.

Dans le tableau de bord des diffusions de Campaign, vous pouvez vérifier les messages traités et consulter les logs d’audit de diffusion. Vous pouvez également contrôler le statut des messages dans les logs de diffusion.

## Tracking du comportement {#track-behaviour}

Pour mieux connaître le comportement de vos destinataires, vous pouvez suivre leur réaction à une diffusion : réception, ouverture, clics sur des liens, désabonnements, etc. Dans Campaign, ces informations figurent dans l’onglet **Tracking** des personnes destinataires ciblées par la diffusion et dans l’onglet Tracking de la diffusion.

Le tracking des messages est activé par défaut. Pour configurer les URL, sélectionnez l’option Afficher les URL dans la section inférieure de l’assistant de diffusion. Pour chaque URL du message, vous pouvez choisir d’activer ou non le tracking.


[En savoir plus sur les fonctionnalités de tracking dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=fr#sending-messages){target="_blank"}
