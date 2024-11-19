---
title: Valider une connexion SMPP
description: Découvrir comment valider une connexion SMPP
feature: SMS
role: User
level: Intermediate
badge: label="Disponibilité limitée" type="Informative"
exl-id: eda6934a-e48a-4932-8c88-588f661005d6
source-git-commit: 30babc4bec802f61d3bd28a7ebcf0c15e22b2284
workflow-type: tm+mt
source-wordcount: '4445'
ht-degree: 100%

---

# Valider une connexion SMPP {#validate-smpp-connection}

Voici quelques vérifications pour vous assurer que votre connexion SMPP est correcte.

## Informations à vérifier avant la mise en production {#check-go-live}

Avant de passer en production, assurez-vous que votre configuration SMPP est correcte avec la liste des vérifications ci-dessous.

>[!IMPORTANT]
>
>Cette liste n’est pas exhaustive. Plus vous effectuez de vérifications, mieux c’est.

>[!NOTE]
>
>Activez les traces SMPP en mode verbeux lors des vérifications. Cela vous aidera, ainsi que l’équipe de support, à comprendre les problèmes.

### Rechercher les conflits de compte externe {#sms-external-accounts-check}

Vérifiez que vous n’avez pas de vieux comptes externes SMS. Supprimez les comptes de test afin d’éliminer les conflits potentiels.

Vérifiez qu’aucune autre instance ne se connecte à ce compte externe. En particulier, assurez-vous que l’environnement d’évaluation ne se connecte pas au compte externe de production.

Si vous devez connecter plusieurs comptes de la même instance Adobe Campaign au même fournisseur, contactez ce dernier pour vérifier qu’il distingue effectivement les connexions entre ces comptes. La présence de plusieurs comptes avec le même nom d’utilisateur nécessite une configuration supplémentaire.

Vérifiez que le paramètre de processus dédié est activé pour tous les comptes externes SMS activés. Vous ne pouvez pas mélanger les deux types de comptes (avec et sans processus dédié) sur la même instance.

### Effectuer un test réel {#real-test}

Essayez d’envoyer quelques SMS sur différents mobiles.

**Envoyer un SMS avec toutes sortes de caractères**

Si vous devez envoyer des SMS avec des caractères non GSM ou non ASCII, essayez d’envoyer des messages avec les caractères les plus variés possible. Si vous définissez un tableau de mapping de caractères personnalisé, envoyez au moins un SMS pour toutes les valeurs data_coding possibles.

**Vérifier que les SR sont correctement traités**.

Le SMS doit être marqué comme reçu dans le log de diffusion. Le log de diffusion doit réussir et se présenter comme suit : « *SR yourProvider stat=DELIVRD err=000|#MESSAGE#* ».

Vérifiez que vous avez correctement défini le champ « *Nom d’implémentation SMSC* » : le log de diffusion ne doit jamais contenir « *SR Generic* » sur les environnements de production.

**Vérifier que les MO sont traités**.

Envoyez quelques SMS pour tous les mots-clés de réponse automatique et vérifiez si la réponse est assez rapide, pas plus de quelques secondes.

Vérifiez que les MO sont insérés dans la base de données *nms:inSms*. Si vous disposez de fichiers TLV personnalisés, assurez-vous qu’ils sont également correctement insérés et correctement formatés.

Archivez le log auquel Adobe Campaign répond avec un *DELIVER_SM_RESP (command_status=0)* réussi.

**Effectuer un test de charge**

Ceci est particulièrement important si vous envoyez beaucoup de messages ou si vous utilisez la messagerie en temps réel.

Effectuez un test qui chargera la connexion à 100 % pendant au moins 5 secondes. Vous devrez envoyer des messages réels si le fournisseur n’a pas de moyen de se connecter à un faux compte pour les tests. Pour ce faire, vous pouvez surveiller de près la première diffusion suffisamment volumineuse avec les messages SMPP en mode verbeux activés.

Le nombre minimum de messages à envoyer peut être calculé comme suit :

*Débit max de MT * Nombre total de connexions émetteur/récepteur * 5*

Une fois la diffusion terminée, vérifiez les éléments suivants :

* Vérifiez que tous les messages ont été envoyés (pas nécessairement reçus).
* Il doit y avoir un PDU absolument nul avec command_status non 0x00000000, sauf si cela est explicitement indiqué par le fournisseur comme une opération normale.
* Les connexions doivent rester absolument stables (pas de PDU BIND) pendant l’ensemble du processus de diffusion.
* Vérifiez que tous les messages ont un SR et qu’il a été correctement traité (voir [Vérifier que les SR sont correctement traités](#real-test)). Si un petit pourcentage contient des erreurs, vérifiez qu’il s’agit d’erreurs SR réelles, et non d’erreurs lors de l’envoi ou du traitement du côté Campaign.
* Si vous vous posez des questions sur les performances, vérifiez que la latence est raisonnable, en particulier entre un PDU et son RESP correspondant. Avoir plus de 500 ms de latence peut être un problème pour un débit élevé. Utilisez cette latence pour vérifier la formule de la fenêtre d’émission (voir le paramètre Fenêtre d’émission pour plus de détails).

### Vérifier les PDU {#pdu}

Vérifiez que les PDU sont correctement formatés.

>[!IMPORTANT]
>
>Cette étape est fortement recommandée lors d’une connexion avec un fournisseur qui n’a jamais été connecté à Adobe Campaign auparavant.

**BIND**

Vérifiez que les PDU BIND_* sont correctement envoyés. La chose la plus importante à vérifier est que le fournisseur renvoie toujours des PDU BIND_*_RESP (command_status = 0) réussis.

Vérifiez qu’il n’y ait pas trop de PDU BIND_*. S’il y en a trop, cela peut indiquer que la connexion est instable. Pour plus d’informations, consultez la section de résolution des problèmes liés aux connexions instables.

**ENQUIRE_LINK**

Vérifiez que les PDU ENQUIRE_LINK sont échangés régulièrement lorsque la connexion est inactive.

**SUBMIT_SM / DELIVER_SM**

Envoyez un message, puis recherchez dans les journaux les PDU SUBMIT_SM, SUBMIT_SM_RESP, Deliver_SM et DELIVER_SM_RESP correspondants.

Avec le *PDU SUBMIT_SM* :

* Vérifiez que data_coding est correct, 0 par défaut.
* Vérifiez que short_message est correctement encodé : essayez de le décoder à l’aide d’un convertisseur hexadécimal qui prend en charge plusieurs encodages (certains sont disponibles en ligne).
* Si vous utilisez message_payload pour les messages longs, vérifiez que le contenu est présent dans le champ facultatif et non dans le champ short_message.

Avec le *PDU SUBMIT_SM_RESP* :

* Vérifiez qu’il a réussi, command_status = 0.
* Vérifiez que son corps contient un ID correctement formaté suivi d’un octet « 0 ».

Avec le *PDU DELIVER_SM* :

* Décodez le champ hexadécimal short_message (il existe des outils en ligne pour cela).
* Vérifiez avec un outil de vérification d’expression régulière que l’expression régulière définie dans l’expression régulière Extraction de l’identifiant dans le SR renvoie exactement un groupe de capture et qu’il capture l’identifiant entier dans le message.
* Vérifiez que l’ID extrait correspond à celui dans SUBMIT_SM_RESP.
* Vérifiez que l’expression régulière définie dans l’expression régulière Extraction du statut dans le SR renvoie le contenu du champ « stat ».
* Vérifiez que l’expression régulière définie dans l’expression régulière Extraction de l’erreur dans le SR renvoie le contenu du champ « err ».

Avec le *PDU DELIVER_SM_RESP* :

* Vérifiez qu’il a été envoyé rapidement après avoir reçu le PDU DELIVER_SM (généralement moins d’une seconde).
* Vérifiez qu’il a réussi, command_status = 0.

### Test en direct avec le fournisseur {#sms-live-test}

Une bonne pratique avant la mise en production consiste à effectuer un test en direct avec le fournisseur, les deux côtés examinant les journaux pendant l’exécution.

>[!IMPORTANT]
>
>Cette étape est nécessaire lors de la connexion avec un fournisseur qui n’était pas connecté à Adobe Campaign auparavant.

### Désactiver les traces SMPP en mode verbeux {#sms-disable-smpp}

Une fois toutes les vérifications terminées, la dernière chose à faire est de désactiver les traces SMPP en mode verbeux pour ne pas générer trop de journaux.

## Résolution des problèmes de SMS {#sms-troubleshooting}

### Procédure générale de dépannage {#sms-general-troubleshooting}

Le connecteur SMS comprend 3 entités : le fournisseur SMPP, Adobe et vous.
Le principal expert SMS est le fournisseur SMPP. Il doit donc être impliqué dans tous les problèmes liés au trafic SMS (problèmes de connexion, messages perdus, problèmes de codage, règles spécifiques au pays, etc.).

#### Activer le processus dédié {#sms-dedicated-process}

>[!IMPORTANT]
>
>Assurez-vous que l’option **[!UICONTROL Envoyer les messages par le biais d’un processus dédié]** est activée dans tous les comptes SMS actifs.

Si vous rencontrez des problèmes avec l’ancien connecteur (basé sur MTA, processus dédié désactivé), envisagez de migrer vers le connecteur de processus dédié. Il fonctionne beaucoup mieux, est plus stable et fournit de bien meilleurs retours dans ses logs.

#### Conflit entre différents comptes externes {#sms-conflict-external-accounts}

Si l’instance comporte plusieurs comptes externes SMS, vous devez vérifier que les problèmes ne sont pas causés par un conflit entre comptes externes.

Pour isoler le compte externe qui pose problème, procédez comme suit :

1. Désactivez tous les comptes externes.
1. Activez un compte externe.
1. Essayez de reproduire le problème.
1. Si le problème n’apparaît pas avec ce compte unique, désactivez-le et redémarrez à l’étape 2 sur le compte suivant. Une fois que vous avez vérifié chaque compte individuellement, il existe 2 scénarios possibles :

**Le problème est apparu sur un ou plusieurs comptes.**

Dans ce cas, vous pouvez appliquer d&#39;autres procédures de résolution des problèmes individuellement sur chaque compte. Il est préférable de désactiver les autres comptes lors du diagnostic d’un compte afin de réduire le trafic réseau et le nombre de logs.

**Le problème ne s&#39;affichait pas lorsqu&#39;un seul compte était actif à un moment donné.**

Vous avez un conflit entre les comptes. Comme nous l’avons déjà mentionné, Adobe Campaign traite les comptes individuellement, mais le fournisseur peut les traiter comme un compte unique.

*Vous utilisez des combinaisons nom d’utilisateur ou d’utilisatrice/mot de passe différentes entre tous vos comptes.*
Vous devrez contacter le fournisseur pour diagnostiquer les conflits potentiels de leur côté.

*Certains comptes externes partagent la même combinaison nom d’utilisateur ou d’utilisatrice/mot de passe.*
Le fournisseur n’a aucun moyen de savoir de quel compte externe provient le PDU BIND. Il traite donc toutes les connexions à partir de plusieurs comptes comme une seule, de sorte qu’il achemine probablement les MO et SR de manière aléatoire sur les 2 comptes, ce qui provoque des problèmes apparemment aléatoires.

Si le fournisseur prend en charge plusieurs codes courts pour la même combinaison nom d’utilisateur ou d’utilisatrice/mot de passe, vous devrez lui demander où placer ce numéro court dans le PDU BIND. Notez que cette information doit être placée dans le PDU BIND et non dans SUBMIT_SM, puisque le PDU BIND est le seul endroit qui permettra d’utiliser correctement les MO de routage.

Consultez la section [Informations dans chaque type de PDU](#pdu) ci-dessus pour savoir quel champ est disponible dans le PDU BIND. En général, vous ajoutez le numéro court dans *address_range*, mais cela nécessite une assistance spéciale de la part du fournisseur. Contactez-le pour savoir comment il s’attend à acheminer de manière indépendante plusieurs numéros courts.

Adobe Campaign prend en charge la gestion de plusieurs numéros courts sur le même compte externe. Par conséquent, l’utilisation d’un seul compte pour l’ensemble du trafic fonctionne bien.

#### Un compte externe a cessé de fonctionner. {#sms-external-account-not-working}

En général, les connexions SMPP ont tendance à être très stables au fil du temps, et une fois configurées correctement, elles doivent continuer à fonctionner.

* Vérifiez si le connecteur a été changé récemment et par qui (vérifiez les comptes externes en tant que groupe).
* Vérifiez si le système a été mis à niveau et quand.
* Déterminez si des packages affectant les SMS ont pu être mis à jour récemment.

Si aucune de ces vérifications n’entraîne une cause racine, contactez le fournisseur. Parfois, lorsque les fournisseurs mettent à jour leurs plateformes, leur connecteur se comporte légèrement différemment. Cela peut rompre les paramètres affinés et introduire des régressions.

Il est recommandé de rester en contact avec le fournisseur, qui communique souvent les changements majeurs à l’avance.

#### Problème lié au midsourcing (hébergé)  {#sms-issue-hosted}

* Si le problème se produit dans un environnement de midsourcing, vérifiez que les logs de diffusion et les broadlogs sont correctement créés et mis à jour sur le serveur de midsourcing. Si ce n’est pas le cas, il ne s’agit pas d’un problème de SMS.
* Assurez-vous que le nom de l’opérateur de midsourcing est strictement en minuscules, sinon la diffusion restera en état d’attente.
* Si tout fonctionne sur le server de midsourcing et que les SMS sont correctement envoyés, mais que l’instance marketing n’est pas correctement mise à jour, il est possible qu’un problème de synchronisation de midsourcing se produise.

#### Problème lors de la connexion au fournisseur {#sms-issue-connection}

* Si le PDU BIND renvoie un code *command_status* non nul (ce qui signifie qu’il y a une erreur) ou s’il n’y a pas de PDU BIND_RESP, demandez au fournisseur pourquoi cela se produit.
* Vérifiez que le réseau est correctement configuré pour que la connexion TCP puisse être établie avec le fournisseur.
* Demandez au fournisseur de vérifier qu’il a correctement autorisé les adresses IP de l’instance Adobe Campaign (la plupart des fournisseurs l’exigent).
* Vérifiez les paramètres de compte externe. Demandez au fournisseur en cas de doute sur la valeur de certains champs.
* Si la connexion est réussie mais instable, consultez la section [Problèmes de connexion instable](#unstable-connections) ci-dessous.
* Si les problèmes de connexion sont difficiles à diagnostiquer, une capture réseau vous apporte beaucoup d’informations. Assurez-vous que la capture réseau s’exécute simultanément pendant que le problème s’affiche pour pouvoir être analysé efficacement. Vous devez également noter l’heure exacte à laquelle le problème apparaît, afin qu’il soit plus facile de trouver le problème dans les captures réseau.

#### Problèmes de connexion instable {#unstable-connections}

**Comment diagnostiquer les connexions instables :**

Une connexion est considérée comme instable si l’une des situations suivantes se produit :

* La connexion dure moins d’une heure.
* Le redémarrage du processus SMS réparera temporairement les problèmes. Cela signifie probablement qu’une connexion instable déclenche le ralentissement, redémarrer le processus SMS efface le ralentissement, puis se reproduit jusqu’à la cause racine trouvée.
* Le fournisseur envoie des PDU UNBIND. Le fournisseur ne doit jamais envoyer de PDU UNBIND en fonctionnement normal.
* *enquire_link* expire, soit du côté d’Adobe Campaign, soit du côté du fournisseur. Dans ce cas, vous pouvez voir ENQUIRE_LINK_RESP avec un code d’erreur non nul.
* Il y a beaucoup de PDU BIND. Il ne doit pas y en avoir plus de quelques-uns pendant une journée (cela dépend du nombre de connexions). L’apparition de plusieurs PDU BIND par heure et par connexion doit attirer l’attention.

**Comment résoudre les problèmes de stabilité de connexion :**

* Les connexions instables sont rarement la cause première, il s’agit souvent du résultat d’un autre problème qui déclenche une déconnexion. Il est prioritaire d&#39;identifier la cause première.
* Activez les traces SMPP de verbose. Vous aurez besoin d’elles pour voir ce qui se passe au redémarrage de la connexion.
* Si le fournisseur envoie des PDU UNBIND, il fait probablement quelque chose d’une manière qui n’est pas correcte. Demandez-lui pourquoi il envoie UNBIND et cela mènera probablement à la cause racine.
* La capture réseau est parfois la seule façon de voir comment la connexion est fermée.
* Si le fournisseur ferme les connexions (en envoyant un paquet TCP FIN ou TCP RST), demandez-lui pourquoi il le fait. Cela devrait vous indiquer la cause racine du problème.
* Si le fournisseur ferme la connexion après avoir envoyé une erreur de nettoyage telle que DELIVER_SM_RESP avec un code d’erreur, il doit réparer son connecteur, sinon il empêchera la transmission d’autres types de messages et déclenchera le ralentissement du MTA. Ceci est particulièrement important en mode émetteur-récepteur où la fermeture de la connexion a un impact à la fois sur les MT et SR.
* En cas de dépassements de délai (délais BIND, délais SUBMIT_SM), Campaign peut envoyer des messages trop rapidement pour ce fournisseur. Essayez d’abaisser le paramètre de *débit maximal MT* et vérifiez si cela résout le problème.

#### Problème lors de l’envoi d’un MT (SMS régulier envoyé à un utilisateur final ou une utilisatrice finale)

* Vérifiez que la connexion est stable : une connexion SMPP doit rester active pendant au moins 1 heure en continu. Pour plus d’informations, consultez la section « Problème de connexions instables » ci-dessus.
* Si le redémarrage du processus SMS permet à nouveau d’envoyer des MT pendant une petite période de temps, vous avez probablement un ralentissement dû à une connexion instable. Pour plus d’informations, consultez la section « Problème de connexions instables » ci-dessus.
* Vérifiez que le broadlog est présent et que son statut est correct avec les dates correctes. Si ce n’est pas le cas, il ne s’agit pas d’un problème de SMS, mais d’un problème de diffusion ou de préparation de diffusion (qui ne fait pas partie du cadre de ce document).
* Vérifiez que le connecteur SMS est effectivement lié à l&#39;équipement du fournisseur. Demandez au fournisseur de faire part de ses commentaires pour assurer que tous les systèmes communiquent correctement. Pour plus d’informations sur le processus de liaison, consultez les PDU BIND_TRANSMITTER et BIND_TRANSCEIVER. Vous devrez peut-être activer les traces SMPP pour résoudre correctement les problèmes.
* Lorsque les traces SMPP sont activées, vérifiez que le PDU SUBMIT_SM contient les informations appropriées (voir la documentation ci-dessus).
* Vérifiez que le fournisseur répond par un PDU SUBMIT_SM_RESP avec une valeur « OK » (code 0). Assurez-vous que le PDU arrive avec un délai raisonnable : tout ce qui dure plus d’une seconde doit faire l’objet d’une discussion avec le fournisseur (il arrive habituellement en moins de 100 ms).
* Si toutes ces étapes fonctionnent, c’est que le problème se trouve du côté fournisseur. Il devra effectuer une résolution des problèmes sur sa plateforme.
* Si cela fonctionne mais que le débit n&#39;est pas constant, essayez d&#39;ajuster la fenêtre d&#39;émission et d&#39;abaisser le débit MT. Vous devrez travailler avec le fournisseur pour l&#39;ajuster. Adobe Campaign peut envoyer des messages très rapidement de sorte que des problèmes de performances peuvent survenir sur l’équipement du fournisseur.

#### Les MT sont dupliquées (le même SMS est envoyé plusieurs fois de suite)

Les doublons sont souvent causés par des reprises. Il est normal d’avoir des doublons lors des reprises de messages. Il est préférable d’essayer de supprimer la cause racine des reprises.

* Si vous voyez des doublons envoyés exactement à 60 secondes d’intervalle (ou à des périodes « trop régulières »), il s’agit probablement d’un problème du côté fournisseur. L’envoi de SUBMIT_SM_RESP n’est pas assez rapide.
* Si vous voyez beaucoup de BIND/UNBIND, vous avez une connexion instable : consultez la section [Problèmes de connexion instable](#unstable-connections) pour connaître les solutions avant de tenter de résoudre les problèmes de doublons de messages.
* Vérifiez que tous les PDU SUBMIT_SM reçoivent des SUBMIT_SM_RESP correspondants peu de temps après. S’ils n’en reçoivent pas ou que les SUBMIT_SM_RESP sont trop lents, le problème est du côté fournisseur.

Réduire le nombre de doublons en cas de reprise :

* Baissez la *fenêtre d’émission*. La fenêtre d’émission doit être suffisamment grande pour couvrir la latence SUBMIT_SM_RESP, mais pas trop grande. Sa valeur représente le nombre maximum de messages pouvant être dupliqués en cas d’erreur lorsque la fenêtre est pleine.

#### Problème lors du traitement des SR (accusés de réception de diffusion)

* Vous aurez besoin de traces SMPP activées pour tous les types de résolution des problèmes SR.
* Vérifiez que le PDU DELIVER_SM vient du fournisseur et qu’il est correctement formé.
* Vérifiez qu’Adobe Campaign répond avec un PDU DELIVER_SM_RESP réussi dans les délais impartis. Cela garantit que le SR a été inséré dans le tableau providerMsgStatus pour le traitement différé par le processus SMS.

Si le PDU DELIVER_SM n’est pas reconnu, vous devez vérifier quelques éléments :

* Vérifiez l’expression regex associée à l’extraction des identifiants et au traitement des erreurs dans le compte externe. Vous devrez peut-être les valider par rapport au contenu du PDU DELIVER_SM.
* Vérifiez que les erreurs sont correctement configurées dans le tableau broadLogMsg (la documentation de Campaign l’explique en détail).

Si le PDU DELIVER_SM a été reconnu par le connecteur SMPP étendu ACC mais que le broadLog n’est pas mis à jour correctement, vérifiez le processus de réconciliation des identifiants décrit dans la section Correspondance des entrées MT, SR et Broadlog ci-dessus.

Si vous avez tout corrigé, mais que des SR non valides figurent toujours dans les tampons du fournisseur, vous pouvez les ignorer à l&#39;aide de l&#39;option Nombre d&#39;acquittements d&#39;identifiant invalides. Cette option doit être utilisée avec soin et réinitialisée à 0 aussi vite que possible après le nettoyage des tampons.

Si le traitement du SR est lent, essayez de qualifier les messages de statut les plus courants dans la table BroadLogMsg.

Si seulement certains SR sont reçus, mais pas tous, vérifiez qu’aucun autre système ne se connecte au compte de votre fournisseur, par exemple un système de test. Le SR peut être routé sur n’importe quelle connexion, certains d’entre eux peuvent donc être acheminés vers cet autre système. Le fournisseur peut vous aider à trouver où se trouve cet autre système se connectant au compte.

#### Problème lors du traitement de MO (et quarantaine/réponse automatique)

* Activez les traces SMPP pendant les tests. Si vous n’activez pas le protocole TLS, vous devez effectuer une capture réseau lors de la résolution des problèmes de MO pour vérifier que les PDU contiennent les informations correctes et sont correctement formatés.
* Lors de la capture du trafic réseau ou de l’analyse des traces SMPP, veillez à capturer l’ensemble de la conversation avec le MO et sa réponse MT si une réponse est configurée.
* Si le MO (PDU DELIVER_SM) n’apparaît pas dans les traces, vous pouvez avoir la certitude que le problème est du côté fournisseur. Il devra effectuer une résolution des problèmes sur sa plateforme.
* Si le PDU DELIVER_SM apparaît, vérifiez que Campaign a confirmé sa réception avec un PDU DELIVER_SM_RESP réussi (code 0). Ce RESP garantit que toute la logique de traitement a été appliquée par Campaign (réponse automatique et quarantaine). Si ce n’est pas le cas, recherchez un message d’erreur dans les logs de processus SMS.
* Si les réponses automatiques sont activées, vérifiez que SUBMIT_SM a été envoyé au fournisseur. Si ce n’est pas le cas, il est garanti qu’un message d’erreur se trouvera dans les logs de processus SMS.
* Si le PDU MT SUBMIT_SM contenant la réponse se trouve dans les traces mais que le SMS ne parvient pas au téléphone portable, vous devez contacter le fournisseur pour obtenir de l’aide sur la résolution des problèmes, car le problème se trouve probablement de son côté.

#### Problème lors de la préparation de la diffusion sans exclure les destinataires mis en quarantaine (mis en quarantaine par la fonction de réponse automatique)

* Vérifiez que le format du numéro de téléphone est exactement le même dans la table de quarantaine et dans le log de diffusion. Si ce n’est pas le cas, consultez la section « Envoyer le numéro de téléphone complet » si vous rencontrez des problèmes avec le préfixe + du format de numéro de téléphone international.
* Des exclusions peuvent se produire si le numéro court de la personne destinataire est identique à celui défini dans le compte externe ou s’il est vide (vide = tout numéro court). Si un seul numéro court est utilisé pour l’ensemble de l’instance Campaign, il est plus facile de laisser tous les champs « numéro court » vides.

#### Problèmes d’encodage  {#sms-encoding-issues}

Les problèmes d’encodage sont fréquents dans les SMS. Voici quelques étapes de base.

**Étape 1 : Contacter le fournisseur**

Le fournisseur est l’entité experte qui sait comment fonctionne le SMS. Contactez-le et voyez avec lui ce qui ne va pas. Il devrait pouvoir vous dire si le problème est de son côté ou de celui de Campaign. Si le problème concerne Campaign, il devrait être en mesure de préciser exactement le champ incorrect, ce qui constitue une aide précieuse.

**Étape 2 : Connaître le contenu de votre message**

Vous devrez savoir ce qu’il y a dans votre message. Cette phrase peut sembler simpliste, mais ce n’est pas le cas. Unicode permet de nombreuses variantes pour les caractères identiques et Campaign ne peut pas toutes les gérer.

La source de problèmes la plus courante est le copier-coller d’un traitement de texte, qui transforme les caractères habituels en versions typographiques correctes : espaces changés en espaces insécables, guillemets doubles changés en guillemets ouvrants et fermants, signes moins changés en différents types de tirets, etc.

Ne copiez pas et ne collez pas votre message lors du test, saisissez-le toujours directement dans l’interface.

**Ne vous laissez pas intimider par l’hexadécimal**. L’hexadécimal semble étrange et peu naturel, mais il a une qualité très distincte : vous pouvez distinguer les caractères similaires. Un L minuscule, un I majuscule, un O, un 0, les différents types de guillemets, les encodages non latins ou même les différents types d’espaces peuvent tous avoir le même aspect ou ne pas s’afficher du tout. L’hexadécimal montre tout et aide à comparer les choses.

Pour convertir les codes unicode en hexadécimal, vous pouvez utiliser des outils en ligne.

**Lors de l’ouverture de tickets** concernant les problèmes d’encodage, que ce soit avec le fournisseur ou le support Campaign, **incluez une version hexadécimale** de ce que vous saisissez et de ce que vous voyez.

**Étape 3 : Savoir ce que vous devez envoyer**

Déterminez l&#39;encodage que vous prévoyez d&#39;utiliser et recherchez en ligne son tableau de caractères. Vérifiez que les caractères que vous avez l&#39;intention d&#39;envoyer sont réellement disponibles dans la page de code cible. Vérifiez que le champ data_coding est correct et correspond à ce que vous et le fournisseur attendez.

**Étape 4 : Connaître ce que vous avez effectivement envoyé**

Vous aurez besoin du résultat du débogage du connecteur pour voir exactement les octets à envoyer au fournisseur. Les problèmes d’encodage apparaissent dans les PDU SUBMIT_SM, veillez donc à les capturer. Envoyez des messages très distincts qui sont faciles à trouver dans le log.

Envoyez différents types de caractères spéciaux lors du test. Par exemple, l’encodage GSM7 comporte des caractères étendus qui sont particulièrement distincts dans leur forme hexadécimale. Ils sont faciles à repérer puisqu’ils n’apparaissent dans aucun autre encodage.

#### Problèmes de performance {#sms-performance-issues}

>[!NOTE]
>
>La performance est un sujet très large. Cette section présente quelques vérifications de base à effectuer avant de tenter de mettre à l’échelle ou de réaliser d’autres projets de grande envergure.

**Problèmes de performances lors de l’envoi de MT**

* Vérifiez que tous les paramètres de la section Débit et délais du compte externe sont corrects et qu’ils correspondent aux paramètres autorisés par le fournisseur.
* Vérifiez qu’il n’y a aucune reprise.
* Vérifiez que l’infrastructure du fournisseur n’est pas saturée. Recherchez les erreurs RMSGQFUL ou RTHROTLED dans les PDU RESP.
* Vérifiez les paramètres serverConf. Commencez par les valeurs par défaut et augmentez les paramètres lentement et un par un.
* Vérifiez que le processus SMS ne redémarre pas toujours lorsqu’il est en cours de chargement. Si tel est le cas, vous devrez peut-être augmenter *maxSMSMemoryMb*, *maxProcessMemoryAlertMb* et *maxProcessMemoryWarningMb* dans le fichier serverConf.

**Problèmes de performances lors de la réception de SR**

Si le fournisseur se plaint d’une surcharge de la mémoire tampon de son côté, cela peut être dû au fait que Campaign ne reçoit pas de SR assez rapidement.

* Vérifiez que la base de données de l’instance n’est pas surchargée. Le traitement de SR dépend fortement des performances de la base de données.
* Demandez au fournisseur d’augmenter la fenêtre d’émission pour DELIVER_SM de son côté. Idéalement, elle doit être aussi grande que le paramètre *batchUpdateSize* dans serverConf.

### Éléments à inclure lors de la communication sur un problème SMS

Chaque fois que vous cherchez de l’aide sur une question de SMS, que ce soit en ouvrant un ticket d’assistance à Adobe Campaign, au fournisseur de SMS, ou tout autre type de communication sur la question, vous devrez inclure les informations suivantes pour vous assurer qu’elle sera correctement qualifiée. Des questions correctement qualifiées sont essentielles pour résoudre les problèmes plus rapidement, aussi prendre un peu plus de temps pour essayer de comprendre la situation et donner des informations significatives sera un bond en avant en termes d’efficacité.

* Activez les messages SMPP en mode verbeux lorsque le problème apparaît. La plupart des problèmes de SMS sont impossibles à résoudre sans cela.
* Si le problème est lié au trafic SMS, contactez d’abord le fournisseur. Il est le mieux informé et sa plateforme est généralement adaptée pour un diagnostic efficace des problèmes de trafic SMS en temps réel.
* Incluez une description brève mais factuelle du problème.
* Incluez une description du résultat attendu.
* Incluez les commentaires du fournisseur.
* Incluez les logs et/ou les captures réseau appropriés. Lorsque vous effectuez des captures, veillez à reproduire le problème pendant ces captures.
* Si vous incluez des journaux, des traces ou des captures, indiquez l’emplacement exact dans le fichier lorsque le problème apparaît, ainsi que l’emplacement exact d’un exemple probant, le cas échéant. Les captures ou les traces peuvent être volumineuses et fastidieuses à regarder, donc tout ce qui aide à localiser les informations nécessaires est utile.
* Si vous référencez des messages, des PDU ou des logs, indiquez clairement leur horodatage afin qu’ils soient faciles à trouver par d’autres personnes.
* Essayez de reproduire le problème sur un environnement de test. Si vous n&#39;êtes pas sûr d&#39;un paramètre, essayez-le sur l&#39;environnement de test et vérifiez le résultat avec les traces SMPP. Il est généralement préférable de signaler les problèmes reproduits dans les environnements de test que de les signaler directement dans les environnements de production.
* Incluez les modifications ou les ajustements apportés sur la plateforme : même un petit changement peut avoir des impacts énormes. Incluez également toute modification que le fournisseur peut avoir apportée de son côté.

#### Quand une capture réseau est-elle utile ?

Une capture réseau n’est pas toujours nécessaire. Très souvent, les messages SMPP en mode verbeux sont suffisants. Voici quelques directives qui vous aideront à déterminer si une capture réseau est nécessaire :

* Problèmes de connexion, mais les messages en mode verbeux n’affichent aucun PDU BIND_RESP.
* Déconnexions inexpliquées sans message d’erreur (comportement du connecteur lorsqu’il détecte une erreur de protocole de bas niveau).
* Le fournisseur se plaint du processus unbind/de déconnexion.
* Problèmes d’encodage dans les champs facultatifs TLV.
* Il est possible qu&#39;il y ait un trafic mixte entre les différentes connexions.

Dans toutes les autres situations, essayez d&#39;abord d&#39;analyser les messages SMPP en mode verbeux et de demander une capture réseau uniquement s&#39;il est clair que des informations manquent dans les logs de mode verbeux.

#### Quand une capture réseau est-elle inutile ?

Dans certains cas, la capture du trafic réseau est inutile ou simplement une perte de temps. Voici les situations les plus courantes :

* TLS activé : par définition, le trafic TLS est chiffré, et il ne peut pas être capturé.
* Problèmes de performances : les logs contiennent toutes les informations nécessaires pour tracer les problèmes de performance.
* Problèmes de minutage (minutage des reprises, période enquire_link, limitation de débit, etc.)
* Analyse et traitement SR : les logs explicites offrent beaucoup plus de contexte et une meilleure présentation.
* Traitement MO (réponses automatiques, quarantaine).
* Erreurs n’impliquant pas de trafic SMPP réel : préparation de la diffusion, problèmes d’API du Message Center, problèmes de workflow, etc.
