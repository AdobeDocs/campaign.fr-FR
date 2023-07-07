---
title: Configurer des e-mails avec Adobe Campaign
description: Découvrez comment configurer des e-mails dans Adobe Campaign.
feature: Email
role: User
level: Beginner
source-git-commit: 263ec61c3717c054cc135f1c4fb1f7e287e4a154
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 90%

---

# Configurer et envoyer la diffusion {#configure-delivery}

## Configurer des paramètres supplémentaires {#delivery-additional-parameters}

Avant d’envoyer la diffusion, vous pouvez définir les paramètres d’envoi dans les propriétés de la diffusion, via l’onglet **[!UICONTROL Diffusion]**.

![](assets/delivery-properties-delivery.png)

* **[!UICONTROL Priorité de diffusion]** : utilisez cette option pour modifier l’ordre d’envoi de vos diffusions en configurant leur niveau de priorité, de **[!UICONTROL Très basse]** à **[!UICONTROL Très haute]** (la valeur par défaut étant **[!UICONTROL Normale]**).

* **[!UICONTROL Nombre de messages groupés]** : cette option permet de définir le nombre de messages regroupés dans un même package d’envoi XML. Si le paramètre est défini sur 0, les messages sont automatiquement regroupés. La taille du paquet est définie par le calcul `<delivery size>/1024`, avec un minimum de 8 messages et un maximum de 256 messages par package.

  >[!IMPORTANT]
  >
  >Lorsque vous créez la diffusion en dupliquant une diffusion existante, vous réinitialisez également ce paramètre.

* **[!UICONTROL Envoyer en plusieurs vagues]** : cette option vous permet d’envoyer vos messages par lots, plutôt qu’à toute votre audience en même temps. [En savoir plus](#sending-using-multiple-waves).

* **[!UICONTROL Tester la diffusion via SMTP]** : cette option vous permet de tester la diffusion par SMTP. La diffusion est traitée jusqu’à la connexion au serveur SMTP mais n’est pas envoyée : pour chaque destinataire de la diffusion, Campaign se connecte au serveur du fournisseur SMTP, exécute la commande SMTP RCPT TO et ferme la connexion avant la commande SMTP DATA.

  >[!NOTE]
  >
  >* Cette option ne doit pas être définie en midsourcing.
  >
  >* En savoir plus sur la configuration du serveur SMTP dans [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/configure-delivery-settings.html?lang=fr#smtp-relay){target="_blank"}.

* **[!UICONTROL E-mail Cci]** : cette option vous permet de stocker vos e-mails dans un système externe à l’aide de l’option Cci en ajoutant simplement une adresse e-mail à la cible des messages. [En savoir plus](email-parameters.md).

## Envoi en plusieurs vagues {#sending-using-multiple-waves}

Pour équilibrer la charge, vous pouvez répartir les envois en plusieurs lots. Configurez le nombre de lots et leur proportion par rapport à l&#39;ensemble de la diffusion.

>[!NOTE]
>
>Vous pouvez uniquement définir la taille et le délai entre deux vagues consécutives. Le critère de sélection des destinataires pour chaque vague n&#39;est pas paramétrable.

1. Ouvrez la fenêtre des propriétés de la diffusion, puis cliquez sur l&#39;onglet **[!UICONTROL Diffusion]**.
1. Sélectionnez l&#39;option **[!UICONTROL Envoyer en plusieurs vagues]**, puis cliquez sur le lien **[!UICONTROL Définition des vagues...]**.

   ![](assets/delivery-define-waves.png)

1. Pour configurer des vagues, vous pouvez effectuer l&#39;une des opérations suivantes :

   * Définissez la taille de chaque vague. Par exemple, si vous saisissez **[!UICONTROL 30 %]** dans le champ correspondant, chaque vague représentera 30 % des messages inclus dans l&#39;envoi, à l&#39;exception de la dernière vague qui représentera 10 % des messages.

     Dans le champ **[!UICONTROL Période]**, définissez le délai entre le démarrage de deux vagues consécutives. Par exemple, si vous saisissez **[!UICONTROL 2j]**, la première vague démarre immédiatement, la deuxième démarre dans deux jours, la troisième dans quatre jours, etc.

     ![](assets/delivery-waves-size.png)

   * Définissez un calendrier pour l&#39;envoi de chaque vague.

     Dans la colonne **[!UICONTROL Démarrage]**, indiquez le délai entre le démarrage de deux vagues consécutives. Dans la colonne **[!UICONTROL Taille]**, saisissez un nombre fixe ou un pourcentage.

     Dans l&#39;exemple ci-dessous, la première vague représente 25 % du nombre total des messages inclus dans l&#39;envoi et démarre immédiatement. Les deux vagues suivantes terminent l&#39;envoi et sont définies pour démarrer à six heures d&#39;intervalle.

     ![](assets/delivery-waves-calendar.png)

   Une règle de typologie spécifique, la **[!UICONTROL Vérification de la planification des vagues]**, garantit que la dernière vague est planifiée avant la limite de validité de la diffusion. Les typologies de campagnes et leurs règles, configurées dans l’onglet **[!UICONTROL Typologie]** des propriétés de diffusion, sont présentées dans [cette section.](../../automation/campaign-opt/campaign-typologies.md#typology-rules)<!--ref TBC-->

   >[!IMPORTANT]
   >
   >Veillez à ce que les dernières vagues ne dépassent pas la date limite d&#39;envoi qui est définie dans l&#39;onglet **[!UICONTROL Validité]**.Sinon, certains messages peuvent ne pas être envoyés.
   >
   >Lors de la configuration des dernières vagues, veillez également à prévoir assez de temps pour les reprises. <!--See [this section]().-->

1. Pour suivre vos envois, accédez aux logs de diffusion. Pour plus d’informations, consultez [cette page](send.md)<!--ref TBC-->.

   Vous pouvez visualiser les diffusions qui ont déjà été envoyées dans les vagues traitées (statut **[!UICONTROL Envoyé]**) et celles à envoyer dans les vagues restantes (statut **[!UICONTROL En attente]**).

Les deux exemples ci-dessous constituent les cas d&#39;utilisation les plus fréquents de plusieurs vagues.

* **Lors de la phase de démarrage**

  Lorsque vous envoyez des emails à l&#39;aide d&#39;une nouvelle plateforme, rien n&#39;est plus suspect pour un FAI (fournisseur d&#39;accès internet) que les adresses IP qui ne sont pas reconnues. Si des emails sont subitement envoyés en masse, le FAI les range souvent dans le courrier indésirable.

  Pour éviter que les emails soient marqués comme spam, vous pouvez augmenter progressivement le volume envoyé à l&#39;aide de vagues. Cela permet d&#39;entamer la phase de démarrage en douceur et de réduire le nombre total d&#39;adresses invalides.

  Pour ce faire, utilisez l&#39;option **[!UICONTROL Planifier les vagues selon un calendrier]**. Par exemple, définissez la première vague sur 10 %, la deuxième sur 15 %, etc.

  ![](assets/delivery-waves-ex-ramp-up.png)

* **Campagnes impliquant un centre d&#39;appels**

  Lorsque vous gérez une campagne téléphonique de fidélisation, votre entreprise a une capacité de traitement des appels limitée pour contacter les abonnés.

  Grâce aux vagues, vous pouvez limiter le nombre des messages à 20 par jour, ce qui correspond à la capacité de traitement quotidien d&#39;un centre d&#39;appels.

  Pour ce faire, sélectionnez l&#39;option **[!UICONTROL Planifier plusieurs vagues de même taille]**. Saisissez **[!UICONTROL 20]** pour la taille de la vague et **[!UICONTROL 1j]** dans le champ **[!UICONTROL Période]**.

  ![](assets/delivery-waves-ex-call-center.png)

## Confirmer la diffusion {#confirm-delivery}

Une fois la diffusion paramétrée et prête à être envoyée, vérifiez que vous avez exécuté l&#39;analyse de la diffusion avant de confirmer l&#39;envoi.

Pour ce faire, suivez les étapes ci-après.

1. Cliquez sur **[!UICONTROL Envoyer]**, sélectionnez l’action souhaitée.

   * Pour envoyer immédiatement la diffusion, sélectionnez [**Diffuser dès que possible**].
   * Pour planifier l’envoi à une date ultérieure, sélectionnez **[!UICONTROL Différer la diffusion]**. [En savoir plus](#schedule-delivery-sending).

1. Cliquez sur **[!UICONTROL Analyser]**. Pour plus d’informations, consultez [cette section](delivery-analysis.md).

   ![](assets/delivery-send-analyze.png)

1. Une fois que vous avez terminé, cliquez sur **[!UICONTROL Confirmer l’envoi]** pour lancer la diffusion des messages.

   ![](assets/delivery-send-confirm.png)

1. Vous pouvez fermer l&#39;assistant de diffusion et suivre l&#39;exécution de la diffusion depuis le **[!UICONTROL Diffusion]** , accessible à partir du détail de cette diffusion ou à partir de la liste des diffusions.

   Voir à ce propos les sections ci-dessous :

   * [Contrôler une diffusion](send.md)
   * [Comprendre les échecs de diffusion](delivery-failures.md)

<!--About message tracking-->

## Planification de lʼenvoi de la diffusion {#schedule-delivery-sending}

Vous pouvez différer la diffusion des messages pour planifier l&#39;envoi ou pour gérer la pression commerciale afin de ne pas sur-solliciter une population.

1. Cliquez sur le bouton **[!UICONTROL Envoyer]** et sélectionnez l’option **[!UICONTROL Différer la diffusion]**.

1. Indiquez une date de démarrage dans le champ **[!UICONTROL Date de contact]**.

   ![](assets/delivery-send-postpone.png)

1. Lancez l&#39;analyse de la diffusion et validez l&#39;envoi de la diffusion. Toutefois, cet envoi ne démarrera pas avant la date indiquée dans le champ **[!UICONTROL Date de contact]**.

   >[!IMPORTANT]
   >
   >Une fois que vous avez lancé l&#39;analyse, la date de contact que vous avez définie est figée.Si vous modifiez cette date, veillez à relancer l&#39;analyse pour que vos modifications soient bien prises en compte.

   ![](assets/delivery-send-scheduled.png)

Dans la liste des diffusions, la diffusion apparaîtra avec le **[!UICONTROL En attente]** statut.

La planification peut aussi être paramétrée en amont via le bouton **[!UICONTROL Planification]** de la diffusion.

![](assets/delivery-scheduling-button.png)

Elle vous permet de différer la diffusion à une date ultérieure ou enregistrer la diffusion dans le calendrier prévisionnel.

* L&#39;option **[!UICONTROL Planifier la diffusion (pas d&#39;exécution automatique)]** permet de planifier une analyse prévisionnelle de la diffusion.

  Lorsque ce paramétrage est enregistré, la diffusion passe alors dans l&#39;état **[!UICONTROL Ciblage en attente]**.L&#39;analyse sera lancée à la date indiquée.

* L&#39;option **[!UICONTROL Planifier la diffusion (exécution automatique à la date prévue)]** permet d&#39;indiquer la date de contact.

  Cliquez sur le bouton **[!UICONTROL Envoyer]** et choisissez **[!UICONTROL Différer la diffusion]** puis lancez l&#39;analyse et confirmez l&#39;envoi. Une fois l&#39;analyse terminée, la cible de la diffusion est prête et les messages seront automatiquement envoyés à la date indiquée.

Les dates et heures sont entendues dans le fuseau horaire de l&#39;opérateur courant. La liste déroulante **[!UICONTROL Fuseau horaire]** située sous la zone de saisie de la date de contact permet d&#39;adapter automatiquement la date et l&#39;heure saisie dans le fuseau horaire sélectionné.

Ainsi, si vous planifiez une diffusion pour qu&#39;elle s&#39;exécute automatiquement à 8h heure de Londres, l&#39;heure est automatiquement convertie dans le fuseau sélectionné :

![](assets/delivery-schedule-time-zone.png)

<!--
## Adjust delivery failure management {#delivery-failure-management}

### Configure retries {#configure-retries}

Temporarily undelivered messages due to a **Soft** or **Ignored** error are subject to an automatic retry. The delivery failure types and reasons are presented in this [section](../../delivery/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

>[!IMPORTANT]
>
>For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the retry settings in the delivery are no longer used by Campaign. Soft bounce retries and the length of time between them are determined by the Enhanced MTA based on the type and severity of the bounce responses coming back from the message's email domain.

For on-premise installations and hosted/hybrid installations using the legacy Campaign MTA, the central section of the **[!UICONTROL Delivery]** tab for delivery parameters indicates how many retries should be performed the day after the delivery and the minimum delay between retries.

![](assets/s_ncs_user_wizard_retry_param.png)

By default, five retries are scheduled for the first day of the delivery with a minimum interval of one hour spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Validity]** tab (see [Defining validity period](#defining-validity-period)).

### Define the validity period {#define-validity-period}

When the delivery has been launched, the messages (and any retries) can be sent until the delivery deadline. This is indicated in the delivery properties, via the **[!UICONTROL Validity]** tab.

![](assets/s_ncs_user_email_del_valid_period.png)

* The **[!UICONTROL Delivery duration]** field lets you enter the limit for global delivery retries. This means that Adobe Campaign sends the messages beginning on the start date, and then, for messages returning an error only, regular, configurable retries are performed until the validity limit is reached.

  You can also choose to specify dates. To do this, select **[!UICONTROL Explicitly set validity dates]**. In this case, the delivery and validity limit dates also let you specify the time. The current time is used by default, but you can modify this directly in the input field.

  >[!IMPORTANT]
  >
  >For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the **[!UICONTROL Delivery duration]** setting in your Campaign email deliveries will be used only if set to **3.5 days or less**. If you define a value higher than 3.5 days, it will not be taken into account.

* **Validity limit of resources**: The **[!UICONTROL Validity limit]** field is used for uploaded resources, mainly for the mirror page and images. The resources on this page are valid for a limited time (to save disk space).

  The values in this field can be expressed in the units listed in [this section](../../platform/using/adobe-campaign-workspace.md#default-units).
-->