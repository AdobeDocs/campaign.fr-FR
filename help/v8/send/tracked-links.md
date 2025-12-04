---
title: Configuration des liens trackés
description: Découvrez comment configurer des liens suivis dans les diffusions
feature: Monitoring
role: User, Developer
level: Beginner
exl-id: ed88e1d6-c0d5-4a85-9f3e-be670f4bcc10
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 85%

---

# Configuration des liens trackés {#how-to-configure-tracked-links}

La réception des messages ainsi que l’activation des liens insérés dans le contenu des messages peuvent être suivis pour chaque diffusion. Vous pouvez ainsi assurer un tracking du comportement des destinataires suite aux actions de diffusion dont ils ont été la cible.

>[!NOTE]
>
>Les liens inclus dans le contenu des emails qui comportent des éléments de personnalisation ont besoin d&#39;une syntaxe spécifique pour être suivis. Découvrez comment ajouter des liens dans des e-mails qui peuvent être personnalisés et qui prennent en charge le tracking dans [cette section](personalized-links.md).

Le tracking des messages est activé par défaut. Pour personnaliser le tracking des URL, procédez comme suit :

1. Sélectionnez l’option **[!UICONTROL Afficher les URL]**, située dans la section inférieure de l’assistant de diffusion, sous le contenu du message.

   ![](assets/s_ncs_user_email_del_display_urls.png)

   Lorsque vous sélectionnez une URL dans la liste des URL suivies, elle est mise en surbrillance dans le contenu de la diffusion, à l’exception du lien de la page miroir et du lien de désinscription qui sont fournis par défaut.

   ![](assets/s_ncs_user_email_del_show_urls.png)

1. Pour chaque URL du message, choisissez d’activer ou non le tracking.

   >[!IMPORTANT]
   >
   >Lorsque l’URL du lien est utilisée comme libellé, il est recommandé de désactiver le suivi afin de prévenir tout risque de rejet pour cause d’hameçonnage.
   >
   >Par exemple, si l’URL www.adobe.com est insérée dans le message et que l’URL est suivie, le contenu du lien hypertexte sera transformé en https://nlt.adobe.net/r/?id=xxxxxx. Il pourrait alors être considéré comme frauduleux par les clients de messagerie des destinataires.

1. Au besoin, modifiez le libellé du tracking, double-cliquez dessus et saisissez-en un nouveau.

   >[!NOTE]
   >
   >Les noms des URL suivies et des libellés être modifiés afin de simplifier la lecture des informations lors du suivi des diffusions. Deux URL ou deux libellés portant le même nom seront cumulés lors du calcul des clics.

1. Au besoin, modifiez le tracking, sélectionnez un nouveau mode dans la colonne **[!UICONTROL Tracking]** correspondant au lien visé, comme dans l’exemple ci-dessous :

   ![](assets/s_ncs_user_select_tracking_mode.png)

   Pour chaque URL, vous pouvez définir le mode de tracking sur l’une de ces valeurs :

   * **[!UICONTROL Activé]** : active le tracking de cette URL.
   * **[!UICONTROL Non activé]** : désactive le suivi de cette URL.
   * **[!UICONTROL Toujours activé]** : active toujours le tracking de cette URL. Cette information est enregistrée de sorte que si l&#39;URL réapparaît dans le contenu d&#39;un prochain message, son tracking est automatiquement activé.
   * **[!UICONTROL Jamais activé]** : n&#39;active jamais le tracking de cette URL. Cette information est enregistrée de sorte que si l&#39;URL réapparaît dans le contenu d&#39;un prochain message, son tracking est automatiquement désactivé.
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
