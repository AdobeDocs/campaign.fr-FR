---
title: Configuration des liens trackés
description: Découvrez comment configurer des liens suivis dans les diffusions
feature: Monitoring
role: User, Developer
level: Beginner
exl-id: ed88e1d6-c0d5-4a85-9f3e-be670f4bcc10
TQID: https://experienceleague.adobe.com/VeDV3OsmWKOlAGNhUiDb5uDmjX0lXWa1RnA3KHm6F-w
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 593
ht-degree: 52%

---

# Configuration des liens trackés {#how-to-configure-tracked-links}

Pour chaque diffusion, vous pouvez suivre la réception des messages et l&#39;activation des liens insérés dans le contenu des messages. Vous pouvez ainsi suivre le comportement des destinataires à la suite des actions de diffusion qui les ont ciblés.

>[!NOTE]
>
>Les liens inclus dans le contenu des emails qui comportent des éléments de personnalisation ont besoin d&#39;une syntaxe spécifique pour être suivis. Découvrez comment ajouter des liens dans des e-mails qui peuvent être personnalisés et qui prennent en charge le tracking dans [cette section](personalized-links.md).

Le tracking des messages est activé par défaut. Pour personnaliser le suivi des URL, procédez comme suit :

1. Sélectionnez l’option **[!UICONTROL Afficher les URL]**, située dans la section inférieure de l’assistant de diffusion, sous le contenu du message.

   ![](assets/s_ncs_user_email_del_display_urls.png)

   Lorsque vous sélectionnez une URL dans la liste des URL suivies, elle est mise en surbrillance dans le contenu de la diffusion, à l’exception du lien de la page miroir et du lien de désinscription qui sont fournis par défaut.

   ![](assets/s_ncs_user_email_del_show_urls.png)

1. Pour chaque URL du message, choisissez d’activer ou non le tracking.

   >[!IMPORTANT]
   >
   >Lorsque l’URL du lien est utilisée comme libellé, il est recommandé de désactiver le suivi afin de prévenir tout risque de rejet pour cause d’hameçonnage.
   >
   >Par exemple, si l’URL www.adobe.com est insérée dans le message et que le suivi y est activé, le contenu du lien hypertexte sera modifié en https://nlt.adobe.net/r/?id=xxxxxx. Cela signifie qu’il peut être considéré comme frauduleux par les clients de messagerie des destinataires.

1. Au besoin, modifiez le libellé du tracking, double-cliquez dessus et saisissez-en un nouveau.

   >[!NOTE]
   >
   >Les libellés des URL suivies et des libellés peuvent être modifiés afin de simplifier la lecture des informations lors du suivi des diffusions. Deux URL ou deux libellés portant le même nom seront ajoutés lors du calcul du nombre de clics.

1. Au besoin, modifiez le tracking, sélectionnez un nouveau mode dans la colonne **[!UICONTROL Tracking]** correspondant au lien visé, comme dans l’exemple ci-dessous :

   ![](assets/s_ncs_user_select_tracking_mode.png)

   Pour chaque URL, vous pouvez définir le mode de tracking sur l’une de ces valeurs :

   * **[!UICONTROL Activé]** : active le tracking de cette URL.
   * **[!UICONTROL Non activé]** : désactive le suivi de cette URL.
   * **[!UICONTROL Toujours activé]** : active toujours le tracking de cette URL. Ces informations sont enregistrées afin que la prochaine fois, si l’URL apparaît à nouveau dans le contenu d’un futur message, son tracking soit automatiquement activé.
   * **[!UICONTROL Jamais trackée]** : n&#39;active jamais le tracking de cette URL. Ces informations sont enregistrées afin que la prochaine fois, si l’URL apparaît à nouveau dans un futur message, son tracking soit automatiquement désactivé.
   * **[!UICONTROL Opt-out]** : considère cette URL comme une option d&#39;opt-out ou une URL de désabonnement.
   * **[!UICONTROL Page miroir]** : considère cette URL comme une URL de page miroir.

1. De plus, vous pouvez sélectionner une catégorie pour chaque URL suivie dans la liste déroulante de la colonne **[!UICONTROL Catégorie]**. Ces catégories peuvent être affichées dans les rapports, par exemple dans le rapport **[!UICONTROL URL et flux de clics]** (voir [cette section](../reporting/delivery-reports.md#urls-and-click-streams)). Les catégories sont définies dans une énumération spécifique : **[!UICONTROL urlCategory]**. En savoir plus sur l’utilisation des énumérations dans [cette section](../config/enumerations.md).

## Bonnes pratiques relatives aux délimiteurs d’URL {#url-delimiters}

Nous vous recommandons vivement de placer les URL dans des délimiteurs dans l&#39;onglet **[!UICONTROL Contenu textuel]** avant d&#39;appliquer la formule de tracking. Les délimiteurs d&#39;URL que vous saisissez dans cet onglet sont utilisés par Adobe Campaign pour identifier les URL dans les chaînes de caractères. Vous pouvez utiliser les paires de délimiteurs suivantes :

* Parenthèses ( )
* Crochets [ ]
* Accolades { }

Dans cet exemple, l&#39;URL https://www.adobe.com est suivie d&#39;un point-virgule. Le point-virgule peut être interprété par les clients de messagerie des destinataires comme faisant partie de l&#39;URL. Par conséquent, le lien peut être rompu. Pour éviter ce problème, vous pouvez placer l&#39;URL dans des délimiteurs de l&#39;une des façons suivantes :

* (https://www.adobe.com);
* [https://www.adobe.com];
* {https://www.adobe.com};
