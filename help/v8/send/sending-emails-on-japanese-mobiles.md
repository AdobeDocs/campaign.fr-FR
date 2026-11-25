---
product: campaign
title: Envoyer des e-mails sur des mobiles japonais avec Adobe Campaign
description: Découvrez comment configurer, concevoir et envoyer des e-mails qui seront lus sur un mobile japonais
feature: Email, Email Design
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 02cca21f-b1ac-4ac2-9761-015f6c7f5567
TQID: 'https://experienceleague.adobe.com/LexEFgpaidGnonpgRFTasSk7Jr3Nc7443R8kj0kOLlM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 50d1fd2e-0fc9-5627-bbc9-02dbc9d15e08
    internal-label: Email
  - id: b631758a-142d-425f-b9aa-f756d85cb979
    internal-label: Campaign Email Designer
subfeature_v2:
  - id: c8da4fdd-eb94-4751-a43c-f82733fb2d6e
    internal-label: Email design
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 80%
---
# Envoyer des e-mails sur des mobiles japonais {#sending-emails-on-japanese-mobiles}

## Formats d&#39;email pour les mobiles japonais {#email-formats-for-japanese-mobiles}

Adobe Campaign gère trois formats japonais spécifiques pour les e-mails sur les appareils mobiles : **Deco-mail** (appareils mobiles DoCoMo), **Decore Mail** (appareils mobiles Softbank) et **Decoration Mail** (appareils mobiles KDDI AU). Ces formats imposent des contraintes particulières d’encodage, de structure et de taille. En savoir plus sur les limites et les recommandations dans [Limites et recommandations](#limitations-and-recommendations).

Pour qu&#39;un destinataire puisse recevoir correctement des messages dans l&#39;un de ces formats, il est recommandé de sélectionner **[!UICONTROL Deco-mail (DoCoMo)]**, **[!UICONTROL Decore Mail (Softbank)]** ou **[!UICONTROL Decoration Mail (KDDI AU)]** dans le profil correspondant :

![Onglet Général du destinataire avec la liste Format d&#39;email ouverte : Inconnu, Texte, HTML, Deco-mail, Decoration Mail, Decore Mail](assets/deco-mail_03.png)

Cependant, si vous laissez l&#39;option **[!UICONTROL Format des emails]** définie sur **[!UICONTROL Inconnu]**, **[!UICONTROL HTML]** ou **[!UICONTROL Texte]**, Adobe Campaign détectera automatiquement, lors de l&#39;envoi de l&#39;email, le format japonais à utiliser pour que le message s&#39;affiche correctement.

Ce système de détection automatique repose sur la liste des domaines prédéfinis dans l&#39;ensemble de règles de mail **[!UICONTROL Gestion des formats des emails]**. Pour plus d’informations sur la gestion des formats d’e-mail, reportez-vous à la [documentation de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/email-deliverability.html?lang=fr#managing-email-formats).

## Limites et recommandations {#limitations-and-recommendations}

Un certain nombre de contraintes s&#39;appliquent lorsque vous souhaitez envoyer des emails destinés à être lus sur un mobile opéré par un fournisseur japonais (Softbank, DoCoMo, KDDI AU).

Ainsi, vous devez :

* Utiliser exclusivement des images au format JPEG ou GIF.
* Créer une diffusion dont la somme des parties texte et HTML est strictement inférieure à 10 000 octets (pour KDDI AU et DoCoMo).
* Utiliser des images dont la taille totale avant encodage est inférieure à 100 Ko.
* Ne pas utiliser plus de 20 images par message.
* Utiliser un format HTML réduit (un nombre limité de balises sont disponibles pour chaque opérateur).

>[!NOTE]
>
>Des limitations spécifiques à chaque opérateur sont à prendre en compte lors de la création de votre message. Consultez la documentation de leur produit.


## Test du contenu d’e-mail {#testing-the-email-content}

### Prévisualisation du message {#previewing-the-message}

Adobe Campaign vous permet de vérifier que le format de votre message est adapté à l&#39;envoi sur un mobile japonais.

Vous pouvez d&#39;abord contrôler l&#39;affichage et le formatage au moment de la création du message, une fois que vous avez défini votre contenu et renseigné l&#39;objet de l&#39;email.

Dans l&#39;onglet **[!UICONTROL Aperçu]** de la fenêtre d&#39;édition du contenu, en cliquant sur **[!UICONTROL Détails > Diagnostic Deco-mail]**, vous pouvez alors :

* vérifier que les balises du contenu HTML sont conformes aux restrictions du format japonais.
* vérifier que le nombre d&#39;images dans le message ne dépasse pas la limite imposée par le format (20 images).
* vérifier la taille totale du message (inférieure à 100 Ko).

  ![Prévisualisez la fenêtre de résultats avec l&#39;onglet de diagnostic Deco-mail répertoriant les avertissements pour les balises non prises en charge et la limite de taille de 100 ko](assets/deco-mail_06.png)

### Exécution de la règle de typologie {#running-typology-rule}

En plus du diagnostic de prévisualisation, une deuxième vérification est effectuée lors de l&#39;envoi d&#39;un BAT ou d&#39;une diffusion : une règle de typologie spécifique, **[!UICONTROL Vérification du Deco-mail]**, est lancée au cours de l&#39;analyse.

>[!IMPORTANT]
>
>Cette règle de typologie s&#39;exécute seulement si au moins l&#39;un des destinataires est paramétré pour recevoir des emails au format **[!UICONTROL Deco-mail (DoCoMo)]**, **[!UICONTROL Decore Mail (Softbank)]** ou **[!UICONTROL Decoration Mail (KDDI AU)]**.

Cette règle permet de s&#39;assurer que la diffusion respecte les [contraintes de format](#limitations-and-recommendations) définies par les opérateurs japonais, notamment la taille totale de l&#39;email, la taille de ses parties HTML et texte, le nombre d&#39;images dans le message et les balises du contenu HTML.

### Envoi de BAT {#sending-proofs}

Vous pouvez envoyer des BAT pour tester votre diffusion. Lors de l’envoi d’un BAT, si vous avez recours à des adresses de substitution, veillez à saisir des adresses correspondant au format des e-mails du profil utilisé.

Par exemple, vous pouvez remplacer l&#39;adresse d&#39;un profil par test@softbank.ne.jp si le format des emails de ce profil a été défini au préalable sur **[!UICONTROL Decore Mail (Softbank)]**.

![Envoyez une boîte de dialogue de BAT dans Substitution du mode adresse avec une adresse de test softbank.ne.jp mappée à un profil](assets/deco-mail_05.png)

## Envoyer des messages {#sending-messages}

Pour envoyer une diffusion à des destinataires dont le format des emails est japonais, vous pouvez procéder de deux manières :

* Créez deux diffusions : une uniquement pour les destinataires japonais et une autre pour les autres destinataires. Consultez la section [Concevoir une diffusion spécifique pour les formats japonais](#designing-a-specific-delivery-for-japanese-formats).
* Créez une seule diffusion et Adobe Campaign détectera automatiquement le format à utiliser. Voir [Concevoir une diffusion pour tous les formats](#designing-a-delivery-for-all-formats).

### Conception dʼune diffusion spécifique pour les formats japonais {#designing-a-specific-delivery-for-japanese-formats}

Vous pouvez créer un workflow comprenant deux diffusions : une destinée à être lue sur un mobile japonais et une pour les destinataires avec un format d&#39;email standard.

Pour cela, utilisez une activité **[!UICONTROL Partage]** dans votre workflow et définissez les formats d&#39;email japonais (Deco-mail, Decoration Mail et Decore Mail) comme conditions de filtrage.

![Boîte de dialogue de filtrage avec trois conditions de format d&#39;email combinées par Or : Deco-mail, Decoration Mail et Decore Mail](assets/deco-mail_08.png)

![Workflow : requête, déduplication, puis partage par format d&#39;email vers une diffusion mobile japonaise et une diffusion standard](assets/deco-mail_07.png)

### Conception dʼune diffusion pour tous les formats {#designing-a-delivery-for-all-formats}

Lorsqu&#39;Adobe Campaign gère dynamiquement les formats en fonction du domaine (profils avec format des emails défini sur **[!UICONTROL Inconnu]**, **[!UICONTROL HTML]** ou **[!UICONTROL Texte]**), vous pouvez envoyer la même diffusion à tous vos destinataires.

Le contenu du message s&#39;affichera correctement pour les utilisateurs sur les mobiles japonais, tout comme pour les destinataires standard.

>[!IMPORTANT]
>
>Veillez toutefois à respecter les spécificités liées à chaque format d&#39;email japonais (Deco-mail, Decoration Mail et Decore Mail). Pour plus d&#39;informations sur les limitations, consultez [Limitations et recommandations](#limitations-and-recommendations).
