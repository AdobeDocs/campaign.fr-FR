---
title: Paramètres de l’e-mail dans Adobe Campaign
description: Découvrez les options et les paramètres spécifiques à la diffusion e-mail dans Adobe Campaign.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: 6b70ad987b828dc1c17bc4f0683046be4eff0408
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 70%

---

# Paramètres de l’e-mail {#email-parameters}

Cette section présente les options et paramètres disponibles dans les propriétés de diffusion spécifiques à la diffusion e-mail.

## Utiliser E-mail Cci {#email-bcc}

Vous pouvez configurer Adobe Campaign pour conserver une copie des e-mails envoyés depuis votre plateforme. Cette option est détaillée sur [cette page](email-bcc.md).

## Sélectionner des formats de message {#selecting-message-formats}

Vous pouvez modifier le format des e-mails envoyés. Pour cela, éditez les propriétés de la diffusion et cliquez sur le bouton **[!UICONTROL Diffusion]**.

![](assets/email-message-format.png)

Sélectionnez le format du mail dans la section inférieure de la fenêtre :

* **[!UICONTROL Tenir compte des préférences des destinataires]** (mode par défaut)

  Le format du message est défini en fonction des informations enregistrées dans le profil du destinataire et stockées par défaut dans le champ **[!UICONTROL Format des emails]** (@emailFormat). Si un destinataire souhaite recevoir les messages dans un format particulier, ce format lui est envoyé. Si ce champ n&#39;est pas renseigné, le message sera envoyé en multipart-alternative (voir ci-dessous).

* **[!UICONTROL Laisser le mailer des destinataires choisir le format le plus adapté]**

  Le message contient les deux formats : texte et HTML. Le format affiché lors de la réception dépend de la configuration du logiciel de messagerie du destinataire (multipart-alternative).

  >[!IMPORTANT]
  >
  >Cette option inclut les deux versions du document. Par conséquent, elle affecte le débit de diffusion, car la taille du message est supérieure.

* **[!UICONTROL Envoyer tous les messages au format texte]**

  Le message est envoyé au format texte. Le format HTML ne sera pas envoyé mais uniquement utilisé pour la page miroir, lorsque le destinataire clique sur le lien dans le message.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## Configurer le codage des caractères {#character-encoding}

Dans l’onglet **[!UICONTROL SMTP]** des paramètres de diffusion, la section **[!UICONTROL Encodage des caractères]** vous permet de définir un encodage spécifique.

L’encodage par défaut est UTF-8. Si certains fournisseurs de messagerie de vos destinataires ne prennent pas en charge l’encodage UTF-8 standard, vous pouvez définir un encodage spécifique pour afficher correctement les caractères spéciaux sur les emails de vos destinataires.

Par exemple, vous souhaitez envoyer un email contenant des caractères japonais. Pour vous assurer que tous les caractères s’afficheront correctement à vos destinataires au Japon, vous pouvez utiliser un encodage prenant en charge les caractères japonais plutôt que le format UTF-8 standard.

Pour ce faire, sélectionnez l’option **[!UICONTROL Forcer l&#39;encodage des messages (codepage)]** dans la section **[!UICONTROL Encodage des caractères]**, puis choisissez un encodage dans la liste déroulante qui s’affiche.

![](assets/email-smtp-encoding.png)

## Gérer les e-mails de rebond {#managing-bounce-emails}

L’onglet **[!UICONTROL SMTP]** des propriétés de la diffusion permet de configurer la gestion des e-mails de rebond.

* **[!UICONTROL Adresse en cas d’erreur]** : par défaut, les e-mails de rebond sont réceptionnés dans la boîte d’erreur par défaut de la plateforme. Vous pouvez toutefois définir une adresse d’erreur spécifique pour une diffusion.

* **[!UICONTROL Adresse des rebonds]** : vous pouvez également définir une autre adresse vers laquelle les e-mails de rebond non traités seront transférés. Cette adresse permet d’étudier les raisons des rebonds lorsque les e-mails n’ont pas pu être qualifiés automatiquement par l’application.

Chacun de ces champs peut être personnalisé à l’aide de l’icône dédiée. En savoir plus sur les champs de personnalisation dans [cette section](personalization-fields.md).

![](assets/email-smtp-bounce.png)

Pour plus d’informations sur la gestion des e-mails de rebond, consultez [cette section](delivery-failures.md#bounce-mail-management).

## Activer le désabonnement de la liste en un clic {#one-click-list-unsubscribe}

L’URL list-unsubscribe en un clic est un lien ou un bouton affiché en regard des informations de l’expéditeur de l’e-mail, qui permet aux destinataires de se désinscrire instantanément de vos listes de diffusion en un seul clic. <!--[Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}-->

Il s’affiche sous la forme d’un lien **Se désabonner** dans les interfaces de messagerie des FAI. Par exemple :

![](assets/email-list-unsubscribe-example.png)

L’ajout d’un en-tête SMTP appelé List-Unsubscribe est obligatoire pour assurer une gestion optimale de la délivrabilité et peut être utilisé comme alternative à l’icône « Signaler comme SPAM ». En effet, l&#39;utilisation de cette fonctionnalité réduit les taux de plainte et contribue à protéger votre réputation.

>[!IMPORTANT]
>
>Pour afficher l’URL de désabonnement en un clic dans l’en-tête de l’e-mail, le client de messagerie du destinataire doit prendre en charge cette fonctionnalité.

Pour activer cette fonctionnalité, sélectionnez l&#39;option **[!UICONTROL Ajout d&#39;en-tête List-Unsubscription en un clic]** dans l&#39;onglet **[!UICONTROL SMTP]** des propriétés de la diffusion.

>[!NOTE]
>
>Cette option est activée par défaut.

![](assets/email-smtp-list-unsubscribe.png)

<!--
>[!WARNING]
>
>If you uncheck this option in the delivery template, it will still be enabled by default in the deliveries created from this template. You need to enable the option again at the delivery level.-->

Selon le client de messagerie et la méthode qu’il utilise pour effectuer son opt-out, le fait de cliquer sur le lien **Se désabonner** dans l’en-tête de l’e-mail peut avoir les impacts suivants :

* Si le client de messagerie utilise la méthode **One-Click** List-Unsubscribe, le destinataire est directement désabonné.

  >[!NOTE]
  >
  >Les principaux FAI tels que Google et Yahoo ! exigent des expéditeurs qu&#39;ils se conforment à **List-Unsubscribe en un clic**.

* Si le client de messagerie ne prend pas en charge List-Unsubscribe en un clic, il peut toujours utiliser la méthode **« mailto »** List-Unsubscribe, qui envoie un e-mail prérempli à l’adresse de désabonnement spécifiée dans l’en-tête de l’e-mail.

  Vous pouvez définir l&#39;adresse explicitement dans l&#39;en-tête ou utiliser une adresse dynamique (par exemple à l&#39;aide de &lt;%=errorAddress%> ou de l&#39;option &#39;NmsEmail_DefaultErrorAddr&#39;) qui peut être définie via l&#39;assistant de déploiement.

>[!NOTE]
>
>Vous pouvez également définir manuellement les méthodes [List-Unsubscribe en un clic](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#one-click-list-unsubscribe){target="_blank"} et [« mailto » List-Unsubscribe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#mailto-list-unsubscribe){target="_blank"}. Les étapes détaillées sont décrites dans le [ Guide des bonnes pratiques en matière de délivrabilité d&#39;Experience Cloud](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=fr#list-unsubscribe){target="_blank"}.


## Ajouter des en-têtes SMTP {#adding-smtp-headers}

Vous pouvez ajouter des en-têtes SMTP à vos diffusions. Pour ce faire, utilisez la section correspondante de l’onglet **[!UICONTROL SMTP]** de la diffusion.

Le script saisi dans cette fenêtre doit référencer un en-tête par ligne sous la forme suivante : **nom:value**.

Les valeurs sont automatiquement encodées, si nécessaire.

>[!IMPORTANT]
>
>L&#39;ajout d&#39;un script pour l&#39;insertion d&#39;en-têtes SMTP supplémentaires est réservé aux utilisateurs expérimentés.
>
>La syntaxe de ce script doit être strictement conforme aux exigences de ce type de contenu : aucun espace superflu, aucune ligne vide, etc.

![](assets/email-smtp-headers.png)


## Générer une page miroir {#generating-mirror-page}

La page miroir est une page HTML accessible en ligne via un navigateur web et dont le contenu est identique à celui de l’e-mail. Cela peut être utile si vos personnes destinataires rencontrent des problèmes de rendu ou accèdent à des images endommagées quand ils affichent votre e-mail dans leur boîte de réception.

Découvrez comment insérer un lien vers la page miroir dans [cette section](mirror-page.md).
