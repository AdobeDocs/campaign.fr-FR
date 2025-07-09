---
title: Caractéristiques du canal SMS
description: En savoir plus sur les caractéristiques du canal SMS
feature: SMS
role: User
level: Intermediate
exl-id: abab6f15-43ea-42fc-817b-8dbd88df82f7
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 98%

---

# Caractéristiques du canal SMS {#sms-channel}

>[!IMPORTANT]
>
>Cette documentation s’applique à Adobe Campaign v8.7.2 et versions ultérieures. Pour passer de l’ancien au nouveau connecteur SMS, reportez-vous à cette [note technique](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Pour les versions plus anciennes, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Types de SMS {#sms-types}

Lorsque vous enverrez des SMS par l’intermédiaire d’un fournisseur de services SMS, vous rencontrerez trois types de SMS différents :

* **SMS MT (Mobile Terminated)** : il s’agit d’un SMS émis par Adobe Campaign vers les téléphones portables par l’intermédiaire du fournisseur SMPP.
* **SMS MO (Mobile Originated)** : il s’agit d’un SMS envoyé par un téléphone mobile à Adobe Campaign par l’intermédiaire du fournisseur SMPP.
* **SMS SR (Status Report) ou DR ou DLR (Delivery Receipt)** : il s’agit d’un accusé de réception envoyé par le téléphone mobile à Adobe Campaign par l’intermédiaire du fournisseur SMPP indiquant que le SMS a été reçu. Adobe Campaign peut également recevoir des SR indiquant que le message n’a pas pu être remis, souvent avec une description de l’erreur.

Vous devez faire la distinction entre les accusés de réception (PDU RESP, partie du protocole SMPP) et les SR. Un SR est un type de SMS qui est envoyé par le réseau de bout en bout, alors qu’un accusé de réception n’est qu’une confirmation de la réussite d’un transfert.

Les accusés de réception et les SR peuvent déclencher des erreurs, la distinction entre les deux facilitera le résolution des problèmes.

### Informations transportées par un SMS  {#sms-info}

Un SMS contient plus d&#39;informations que de texte. Voici une liste de ce que vous pouvez vous attendre à trouver dans un SMS :

* Le texte, qui est limité à 140 octets, ce qui signifie entre 70 et 160 caractères selon l&#39;encodage. Voir [Encodage du texte SMS](#sms-text-encoding) ci-dessous pour plus de détails et pour connaître les limitations.
* Adresse de la personne destinataire, parfois appelée ADC ou MSISDN (le nom technique pour « numéro de téléphone »). C’est le numéro du mobile qui recevra le SMS.
* Adresse de l’expéditeur ou de l’expéditrice, souvent appelée oADC, peut aussi être désignée sous le terme d’ID d’expéditeur ou d’expéditrice. Il peut s’agir d’un numéro de téléphone (pour un usage courant), d’un code court (lorsqu’il est envoyé par l’intermédiaire d’un fournisseur) ou d’un nom (il s’agit d’une fonctionnalité en option, dans ce cas, vous ne pouvez pas répondre au SMS).
* Un indicateur permettant de savoir si le message est un message Flash (un message Flash est une fenêtre contextuelle qui n’est pas stockée en mémoire).
* Indicateur indiquant si un SR est attendu ou non.
* Une date de validité. Une fois dépassée, aucun équipement réseau n’est autorisé à réessayer (pas toujours présente ou respectée).
* Un champ data_coding qui indique l’encodage du texte.

## Encodage du texte SMS {#sms-text-encoding}

>[!IMPORTANT]
>
>L’encodage des SMS est un sujet vaste et complexe, avec de nombreux écueils et des implémentations qui ne respectent pas les normes.

La première règle est de **toujours contacter le fournisseur SMPP en cas de problèmes d’encodage**. Seuls les fournisseurs SMSC ont une connaissance précise de l’encodage qu’ils prennent en charge et des règles spéciales qui peuvent s’appliquer en raison de limitations de leur plateforme technique. Assurez-vous qu’ils vérifient attentivement les informations échangées, car c’est la clé pour garantir une interconnexion fiable et efficace.

Les messages SMS utilisent un encodage spécial de 7 bits, souvent appelé encodage GSM7.  Wikipedia propose [un excellent article sur ce sujet (GSM 03.38 en anglais)](https://en.wikipedia.org/wiki/GSM_03.38).

Dans le protocole SMPP, le texte GSM7 sera étendu à 8 bits par caractère pour faciliter le résolution des problèmes. La SMSC le compresse en 7 bits par caractère avant de l&#39;envoyer au mobile. Cela signifie que le champ short_message du SMS peut comporter jusqu’à 160 octets dans le cadre SMPP, alors qu’il est limité à 140 octets lorsqu’il est envoyé sur le réseau mobile (le bit le plus important est simplement supprimé).

En cas de problème d’encodage, voici quelques éléments importants à vérifier :
* Assurez-vous d’abord de bien identifier quels caractères appartiennent à quel encodage. Le GSM7 est souvent critiqué pour sa gestion imparfaite des accents et autres signes diacritiques. Surtout en français, où &quot;é&quot; et &quot;è&quot; font partie de GSM7, mais &quot;ê&quot;, &quot;â&quot; ou &quot;ï&quot; non. Il en va de même pour l&#39;espagnol.
* Le C avec cédille (ç) n’est présent que dans les majuscules de l’alphabet GSM7, mais certains téléphones le rendent en minuscules ou « smart » : la recommandation générale est de l’éviter complètement et de supprimer la cédille (le texte reste tout à fait compréhensible en français) ou de passer au système UCS-2.
* **Évitez d’utiliser le format ASCII dans les SMS.** sauf requête explicite du fournisseur SMPP : cet encodage réduit l’espace car il contient des caractères 8 bits et une couverture inférieure à celle de GSM7. Cet encodage peut être requis pour les réseaux CDMA (utilisés en Amérique du Nord).
* Latin-1 n’est pas toujours pris en charge. Vérifiez la compatibilité avec votre fournisseur SMSC avant de tenter d’utiliser Latin-1.
* Les tableaux de conversion de langue nationale ne sont pas pris en charge par le connecteur Adobe Campaign. Vous devez utiliser UCS-2 ou un autre data_coding à la place.
* UCS-2 et UTF-16 sont souvent mélangés par les téléphones. Il s’agit d’un problème pour les personnes envoyant des émoticônes et autres caractères peu utilisés, non présents dans UCS-2.
* Certains téléphones plus anciens ne contiennent pas de glyphes de police pour tous les caractères UCS-2. Les smartphones les plus récents sont généralement capables d’afficher des caractères rares assez facilement, les smartphones plus anciens manquent souvent d’émojis et les très anciens téléphones fonctionnels ont généralement un support limité à ce qui est utile dans la langue maternelle du pays dans lequel ils ont été achetés. Si vous voulez utiliser un emoji ou ASCII-art, testez-le sur un large éventail de téléphones avant de procéder à l’envoi. L’aperçu Campaign ne simule pas les glyphes manquants et affiche les symboles disponibles dans le navigateur Web dans laquel il s’affiche.

Le champ *data_coding* indique l’encodage utilisé. Il existe un problème majeur, selon lequel la valeur 0 signifie *encodage SMSC par défaut* dans la spécification (GSM7 en général), bien que cela ne soit pas toujours le cas. Vérifiez auprès du fournisseur SMPP quel encodage est associé à data_coding = 0. D’autres valeurs data_coding tendent à suivre la spécification, mais la seule façon de s’en assurer est de vérifier auprès du fournisseur SMPP.

La taille maximale d&#39;un message dépend de son encodage. Ce tableau récapitule toutes les informations pertinentes :

| Encodage | data_coding habituel | Taille du message (caractères) | Taille de partie pour SMS à plusieurs parties | Caractères disponibles |
|:-:|:-:|:-:|:-:|:-:|  
| GSM 7 | 0 | 160 | 152 | Jeu de caractères de base GSM7 + extension (les caractères étendus prennent 2 caractères) |
| Latin -1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (varie d&#39;un téléphone à l&#39;autre) |

## SMS en plusieurs parties (SMS long) {#multipart-sms}

Les SMS en plusieurs parties, ou SMS longs, sont des SMS envoyés en plusieurs parties. En raison de limitations techniques du protocole de réseau mobile, un SMS ne peut pas dépasser 140 octets (voir la section Encodage du texte SMS ci-dessous pour connaître le nombre de caractères pouvant tenir dans un SMS). Ainsi, les messages plus longs doivent être fractionnés.

Chaque partie d&#39;un long message est un SMS individuel. Ces pièces se déplacent indépendamment sur le réseau et sont assemblées par le téléphone mobile récepteur. Afin de gérer harmonieusement les reprises et les problèmes de connectivité, Campaign envoie les parties dans l’ordre inverse et ne demande un SR que sur la première partie du message (celle qui est envoyée en dernier). Comme le téléphone mobile n’affiche un message qu’à la réception de sa première partie, les reprises sur d’autres parties ne produisent pas de doublons sur le téléphone mobile.

Le nombre maximal de SMS par message peut être défini par diffusion à l’aide du paramètre Nombre maximal de SMS par message défini dans le modèle de diffusion. Les messages qui dépassent cette limite échouent lors de l&#39;envoi d&#39;un SMS avec une raison d&#39;échec trop longue.

Il y a deux façons d&#39;envoyer des SMS longs :

* UDH
* message_payload

UDH est la méthode par défaut et recommandée pour envoyer des messages longs. Dans ce mode, le connecteur divise le message en plusieurs PDU SUBMIT_SM avec les informations UDH. Ce protocole est celui utilisé par les téléphones mobiles eux-mêmes, permettant ainsi à Campaign de contrôler de manière optimale la génération de messages, afin de calculer exactement combien de parties ont été envoyées et comment elles ont été fractionnées.

*message_payload* permet d’envoyer tout le long message en un seul PDU SUBMIT_SM. Le fournisseur doit le fractionner, ce qui signifie qu’il est impossible pour Campaign de savoir exactement combien de parties ont été envoyées. Certains fournisseurs requièrent ce mode, mais ne l’utilisent que s’ils ne prennent pas en charge l’UDH.

Consultez la description des champs esm_class, short_message et message_payload du PDU SUBMIT_SM pour plus d’informations sur le protocole et les formats.

>[!NOTE]
>
>Bien qu’Adobe Campaign prenne en charge à la fois UDH et message_payload pour l’envoi, seul message_payload est pris en charge pour les SMS entrants (MO).
