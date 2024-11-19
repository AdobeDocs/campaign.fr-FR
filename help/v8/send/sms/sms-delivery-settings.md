---
title: Paramètres de diffusion SMS
description: Découvrir comment configurer une diffusion SMS
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="Disponibilité limitée" type="Informative"
exl-id: c4d500ef-2339-491f-9ae2-9bfaf72088a9
source-git-commit: 826abd5c5f8b191d34abf724b91c5a82665d00a2
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 100%

---

# Paramètres de diffusion SMS {#sms-settings}

>[!IMPORTANT]
>
>Cette documentation concerne Adobe Campaign v8.7.2 et les versions ultérieures.
>
>Pour les versions plus anciennes, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

Les paramètres techniques nécessaires à une diffusion SMS sont les suivants :

* Le compte externe SMPP pour le routage des messages. [En savoir plus](smpp-external-account.md#smpp-connection-settings)
* Configurer l’onglet SMS. [Voici comment procéder](#sms-tab)

Vous pouvez configurer tout ceci dans un modèle de diffusion afin d’éviter d’effectuer le paramétrage pour chaque création de diffusion SMS.

## Configurer l’onglet SMS {#sms-tab}

![](assets/send_settings.png){zoomable="yes"}

Voici les informations dont vous avez besoin pour remplir ce formulaire. Chaque champ est expliqué ci-dessous :

* **[!UICONTROL Adresse d’expédition]**

  Ce champ est facultatif. Il permet d&#39;écraser l&#39;adresse de l&#39;expéditeur (oADC). Le contenu de ce champ est placé dans le champ *source_addr* du PDU SUBMIT_SM.

  Le champ est limité à 21 caractères par la spécification SMPP, mais certains fournisseurs peuvent autoriser des valeurs plus longues. Notez également que des restrictions très strictes peuvent être appliquées dans certains pays (longueur, contenu, caractères autorisés, etc.). Ainsi, vous devrez peut-être vérifier que le contenu que vous placez ici est légal. Faites particulièrement preuve de prudence lorsque vous utilisez des champs personnalisés.

  Si ce champ est laissé vide, la valeur du champ Numéro source défini dans le compte externe sera utilisée. Si les deux valeurs sont vides, le champ *source_addr* est vide.

* **[!UICONTROL Identifiant service ou programme]**

  >[!NOTE]
  >
  >L’utilisation de cette fonctionnalité est déconseillée. Les paramètres SMPP facultatifs offrent une mise en œuvre beaucoup plus flexible.
  >
  >Les deux fonctionnalités ne peuvent pas être utilisées en même temps.

  Associé au paramètre de compte externe correspondant, permet d’envoyer un paramètre facultatif avec chaque MT. Ce champ définit la partie valeur du fichier TLV.

* **[!UICONTROL Mode de transmission]**

  Ce champ indique le type de SMS que vous souhaitez transférer : messages normaux ou flash, stockés sur le mobile ou la carte SIM. Ce paramètre est transmis dans le champ facultatif dest_addr_subunit du PDU SUBMIT_SM.

   * **Flash** définit la valeur sur 1. Cela envoie un message Flash qui s&#39;affiche sur le mobile et n&#39;est pas stocké en mémoire.
   * **Normal** définit la valeur sur 0. Cela envoie un message normal.
   * **Enregistrer sur mobile** définit la valeur sur 2. Cela dit au téléphone de stocker le SMS dans la mémoire interne.
   * **Enregistrer sur le terminal** définit la valeur sur 3. Cela indique au téléphone de stocker le SMS dans la carte SIM.

* **[!UICONTROL Priorité, type de communication]**

  Ces champs sont ignorés par le connecteur SMPP étendu.

* **[!UICONTROL Nombre maximal de SMS par message]**

  Ce paramètre ne fonctionne que si le paramètre Payload du message est désactivé (voir dans les paramètres du compte externe pour plus d’informations). Si le message nécessite plus de SMS que cette valeur, une erreur est déclenchée.

  Le protocole SMS limite les SMS à 255 parties, mais certains téléphones portables ont du mal à assembler de longs messages avec plus de 10 parties environ, la limite dépend du modèle exact. Si vous voulez ne pas prendre de risque, ne dépassez pas 5 parties par message.

  En raison du fonctionnement des messages personnalisés dans Adobe Campaign, la taille des messages peut varier, de sorte qu’un grand nombre de messages très longs peut augmenter considérablement les coûts d’envoi : le définir sur une valeur raisonnable permet de contrôler ces coûts.

  Spécifier 0 désactive la limite.

* **[!UICONTROL Paramètres SMPP facultatifs (TLV)]**
Vous pouvez spécifier des champs supplémentaires à envoyer en tant que paramètres SMPP (TLV) facultatifs. Ces champs supplémentaires sont envoyés avec chaque MT et les champs personnalisés permettent d’avoir des valeurs différentes pour chaque MT.
Le tableau répertorie les paramètres facultatifs à envoyer avec chaque message. Les colonnes contiennent les informations suivantes :
   * **Libellé** : il s’agit d’un libellé de forme libre facultatif. Il n’est pas transmis au fournisseur. Vous pouvez fournir une description textuelle du paramètre.
   * **Balise** : valeur de balise, au format décimal (par exemple, 12345) ou hexadécimal avec le préfixe 0x (par exemple, 0x12ab). Les balises peuvent aller entre 0 et 65535. Demandez au fournisseur de services SMPP les balises qu’il prend en charge.
   * **Valeur** : valeur à envoyer dans le paramètre facultatif. Il s’agit d’un champ personnalisé.
   * **Format** : codage utilisé pour le paramètre. Vous pouvez sélectionner n’importe quel codage de texte pris en charge ou les formats binaires les plus courants. Demandez au fournisseur de services SMPP le format requis.
   * **Longueur maximale** : nombre maximal d’octets pour ce paramètre. Ceci est ignoré pour les champs binaires, car les champs binaires ont une taille fixe.

* **[!UICONTROL Utiliser des formats binaires pour TLV]**

  Campaign prend en charge l’envoi de TLV au format binaire. Le fichier binaire se limite à l’envoi de nombres.

  Comme les champs personnalisés génèrent toujours du texte, le champ personnalisé doit contenir une représentation décimale du nombre (toute chaîne est correcte tant qu’elle ne contient que des chiffres). Les valeurs peuvent être signées ou non, le moteur de personnalisation les convertit simplement en la bonne représentation binaire.

  Lors de l’utilisation de formats binaires, les valeurs spéciales «  » (chaîne vide), « null » et « undefined » désactivent complètement le champ sans générer d’erreur. Dans ces 3 cas spéciaux, la balise n’est pas transmise du tout. Cela permet de transmettre un TLV spécifique uniquement pour certains messages lorsque vous utilisez du code JavaScript soigneusement conçu dans le champ de personnalisation.

  >[!NOTE]
  >
  >Les formats binaires sont toujours codés dans un format big-endian.

