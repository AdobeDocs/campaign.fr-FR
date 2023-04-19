---
title: Collecte et traitement des événements
description: Découvrez comment les messages transactionnels de Campaign collectent et traitent les événements
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: c1deb0a1-aeba-4813-b674-a6a164b98b02
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 44%

---

# Traitement des événements {#event-processing}

Dans le cadre d’une messagerie transactionnelle, un événement est généré par un système d’information externe et envoyé à Adobe Campaign via le **[!UICONTROL PushEvent]** et **[!UICONTROL PushEvents]** méthodes. Ces méthodes sont décrites dans la section [cette section](event-description.md).

Cet événement contient des données liées à l’événement, telles que :

* its [type](transactional.md#create-event-types): confirmation de commande, création de compte sur un site web, etc.,
* l&#39;adresse email ou le numéro de téléphone,
* toute autre information pour enrichir et personnaliser le message transactionnel avant la diffusion : coordonnées du client, langue du message, format de l&#39;email, etc.

Exemple de données d&#39;un événement :

![](assets/mc-event-request.png)

Pour traiter les événements de message transactionnel, les étapes suivantes sont appliquées sur la ou les instances d&#39;exécution :

1. [Collecte des événements](#event-collection)
1. [Acheminement de l&#39;événement vers un modèle de message](#routing-towards-a-template)
1. Enrichissement de l&#39;événement avec des données de personnalisation
1. [Exécution de la diffusion](delivery-execution.md)
1. [Recyclage des événements](#event-recycling) dont la diffusion associée a échoué (via un workflow Adobe Campaign)

Une fois toutes les étapes effectuées, chaque destinataire ciblé reçoit un message personnalisé.

## Collecte d’événements {#event-collection}

Les événements générés par le système d&#39;information peuvent être collectés selon deux modes :

* Les appels aux méthodes SOAP vous permettent d&#39;effectuer une transmission de type push des événements dans Adobe Campaign : la méthode PushEvent permet d&#39;envoyer un événement à la fois, la méthode PushEvents, plusieurs événements à la fois. [En savoir plus](event-description.md).

* La création d&#39;un workflow permet de récupérer les événements par import de fichier ou via une passerelle SQL, avec la fonctionnalité [Federated Data Access](../connect/fda.md) module .

Une fois collectés, les événements sont répartis par les workflows techniques entre les files d’attente temps réel et par lots de la ou des instances d’exécution, en attendant d’être associés à une [modèle de message](transactional-template.md).

![](assets/mc-event-queues.png)

>[!NOTE]
>
>Sur les instances d&#39;exécution, les dossiers **[!UICONTROL Événements en temps réel]** ou **[!UICONTROL Événements par lots]** ne doivent pas être définis comme des vues, car cela pourrait entraîner des problèmes de droit d&#39;accès. Pour plus d&#39;informations sur la définition d&#39;un dossier en tant que vue, consultez [cette section](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## Transfert d’un événement vers un modèle {#event-to-template}

Une fois le modèle de message publié sur la ou les instances d&#39;exécution, deux modèles sont automatiquement générés : l’un à lier à un événement en temps réel, l’autre à lier à un événement batch.

L&#39;étape de routage consiste à associer un événement au modèle de message approprié, en fonction des éléments suivants :

* Type d&#39;événement spécifié dans les propriétés de l&#39;événement lui-même :

   ![](assets/event-type-sample.png)

* Type d&#39;événement spécifié dans les propriétés du modèle de message :

   ![](assets/event-type-select.png)

Par défaut, le routage s&#39;appuie sur les informations suivantes :

* Le type d&#39;événement
* Le canal à utiliser (email par défaut)
* Le modèle de diffusion le plus récent, selon la date de publication

## Vérification du statut des événements {#event-statuses}

Tous les événements traités sont regroupés dans une seule vue, dans la **Historique des événements** ou l’Explorateur. Ils peuvent être classés par type d’événement ou par **status**.

Les statuts possibles sont les suivants :

* **En attente**

   * Un événement en attente peut être un événement qui vient d’être collecté et qui n’a pas encore été traité. Le **[!UICONTROL Nombre d&#39;erreurs]** affiche la valeur 0. Le modèle d&#39;email n&#39;a pas encore été lié.
   * Un événement en attente peut également être un événement traité, mais dont la confirmation est erronée. Le **[!UICONTROL Nombre d&#39;erreurs]** affiche une valeur différente de 0. Pour savoir quand cet événement sera traité à nouveau, consultez la section **[!UICONTROL Traitement demandé le]** colonne .

* **En attente de diffusion**
L&#39;événement a été traité et le modèle de diffusion est lié. L&#39;email est en attente de diffusion et le processus de diffusion classique est appliqué. Pour plus d&#39;informations, vous pouvez ouvrir la diffusion.
* **Envoyé**, **Ignoré** et **Erreur de diffusion**
Ces statuts de diffusion sont récupérés à partir du 
**updateEventsStatus** workflow. Pour plus d&#39;informations, vous pouvez ouvrir la diffusion correspondante.
* **Événement non couvert**
La phase de routage des messages transactionnels a échoué. Par exemple, Adobe Campaign n&#39;a pas trouvé l&#39;e-mail qui sert de modèle pour l&#39;événement.
* **Événement expiré**
Le nombre maximal de tentatives d’envoi a été atteint. L’événement est considéré comme nul.

## Recyclage des événements {#event-recycling}

Si l&#39;envoi d&#39;un message sur un canal spécifique échoue, Adobe Campaign peut renvoyer le message en utilisant un autre canal. Par exemple, si l&#39;envoi d&#39;un message sur le canal SMS échoue, le message est renvoyé en utilisant le canal email.

Pour cela, vous devez paramétrer un workflow qui recrée tous les événements dont le statut est **Erreur de diffusion**, et leur assigner un canal différent de celui utilisé précédemment.

>[!CAUTION]
>
>Cette étape ne peut être réalisée qu&#39;à l&#39;aide d&#39;un workflow et est donc réservée à des utilisateurs experts. Pour plus d&#39;informations, veuillez contacter votre chargé de compte Adobe.
