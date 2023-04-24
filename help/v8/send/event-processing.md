---
title: Collecter et traiter les événements
description: Découvrez comment les messages transactionnels de Campaign collectent et traitent les événements.
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: c1deb0a1-aeba-4813-b674-a6a164b98b02
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 100%

---

# Traitement des événements {#event-processing}

Dans le contexte des messages transactionnels, un événement est généré par un système d’informations externe et envoyé à Adobe Campaign via les méthodes **[!UICONTROL PushEvent]** et **[!UICONTROL PushEvents]**. Ces méthodes sont décrites dans [cette section](event-description.md).

Cet événement contient des données liées à l’événement, telles que :

* son [type](transactional.md#create-event-types) : confirmation de commande, création de compte sur un site web, etc. ;
* l’adresse e-mail ou le numéro de téléphone ;
* toute autre information visant à enrichir et personnaliser le message transactionnel avant sa diffusion : coordonnées du client ou de la cliente, langue du message, format de l’e-mail, etc.

Exemple de données d’événement :

![](assets/mc-event-request.png)

Pour traiter les événements de message transactionnel, les étapes suivantes sont appliquées sur la ou les instances d&#39;exécution :

1. [Collecte des événements](#event-collection)
1. [Acheminement de l&#39;événement vers un modèle de message](#routing-towards-a-template)
1. Enrichissement de l&#39;événement avec des données de personnalisation
1. [Exécution de la diffusion](delivery-execution.md)
1. [Recyclage des événements](#event-recycling) dont la diffusion associée a échoué (via un workflow Adobe Campaign)

Une fois toutes les étapes effectuées, chaque destinataire ciblé reçoit un message personnalisé.

## Collecter les événements {#event-collection}

Les événements générés par le système d&#39;information peuvent être collectés selon deux modes :

* Les appels aux méthodes SOAP vous permettent d&#39;effectuer une transmission de type push des événements dans Adobe Campaign : la méthode PushEvent permet d&#39;envoyer un événement à la fois, la méthode PushEvents, plusieurs événements à la fois. [En savoir plus](event-description.md).

* La création d’un workflow permet de récupérer les événements en important les fichiers ou via une passerelle SQL, avec le module [Federated Data Access](../connect/fda.md).

Une fois collectés, les événements sont scindés par workflows techniques entre les files d’attente en temps réel et par lot de la ou des instances d’exécution, tout en attendant d’être associés à un [modèle de message](transactional-template.md).

![](assets/mc-event-queues.png)

>[!NOTE]
>
>Sur les instances d&#39;exécution, les dossiers **[!UICONTROL Événements en temps réel]** ou **[!UICONTROL Événements par lots]** ne doivent pas être définis comme des vues, car cela pourrait entraîner des problèmes de droit d&#39;accès. Pour plus d&#39;informations sur la définition d&#39;un dossier en tant que vue, consultez [cette section](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## Transférer un événement vers un modèle {#event-to-template}

Une fois le modèle de message publié sur la ou les instances d’exécution, deux modèles sont automatiquement générés : l’un à associer à un événement en temps réel, l’autre à un événement batch.

L&#39;étape de routage consiste à associer un événement au modèle de message approprié, en fonction des éléments suivants :

* Type d&#39;événement spécifié dans les propriétés de l&#39;événement lui-même :

   ![](assets/event-type-sample.png)

* Type d&#39;événement spécifié dans les propriétés du modèle de message :

   ![](assets/event-type-select.png)

Par défaut, le routage s&#39;appuie sur les informations suivantes :

* Le type d&#39;événement
* Le canal à utiliser (email par défaut)
* Le modèle de diffusion le plus récent, selon la date de publication

## Vérifier le statut des événements {#event-statuses}

Tous les événements traités sont regroupés dans une seule vue, dans le dossier **Historique des événements** ou l’explorateur. Ils peuvent être classés par type d’événement ou par **statut**.

Les statuts possibles sont les suivants :

* **En attente**

   * Un événement en attente peut être un événement qui vient d’être collecté et qui n’a pas encore été traité. La colonne **[!UICONTROL Nombre d’erreurs]** affiche la valeur 0. Le modèle d’e-mail n’a pas encore été lié.
   * Un événement en attente peut également être un événement traité, mais dont la confirmation est erronée. La colonne **[!UICONTROL Nombre d’erreurs]** affiche une valeur différente de 0. Pour savoir quand cet événement sera traité à nouveau, consultez la colonne **[!UICONTROL Traitement demandé le]**.

* **En attente de diffusion**
L’événement a été traité et le modèle de diffusion est associé. L’e-mail est en attente de diffusion et le processus de diffusion classique est appliqué. Pour plus d’informations, vous pouvez ouvrir la diffusion.
* **Envoyé**, **Ignoré** et **Erreur de diffusion**
Ces statuts de diffusion sont récupérés à partir du 
workflow **updateEventsStatus**. Pour plus d’informations, vous pouvez ouvrir la diffusion correspondante.
* **Événement non pris en charge**
La phase de routage des messages transactionnels a échoué. Par exemple, Adobe Campaign n’a pas trouvé l’e-mail qui sert de modèle pour l’événement.
* **Evénement ayant expiré**
Le nombre maximum de tentatives d’envoi a été atteint. L’événement est considéré comme nul.

## Recycler les événements {#event-recycling}

Si l&#39;envoi d&#39;un message sur un canal spécifique échoue, Adobe Campaign peut renvoyer le message en utilisant un autre canal. Par exemple, si l&#39;envoi d&#39;un message sur le canal SMS échoue, le message est renvoyé en utilisant le canal email.

Pour cela, vous devez paramétrer un workflow qui recrée tous les événements dont le statut est **Erreur de diffusion**, et leur assigner un canal différent de celui utilisé précédemment.

>[!CAUTION]
>
>Cette étape ne peut être réalisée qu&#39;à l&#39;aide d&#39;un workflow et est donc réservée à des utilisateurs experts. Pour plus d&#39;informations, veuillez contacter votre chargé de compte Adobe.
