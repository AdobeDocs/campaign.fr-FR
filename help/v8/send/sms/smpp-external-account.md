---
title: Paramètres du compte externe SMPP
description: Découvrez comment configurer le compte externe SMPP
feature: SMS
role: User
level: Intermediate
badge: label="Disponibilité limitée" type="Informative"
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '3652'
ht-degree: 27%

---


# Paramètres du compte externe SMPP {#smpp-external-account}

Adobe Campaign utilise le protocole SMPP pour envoyer des SMS à un fournisseur de services.

>[!IMPORTANT]
>
>Adobe Campaign prend en charge le protocole SMPP version 3.4.


Le connecteur SMS dans Adobe Campaign offre de nombreuses options pour adapter son comportement afin d&#39;être compatible avec la plupart des fournisseurs SMPP, qui ont tendance à s&#39;écarter un peu de la spécification officielle.

>[!IMPORTANT]
>
>La configuration d&#39;une connexion à un nouveau fournisseur peut nécessiter des compétences techniques, des connaissances relatives au protocole TCP, au binaire, à la représentation hexadécimale et aux encodages de texte. Il faudra également une coopération active avec le fournisseur.

L&#39;équipement réseau côté fournisseur SMS est souvent appelé SMSC.

## Paramètres de connexion {#smpp-connection-settings}

![](assets/smpp_connection_settings.png){zoomable="yes"}

Voici les paramètres et leur rôle nécessaires pour configurer la connexion :

* **Nom de l&#39;implémentation du SMSC** : définit le nom de l&#39;implémentation du SMSC. Il doit être défini sur le nom de votre fournisseur. Le rôle de ce champ est décrit dans la section Gestion des erreurs SMPP .
* **Serveur** : nom DNS ou adresse IP du serveur auquel se connecter.
* **Port** : port TCP auquel se connecter.
* **Compte** : connexion de la connexion. Transmis dans le champ system_id du PDU BIND.
* **Mot de passe** : mot de passe de la connexion SMPP. Transmis dans le champ du mot de passe du PDU BIND.
* **Type de système** : valeur transmise dans le champ system_type du PDU BIND. Certains fournisseurs ont besoin d&#39;une valeur spécifique ici.
* **Nombre de connexions enfant MTA** : définit le nombre de connexions ouvertes par thread d’envoi.
Le nombre total de connexions peut être calculé à l&#39;aide de cette formule :
  *Nombre total de connexions = Nombre de processus SMS * nombre de threads d’envoi * nombre de connexions enfant MTA*

   * Le nombre de processus SMS est normalement de 1. Sur certaines instances très performantes, plusieurs processus SMS peuvent être démarrés en parallèle.
   * Le nombre de threads d&#39;envoi est défini dans serverConf (paramètre sendThreads ). Par défaut, il est défini sur 1.
   * Le nombre de connexions enfant MTA est ce paramètre dans le compte externe.

  Avec les valeurs par défaut, ce paramètre définit directement le nombre de connexions.

En **mode émetteur-récepteur**, il s’agit du nombre total de connexions.

En **mode Transmitter + receiver**, cela définit le nombre de paires émetteur + récepteur (une paire = un émetteur + un récepteur).
Il n&#39;existe aucun moyen de modifier l&#39;équilibre entre les émetteurs et les récepteurs.

* **Envoyer des messages par le biais d&#39;un processus dédié** :
Pour Adobe Campaign v8.7.2 et versions ultérieures, cette option doit toujours être activée. Cela a de nombreux impacts sur le mode de traitement des messages.
* **Mode de connexion SMPP** :
Définissez la connexion en mode Transmitter ou en mode Transmitter + receiver séparé.
   * Transmitter + receiver (ou TX+RX) : deux connexions TCP distinctes sont utilisées pour transmettre et recevoir des messages.
   * Transceiver (ou TRX) : une connexion TCP unique est utilisée pour transmettre et recevoir des messages.
* **Utiliser des paramètres différents pour le récepteur** :
Disponible uniquement en mode Transmitter + receiver .
Lorsque la case est décochée, les mêmes paramètres sont utilisés pour l&#39;émetteur et le récepteur. Lorsque la case est cochée, les paramètres standard s&#39;appliquent uniquement à l&#39;émetteur, tandis que les paramètres du récepteur s&#39;appliquent uniquement au récepteur.
* **Serveur du récepteur, port, compte, mot de passe, type de système**
Ces paramètres s&#39;appliquent au récepteur en mode Transmitter + receiver . Ils fonctionnent comme la partie émetteur, voir ci-dessus pour [plus de détails](#smpp-connection-settings).
* **Activer les traces SMPP en mode verbeux dans le fichier journal**
Lorsque cette option est activée, les journaux supplémentaires sont générés dans le fichier journal. Cela s’avère très utile pour le dépannage, mais doit être conservé désactivé sur les instances à débit élevé si aucun dépannage n’est requis.

## Paramètres du canal SMPP {#smpp-channel-settings}

![](assets/smpp_channel_settings.png){zoomable="yes"}

### Autoriser la translittération des caractères

La translitération est le processus de recherche de caractères équivalents à ceux qui sont manquants. Par exemple, le caractère français &quot;ê&quot; (avec un accent circonflexe) est absent de l&#39;encodage GSM, mais il peut être remplacé par &quot;e&quot; sans nuire à la lisibilité.

Si cette case n&#39;est pas cochée, l&#39;encodage du texte échoue s&#39;il ne peut pas coder la chaîne telle quelle.

Si cette case est cochée, l&#39;encodage de texte tentera de convertir la chaîne en une version approximative plutôt que d&#39;échouer. Si certains caractères n&#39;ont pas d&#39;équivalent en encodage de cible, l&#39;encodage de texte échoue.

Pour obtenir une explication plus générale du processus d&#39;encodage, consultez la section [Définir un mapping spécifique du paramètre d&#39;encodage](#mapping-encodings).

### Numéro source

Définit l&#39;adresse source par défaut des messages. Ce paramètre s&#39;applique uniquement si le numéro source a été laissé vide dans la diffusion. Par défaut, le champ du numéro source n&#39;est pas transmis.Le fournisseur le remplace donc par le numéro court.

Cela active la fonction de remplacement de l’adresse de l’expéditeur/oADC.

### NPI/TON source, NPI/TON destination

TON (Type de numéro) et NPI (Indicateur de plan de numérotation) (décrits à la section 5.2.5 de la spécification SMPP 3.4). Ces valeurs doivent être définies selon les besoins du fournisseur.

Ils sont transmis tels quels dans les champs source_addr_ton, source_addr_npi, dest_addr_ton et dest_addr_npi du PDU SUBMIT_SM.

### Service type

Ce champ est transmis tel quel dans le champ service_type du PDU SUBMIT_SM. Définissez-le selon les besoins du fournisseur.

## Débits et délais {#smpp-delays}

![](assets/smpp_throughput.png){zoomable="yes"}

Ces paramètres contrôlent tous les aspects du timing du canal SMPP. Certains fournisseurs ont besoin d&#39;un contrôle très précis du taux de message, des délais de fenêtre et des délais de reprise. Ces paramètres doivent donc être définis sur des valeurs correspondant à la capacité du fournisseur et aux conditions indiquées dans son contrat.

### Fenêtre d&#39;émission

La fenêtre correspond au nombre de PDU SUBMIT_SM pouvant être envoyés sans attendre un SUBMIT_SM_RESP correspondant.

Exemple de transmission avec une fenêtre maximale de 4 :

![](assets/sms_sending_window.png){zoomable="yes"}

La fenêtre permet d’augmenter le débit lorsque la liaison réseau présente une latence élevée. La valeur de la fenêtre doit être au moins égale au nombre de SMS/s multiplié par la latence du lien (en secondes), de sorte que le connecteur n&#39;attend jamais un SUBMIT_SM_RESP avant d&#39;envoyer le message suivant.

Si la fenêtre est trop grande, vous pouvez envoyer plus de messages en double en cas de problème de connexion (cas rare). En outre, la plupart des fournisseurs ont une limite très stricte pour la fenêtre et refusent les messages qui dépassent la limite.

Comment calculer la formule optimale de la fenêtre d&#39;émission :

Mesurez la latence maximale entre SUBMIT_SM et SUBMIT_SM_RESP.
Multipliez cette valeur (en secondes) par le débit max MT : cela donnera la valeur optimale de la fenêtre d&#39;envoi.
Exemple : si 300 SMS/s sont définis dans le débit max MT et qu&#39;il y a une latence de 100 ms entre SUBMIT_SM et SUBMIT_SM_RESP en moyenne, la valeur optimale sera 300×0.1 = 30.

En cas de doute, préférez une fenêtre plus grande pour éviter les problèmes de performances.

### Débit max de MT

Nombre maximal de MT par seconde et par connexion. Ce paramètre est strictement appliqué, le MTA n&#39;enverra jamais de messages plus rapidement que cette limite. Il est utile pour les fournisseurs qui nécessitent un ralentissement précis.

Pour connaître la limite de débit totale, multipliez ce nombre par le nombre total de connexions (voir la formule ci-dessus).

0 signifie pas de limite, le MTA enverra le MT aussi vite que possible.

Il est généralement recommandé de maintenir ce paramètre sous 1 000, car il est impossible de garantir un débit précis au-dessus de ce nombre, à moins que l&#39;architecture finale ne soit correctement évaluée et que le fournisseur SMPP ait été spécifiquement demandé. Il peut être préférable d&#39;augmenter le nombre de connexions au-dessus de 1000 MT/s.

### Temps avant reconnexion

Lorsque la connexion TCP est perdue, le connecteur attend ce nombre de secondes avant d&#39;essayer d&#39;établir une connexion.

### Délai d&#39;expiration des MT

Il s’agit du délai entre SUBMIT_SM et son SUBMIT_SM_RESP correspondant. Si le RESP n&#39;est pas reçu à temps, le message sera considéré comme ayant échoué et la stratégie de reprise globale du MTA s&#39;appliquera.

### Délai d&#39;attente maximal d&#39;un bind

Délai entre la tentative de connexion TCP et la réponse BIND_*_RESP. Lorsqu&#39;il expire, la connexion est fermée par le connecteur Campaign et il faudra attendre le temps avant reconnexion avant de réessayer.

### Période d&#39;enquire_link

enquire_link est un type spécial de PDU envoyé pour maintenir la connexion en vie. Cette période est en secondes. Le connecteur de campagne n&#39;envoie enquire_link que lorsque la connexion est inactive pour économiser la bande passante. Si aucun RESP n&#39;est reçu après deux fois cette période, la connexion est considérée comme étant inactive et un processus de reconnexion est déclenché.

## Mapping des encodages {#mapping-encodings}

Pour plus d&#39;informations sur l&#39;encodage de texte, reportez-vous à la [section Encodage de texte SMS](sms-channel.md#sms-text-encoding) .

Ce paramètre permet de définir un mapping de codage personnalisé, différent de la spécification. Vous pourrez déclarer une liste d&#39;encodages, ainsi que leur valeur data_coding. Le MTA tente d&#39;encoder en utilisant le premier encodage de la liste ; s&#39;il échoue, il tente d&#39;utiliser le prochain encodage de la liste, etc... Si aucun encodage ne peut être utilisé pour encoder le message, une erreur se produit. Une fois l&#39;encodage trouvé, le MTA crée le PDU SUBMIT_SM avec le texte codé et le champ data_coding avec la valeur spécifiée dans le tableau.

L&#39;ordre des éléments dans le tableau est important : les encodages sont testés de haut en bas. Placez l&#39;encodage le moins cher ou le plus recommandé en haut de la liste, puis choisissez des encodages de plus en plus chers (ou moins souhaitables).

Notez que UCS-2 n’échouera jamais, car il peut coder tous les caractères pris en charge dans Campaign. Veuillez noter que la longueur maximale d&#39;un SMS UCS-2 est beaucoup plus petite (70 caractères uniquement).

Vous pouvez également utiliser ce paramètre pour forcer l&#39;utilisation d&#39;un encodage spécifique en ne déclarant que 1 ligne dans le tableau de mapping.

Le mapping par défaut utilisé lorsque la case à cocher n&#39;est pas cochée est équivalent au tableau suivant :

| data_coding | Encodage |
|:-:|:-:|
| 0 | GSM |
| 8 | UCS -2 |

Cela signifie que le MTA essaiera de coder le message dans GSM, s&#39;il réussit, il l&#39;envoie avec data_coding défini sur 0.

Si le message ne peut pas être codé en GSM, il sera codé en UCS-2 et définit data_coding sur 8.

## Spécificités du SMSC {#smsc-specificities}

![](assets/smsc_specificities.png){zoomable="yes"}

### Activer message_payload

Lorsque cette option est désactivée, les SMS longs sont fractionnés par le MTA et envoyés dans plusieurs PDU SUBMIT_SM avec UDH. Le message est recomposé par le téléphone portable suivant les données UDH.

Lorsque cette case est cochée, un SMS long est envoyé dans un PDU SUBMIT_SM, plaçant le texte dans le champ facultatif message_payload (voir la spécification SMPP pour plus d’informations à ce sujet).

Si cette fonctionnalité est activée, Campaign ne pourra pas comptabiliser les parties SMS individuellement : tous les messages seront comptabilisés comme envoyés en une seule partie.

### Envoyer le numéro de téléphone complet

Lorsque cette case n&#39;est pas cochée, seuls les chiffres du numéro de téléphone sont envoyés au fournisseur (champ destination_addr du champ SUBMIT_SM ). Il s’agit du comportement par défaut, car l’indicateur de numéro international (généralement un préfixe +) est remplacé par les champs TON et NPI dans SMPP.

Si cette case est cochée, le numéro de téléphone est envoyé tel quel, sans prétraitement (ni espaces potentiels, préfixe + ou signes dièse/hachage/étoile).

Cette fonctionnalité a également un effet sur le comportement de la fonction de quarantaine de réponse automatique : lorsque la case n&#39;est pas cochée, un préfixe + est ajouté aux numéros de téléphone insérés dans la table des quarantaines afin de compenser la suppression du préfixe + du numéro de téléphone par le protocole SMPP lui-même.

### Liaison TON/NPI

TON (Type de numéro) et NPI (Indicateur de plan de numérotation) (décrits à la section 5.2.5 de la spécification SMPP 3.4). Ces valeurs doivent être définies selon les besoins du fournisseur.

Ils sont transmis tels quels dans les champs addr_ton et addr_npi du PDU BIND.

### Plage d&#39;adresses

Envoyé tel quel dans le champ address_range du PDU BIND. Cette valeur doit être définie selon les besoins du fournisseur.

### Nombre d&#39;acquittements d&#39;identifiant invalides

Limite le nombre de &quot;ID de message non valide&quot; DELIVER_SM_RESP pouvant être envoyé pour un seul SR. **Cette valeur ne doit être utilisée qu&#39;à des fins de résolution des problèmes en tant que solution de contournement** et définie sur 0 dans des conditions normales.

Explication détaillée : supposons que vous définissiez ce paramètre sur 2 :

* Le fournisseur envoie un SR (DELIVER_SM) avec l&#39;ID &quot;1234&quot;
* L&#39;ID &quot;1234&quot; est introuvable dans la base de données.
* Le connecteur comptabilise 1 erreur &quot;ID non valide&quot; pour cet ID, de sorte qu&#39;il envoie DELIVER_SM_RESP avec le code d&#39;erreur &quot;ID de message non valide&quot; (comportement normal).
* Le fournisseur tente à nouveau le même SR avec l&#39;ID &quot;1234&quot;
* L&#39;ID &quot;1234&quot; est toujours introuvable dans la base de données.
* Le connecteur comptabilise 2 erreurs &quot;ID non valide&quot; pour cet ID, de sorte qu&#39;il envoie DELIVER_SM_RESP &quot;OK&quot;, même s&#39;il n&#39;a pas été traité correctement.

Cette fonctionnalité est destinée à vider les tampons SR côté fournisseur lorsque des SR non valides bloquent les messages légitimes qui ne peuvent pas être traités.

La définition de ce champ sur 0 désactive le mécanisme de sorte que &quot;Identifiant de message non valide&quot; soit toujours renvoyé, il s’agit d’un comportement normal.

Si ce champ est défini sur 1, le connecteur répond toujours &quot;OK&quot;, même si l&#39;ID n&#39;est pas valide. Cette valeur doit être définie sur 1 uniquement utilisé sous supervision pour le dépannage et pour une durée minimale, par exemple pour récupérer d’un problème côté fournisseur.

### Expression régulière d&#39;extraction de l&#39;ID dans le SR

Le format SR n&#39;est pas strictement appliqué par la spécification du protocole SMPP. Il s’agit uniquement d’une recommandation décrite à l’annexe B de la spécification. C&#39;est pourquoi certains implémentateurs SMPP formattent ce champ différemment, de sorte que Campaign a besoin d&#39;un moyen d&#39;extraire le champ correct.

Par défaut, il capture jusqu’à 10 caractères alphanumériques après &quot;id:&quot;.

L’expression régulière doit comporter exactement un groupe de capture (une partie entre parenthèses). Les parenthèses doivent entourer la partie qui correspond à l&#39;identifiant. Le format d&#39;expression régulière est PCRE.

Lors de la modification de ce paramètre, veillez à inclure le plus de contexte possible pour éviter les faux triggers. S’il existe des préfixes spécifiques (tels que &quot;id:&quot; dans la norme), incluez-les dans l’expression régulière. Utilisez également autant que possible des délimiteurs de mots (\b) pour éviter de capturer du texte au milieu d’un mot.

Ne pas inclure suffisamment de contexte dans l&#39;expression régulière peut introduire un petit défaut de sécurité : le contenu réel du message peut être inclus dans le SR. Ainsi, si vous faites simplement correspondre un format d&#39;ID spécifique sans contexte (par exemple un UUID), il peut analyser le contenu réel du texte (par exemple un UUID incorporé dans le champ de texte) au lieu de l&#39;ID.

### Regex d&#39;extraction du statut dans le SR

Cette expression régulière capture le statut à partir du champ de texte des messages SR.

Par défaut, il capture entre 5 et 15 caractères après &quot;stat:&quot;.

L’expression régulière doit comporter **exactement un groupe de capture** (une partie contenue entre parenthèses). Les parenthèses doivent entourer la partie correspondant au statut. Le format d&#39;expression régulière est PCRE.

### Regex appliquée pour déterminer le statut de réussite

Cette expression régulière est appliquée au résultat de l’expression régulière précédente (&quot;Expression régulière d’extraction du statut&quot;). Si l’expression régulière correspond, le message est considéré comme réussi.

Par défaut, il correspond à tout ce qui commence par &quot;DELIV&quot;. Il correspond à la valeur standard &quot;DELIVRD&quot;.

### Regex appliquée pour déterminer le statut de l&#39;erreur

Cette expression régulière est appliquée au résultat de l’expression régulière précédente (&quot;Expression régulière d’extraction du statut&quot;). Si l’expression régulière correspond, le message est considéré comme erroné.

Par défaut, il correspond à tous les différents états d’erreur décrits dans la spécification.

### Regex d&#39;extraction du code d&#39;erreur dans le SR

Cette expression régulière capture le code d&#39;erreur à partir du champ de texte des messages SR.

Les codes d’erreur peuvent être qualifiés dans la qualification des logs de diffusion.

Par défaut, il capture 3 caractères après &quot;err:&quot;.

### Format de l&#39;ID dans l&#39;acquittement MT

Cela indique le format de l’ID renvoyé dans le champ message_id du PDU SUBMIT_SM_RESP.

* **Ne pas modifier** : l&#39;ID est stocké tel quel dans la base de données, sous la forme de texte encodé en ASCII. Aucun prétraitement ni filtrage n&#39;est effectué.
* **Nombre décimal** : l&#39;ID doit être un nombre décimal au format ASCII. Les espaces de début et de fin et les zéros de début sont supprimés lorsque ce paramètre est utilisé.
* **Nombre hexadécimal** : l&#39;ID doit être un nombre hexadécimal au format ASCII, sans 0x ni h à la fin.L&#39;ID est ensuite converti en nombre décimal avant d&#39;être stocké dans la base de données.
* **Chaîne hexadécimale** : l&#39;ID doit être un texte encodé en ASCII qui est lui-même une chaîne d&#39;octets encodés en hexadécimal. Par exemple, dans le PDU, vous trouverez 0x34 0x31 0x34 0x32 0x34 0x33, qui se traduit par ASCII &quot;414243&quot; ; cette chaîne est décodée sous la forme d&#39;une chaîne hexadécimale d&#39;octets, ce qui vous donne &quot;ABC&quot; : vous stockerez l&#39;ID &quot;ABC&quot; dans la base de données.

### Format de l&#39;ID dans le SR

Cela indique le format de l&#39;identifiant capturé par l&#39;expression régulière Extraction de l&#39;identifiant dans le SR. Les valeurs ont la même signification et le même comportement que le format en MT ci-dessus.

### L&#39;identifiant du SR ou le code d&#39;erreur dans un champ optionnel

Si cette case est cochée, le contenu des champs facultatifs est ajouté au texte traité par les expressions régulières ci-dessus. Le texte aura le format &quot; 0xTAG:VALUE&quot;, 0xTAG étant la valeur hexadécimale de 4 chiffres de la balise en majuscules (ex. 0x002E).

Par exemple, vous pouvez capturer l’ID dans le champ recipient_message_id . Pour cela, activez cette case à cocher et le texte suivant est ajouté au statut :

0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739

Dans cet exemple, 0x001E est la balise du champ facultatif et UUID est la valeur du champ.

Pour capturer cette valeur, vous pouvez désormais définir l&#39;expression régulière suivante dans l&#39;expression régulière d&#39;extraction de l&#39;ID dans le champ de SR :

\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]\} 2\})\b

>[!IMPORTANT]
>
>Vous ne pouvez capturer que les champs facultatifs ayant des valeurs de texte 8 bits (ASCII/UTF-8). En particulier, les champs binaires ne peuvent pas être capturés de manière fiable avec le système d&#39;expressions régulières actuel.

### Stocker l&#39;identifiant du SR ou le code d&#39;erreur dans un champ de texte

Si cette case est cochée, le champ Texte: est conservé pendant le traitement du texte de statut du SR. Cela s&#39;avère utile si le fournisseur place des données importantes dans ce champ, telles que l&#39;ID ou le statut. En règle générale, ce champ peut être ignoré en toute sécurité puisqu&#39;il peut contenir du texte avec un codage non ASCII et perturber le traitement d&#39;expression régulière.

L&#39;activation de cette option peut introduire un très petit défaut de sécurité si l&#39;expression régulière d&#39;extraction de l&#39;identifiant dans le champ SR n&#39;est pas suffisamment précise : le contenu du champ Texte peut être analysé en tant qu&#39;identifiant et un attaquant peut l&#39;utiliser pour injecter des identifiants falsifiés, ce qui peut entraîner un déni de service partiel.

### Balise d’ID de service

Permet d&#39;ajouter un fichier TLV personnalisé. Ce champ définit la balise, transmise sous la forme d’une valeur hexadécimale au format **0x1234**.

La valeur du TLV personnalisé doit être définie dans la diffusion, dans le champ &quot;Service or program ID&quot;, dans les paramètres avancés de la diffusion. La valeur est envoyée sous forme de texte codé UTF-8.

Ce paramètre permet uniquement d&#39;ajouter une option TLV par message.

>[!NOTE]
>
>Cette option est remplacée par le paramètre beaucoup plus puissant **Paramètres SMPP facultatifs (TLV)** dans les paramètres de diffusion. Ces fonctionnalités s’excluent mutuellement et ne peuvent pas être utilisées en même temps.

### Activer TLS via SMPP

Si cette option est activée, toutes les connexions au SMSC sont chiffrées à l’aide de TLS.

### Vérification du certificat

* **Vérification complète du certificat** : vérifiez le certificat TLS et le nom d’hôte distant lors de la connexion. Cette valeur donne le niveau de sécurité le plus élevé.
* **Ignorer la vérification du nom d’hôte** : vérifiez le certificat TLS distant, mais ne vérifiez pas si le nom d’hôte distant correspond. Diminue légèrement la sécurité.
* **Ignorer la vérification du certificat** : ne pas du tout vérifier le certificat TLS. La connexion est toujours cryptée, mais elle est vulnérable aux attaques de l&#39;homme du milieu. La sécurité diminue beaucoup.

## Trafic entrant {#incoming-traffic}

![](assets/incoming_traffic.png){zoomable="yes"}

### Paramètres SMPP facultatifs (TLV) dans MO

Campaign permet de recevoir 3 champs supplémentaires dans MO (table nms:inSms) : SMS lié, alias et compte volumineux. Avec le connecteur SMPP, ces champs peuvent être remplis avec des données provenant de n&#39;importe quel paramètre SMPP facultatif (TLV), avec n&#39;importe quel format commun.

Pour chaque champ, vous pouvez définir la balise associée ainsi que son format. Demandez au fournisseur de services SMPP de disposer de ces informations.

* Balise : la valeur de la balise, soit au format décimal (par ex. 12345), soit au format hexadécimal avec le préfixe 0x (par ex. 0x12ab). Les balises peuvent aller entre 0 et 65535.
* Format : format utilisé pour la valeur. Les valeurs binaires sont toutes des valeurs binaires signées big-endian. Pour les champs de texte, choisissez le codage utilisé par le fournisseur SMPP.

### Réponse automatique aux MO  

Cette fonctionnalité permet de répondre rapidement du texte au MO et de gérer les listes noires par numéro court.

Les colonnes *Mot-clé* et *Numéro court* définissent les conditions pour déclencher la réponse automatique : si les deux champs correspondent, le MO est envoyé et l’action supplémentaire est déclenchée. Pour spécifier un caractère générique, laissez le champ vide. Le mot-clé correspond au premier mot alphanumérique du texte MO, en ignorant la ponctuation et les espaces de début. Cela signifie que le champ Mot-clé ne peut pas contenir d&#39;espaces et doit être un seul mot.

En outre, le paramètre *Mot-clé* est un préfixe. Par exemple, si vous spécifiez &quot;AD&quot;, il correspondra à &quot;AD&quot;, &quot;ADAPT&quot; et &quot;ADOBE&quot;. Si vous avez plusieurs mots-clés avec un préfixe commun, prêtez attention à l’ordre, les mots-clés sont traités de haut en bas.

La colonne *Répondre* correspond au texte à répondre. Aucune personnalisation n&#39;est disponible dans ce champ. Le texte de la réponse est toujours le même. Si vous laissez ce champ vide, aucun message ne sera répondu, mais l&#39;action supplémentaire sera quand même déclenchée.

La colonne d’action *Additional* fournit une action supplémentaire à effectuer lorsque le mot-clé et le code court correspondent tous les codes courts vides). Actuellement, vous pouvez envoyer en quarantaine ou le retirer de la quarantaine. Si vous indiquez une action supplémentaire, mais que le champ de réponse reste vide, l’action est exécutée mais aucune réponse n’est envoyée. La quarantaine est appliquée uniquement pour le numéro court spécifié ou pour tous les numéros courts si le champ est vide.

Toutes les entrées du tableau sont traitées dans l&#39;ordre spécifié, jusqu&#39;à ce qu&#39;une règle corresponde. Si plusieurs règles correspondent à un MO, seule la règle la plus élevée est appliquée.

>[!NOTE]
>
>Le paramètre **envoyer le numéro de téléphone complet** a un impact sur le comportement du mécanisme de quarantaine de réponse automatique : si l&#39;envoi du numéro de téléphone complet n&#39;est pas coché, le numéro de téléphone mis en quarantaine sera précédé d&#39;un signe plus (&quot;+&quot;) pour le rendre compatible avec le format du numéro de téléphone international.

>[!NOTE]
>
>Dans une architecture en mid-sourcing, l&#39;application d&#39;une réponse automatique pour le connecteur SMPP étendu nécessite l&#39;ajout d&#39;un accès en écriture pour l&#39;opérateur mid sur le dossier du compte externe.

>[!IMPORTANT]
>
>Soyez prudent avec les encodages dans les réponses automatiques, en particulier lorsque vous copiez-collez. Les logiciels de traitement de texte ont tendance à ajouter une mise en forme supplémentaire, comme l’ajout d’espaces insécables ou la modification de guillemets en apostrophes.