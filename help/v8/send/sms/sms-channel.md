---
title: Caractéristiques du canal SMS
description: Découvrez les caractéristiques du canal SMS
feature: SMS
role: User
level: Intermediate
badge: label="Disponibilité limitée" type="Informative"
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 23%

---


# Caractéristiques du canal SMS {#sms-channel}

>[!IMPORTANT]
>
>Cette documentation concerne Adobe Campaign v8.7.2 et versions ultérieures.
>
>Pour les versions plus anciennes, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol).


## Types de SMS {#sms-types}

Lors de l&#39;envoi de SMS par l&#39;intermédiaire d&#39;un fournisseur SMS, vous rencontrerez 3 types de SMS différents :

* **SMS MT (Mobile Terminated)** : il s&#39;agit d&#39;un SMS émis par Adobe Campaign vers des téléphones mobiles par l&#39;intermédiaire du fournisseur SMPP.
* **SMS MO (Mobile Originated)** : il s&#39;agit d&#39;un SMS envoyé par un mobile vers Adobe Campaign par l&#39;intermédiaire du fournisseur SMPP.
* **SMS SR (Status Report) or DR or DLR (Delivery Receipt)** : il s&#39;agit d&#39;un reçu de retour envoyé par le mobile à Adobe Campaign via le fournisseur SMPP indiquant que le SMS a été reçu avec succès. Adobe Campaign peut également recevoir des SR indiquant que le message n&#39;a pas pu être remis, souvent avec une description de l&#39;erreur.

Vous devez faire la distinction entre les accusés de réception (PDU RESP, partie intégrante du protocole SMPP) et SR. Un SR est un type de SMS qui est envoyé de bout en bout par le réseau, alors qu&#39;un accusé de réception n&#39;est qu&#39;une confirmation qu&#39;un transfert a réussi.

Les acquittements et les SR peuvent déclencher des erreurs, la distinction entre les deux facilitera la résolution des problèmes.

### Informations transportées par un SMS  {#sms-info}

Un SMS contient plus d&#39;informations que de texte. Voici une liste de ce que vous pouvez vous attendre à trouver dans un SMS :

* Le texte, qui est limité à 140 octets, ce qui signifie entre 70 et 160 caractères selon l&#39;encodage. Voir [Encodage du texte SMS](#sms-text-encoding) ci-dessous pour plus de détails et pour connaître les limitations.
* Adresse du destinataire, parfois appelée ADC ou MSISDN (le nom technique du &quot;numéro de téléphone&quot;). C&#39;est le numéro du mobile qui recevra le SMS.
* Adresse de l’expéditeur, qui peut être appelée oADC ou parfois ID de l’expéditeur. Il peut s&#39;agir d&#39;un numéro de téléphone (dans l&#39;utilisation quotidienne), d&#39;un numéro court (lorsqu&#39;il est envoyé par l&#39;intermédiaire d&#39;un fournisseur) ou d&#39;un nom (il s&#39;agit d&#39;une fonctionnalité en option, dans ce cas, vous ne pouvez pas répondre au SMS).
* Indicateur indiquant si le message est un message Flash (un message Flash est une fenêtre contextuelle qui n’est pas stockée en mémoire)
* Indicateur indiquant si un SR est attendu ou non.
* Date de validité, après laquelle aucun équipement réseau n’est autorisé à effectuer une nouvelle tentative (pas toujours présent ou respecté).
* Champ data_coding qui indique le codage du texte.

## Encodage du texte SMS {#sms-text-encoding}

>[!IMPORTANT]
>
>Le codage des SMS est un sujet vaste et complexe avec de nombreux pièges et mises en oeuvre non conformes !

La première règle est **toujours contacter le fournisseur SMPP en cas de problèmes de codage**. Ils sont les seuls à avoir une connaissance précise de l&#39;encodage qu&#39;ils prennent en charge et des règles spéciales qui peuvent s&#39;appliquer en raison de limitations de leur plateforme technique. Faites-leur vérifier ce que vous leur envoyez et ce qu&#39;ils vous renvoient, c&#39;est le seul chemin vers une interconnexion stable et réussie.

Les SMS utilisent un encodage spécial de 7 bits, souvent appelé encodage GSM7.  Wikipedia a [un bon article à ce sujet (GSM 03.38 en anglais)](https://en.wikipedia.org/wiki/GSM_03.38).

Dans le protocole SMPP, le texte GSM7 sera étendu à 8 bits par caractère pour faciliter le résolution des problèmes. La SMSC le compresse en 7 bits par caractère avant de l&#39;envoyer au mobile. Cela signifie que le champ short_message du SMS peut comporter jusqu&#39;à 160 octets dans le cadre SMPP, alors qu&#39;il est limité à 140 octets lorsqu&#39;il est envoyé sur le réseau mobile (le bit le plus significatif est simplement ignoré).

En cas de problème d&#39;encodage, voici quelques éléments importants à vérifier :
* Tout d’abord, assurez-vous de savoir quels caractères font partie de l’encodage. GSM7 est tristement célèbre pour sa prise en charge partielle des signes diacritiques (accents). Surtout en français, où &quot;é&quot; et &quot;è&quot; font partie de GSM7, mais &quot;ê&quot;, &quot;â&quot; ou &quot;ï&quot; non. Il en va de même pour l&#39;espagnol.
* Le C cédille (ç) n&#39;est présent que dans les majuscules de l&#39;alphabet GSM7, mais certains téléphones le rendent en minuscules ou &quot;smart&quot; : la recommandation générale est de l&#39;éviter complètement et de supprimer la cédille (elle est encore très lisible en français) ou de passer à UCS-2.
* **N’utilisez pas ASCII dans les SMS !**, sauf requête explicite du fournisseur SMPP : cet encodage réduit l&#39;espace car il contient des caractères 8 bits et une couverture inférieure à celle de GSM7. Ce codage peut être requis pour les réseaux CDMA (utilisés en Amérique du Nord).
* Latin-1 n&#39;est pas toujours pris en charge. Vérifiez la compatibilité avec votre fournisseur SMPP avant de tenter d&#39;utiliser Latin-1.
* Les tableaux de conversion de langue nationale ne sont pas pris en charge par le connecteur Adobe Campaign. Vous devez utiliser UCS-2 ou d’autres data_coding à la place.
* UCS-2 et UTF-16 sont souvent mélangés par les téléphones. Il s’agit d’un problème pour les personnes qui envoient des émoticônes et d’autres caractères rarement utilisés non présents dans UCS-2.
* Seuls les anciens téléphones n’ont pas de glyphes de police pour tous les caractères UCS-2. Les derniers smartphones ont tendance à être en mesure d&#39;afficher des caractères rares assez facilement, les smartphones plus anciens manquent souvent de beaucoup d&#39;émoticônes, et les téléphones de fonctionnalités très anciens ont généralement une prise en charge limitée à ce qui est utile dans la langue maternelle du pays dans lequel ils ont été achetés. Si vous voulez utiliser des émoticônes ou de l&#39;art ASCII, testez-le sur un large éventail de téléphones avant de l&#39;envoyer. L’aperçu de campagne ne simule pas les glyphes manquants et affiche tous les symboles disponibles dans le navigateur web qui affiche l’aperçu.

Le champ *data_coding* indique l’encodage utilisé. Un problème majeur est que la valeur 0 signifie *encodage SMSC par défaut* dans la spécification, en général cela signifie GSM7, mais ce n&#39;est pas toujours le cas. Vérifiez auprès du fournisseur SMPP quel encodage est associé à data_coding = 0. D&#39;autres valeurs data_coding tendent à suivre la spécification, mais la seule façon de s&#39;assurer est de vérifier auprès du fournisseur SMPP.

La taille maximale d&#39;un message dépend de son encodage. Ce tableau récapitule toutes les informations pertinentes :

| Encodage | data_coding habituel | Taille du message (caractères) | Taille de partie pour SMS à plusieurs parties | Caractères disponibles |
|:-:|:-:|:-:|:-:|:-:|  
| GSM 7 | 0 | 160 | 152 | Jeu de caractères de base GSM7 + extension (les caractères étendus prennent 2 caractères) |
| Latin -1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (varie d&#39;un téléphone à l&#39;autre) |

## SMS en plusieurs parties (SMS long) {#multipart-sms}

Les SMS en plusieurs parties (souvent appelés SMS longs) sont des SMS envoyés en plusieurs parties. En raison de limitations techniques du protocole de réseau mobile, un SMS ne peut pas dépasser 140 octets (voir la section Encodage du texte SMS ci-dessous pour connaître le nombre de caractères pouvant tenir dans un SMS), de sorte que les messages plus longs doivent être fractionnés.

Chaque partie d&#39;un long message est un SMS individuel. Ces pièces se déplacent indépendamment sur le réseau et sont assemblées par le téléphone mobile récepteur. Afin de gérer les reprises et les problèmes de connectivité de manière élégante, Campaign envoie les parties dans l&#39;ordre inverse et ne demande un SR que sur la première partie du message (celle qui est envoyée en dernier). Comme le téléphone portable n&#39;affiche un message qu&#39;à la réception de sa première partie, les reprises sur d&#39;autres parties ne produisent pas de doublons sur le téléphone mobile.

Le nombre maximal de SMS par message peut être défini par diffusion à l&#39;aide du paramètre Nombre maximal de SMS par message du modèle de diffusion. Les messages qui dépassent cette limite échouent lors de l&#39;envoi d&#39;un SMS avec une raison d&#39;échec trop longue.

Il y a deux façons d&#39;envoyer des SMS longs :

* UDH
* message_payload

UDH est la méthode par défaut et recommandée pour envoyer des messages longs. Dans ce mode, le connecteur divise le message en plusieurs PDU SUBMIT_SM contenant les informations UDH. Ce protocole est celui utilisé par les téléphones portables eux-mêmes, ce qui signifie que Campaign a le plus de contrôle sur la génération de messages, ce qui lui permet de calculer exactement combien de parties ont été envoyées et comment elles ont été fractionnées.

*message_payload* est un moyen d’envoyer tout le long message dans un seul PDU SUBMIT_SM. Le fournisseur devra le fractionner, ce qui signifie qu&#39;il est impossible pour Campaign de savoir exactement combien de parties ont été envoyées. Certains fournisseurs requièrent ce mode, mais ne l&#39;utilisent que s&#39;ils ne prennent pas en charge l&#39;UDH.

Pour plus d’informations sur le protocole et les formats, voir la description des champs esm_class, short_message et message_payload du PDU SUBMIT_SM ci-dessus.

>[!NOTE]
>
>Bien qu’Adobe Campaign prenne en charge à la fois UDH et message_payload pour l’envoi, seul message_payload est pris en charge pour les SMS entrants (MO).