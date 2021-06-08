---
product: Adobe Campaign
title: Prise en main de l’architecture de Campaign
description: Découvrir les environnements et les bases du déploiement
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: 8b31e24e0b6cfb699179e62366bc6706e9019382
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 76%

---

# Prise en main de l’architecture de Campaign{#gs-ac-archi}

## Environnements

Campaign est disponible sous forme d’instances individuelles, où chaque instance représente un environnement Campaign complet.

Trois types d’environnements sont disponibles avec le Cloud Service de Campaign :

* **Environnement** de production : héberge les applications destinées aux professionnels.

* **Environnement d’évaluation** : utilisés pour divers tests de performance et de qualité avant que les modifications apportées à l’application ne soient transmises à l’environnement de production.

* **Environnement** de développement : permet aux développeurs d’implémenter Campaign dans les mêmes conditions d’exécution que les environnements d’évaluation et de production.

Vous pouvez exporter et importer des packages d’un environnement à l’autre.

[!DNL :arrow_upper_right:] En savoir plus sur les packages dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Déploiement midsourcing{#mid-sourcing-deployment}

La communication générale entre les serveurs et les processus est réalisée conformément au schéma suivant :

![](assets/architecture.png)

* Les modules de diffusion et de gestion des mails rebonds sont désactivés sur l&#39;instance.

* L&#39;application est configurée pour déléguer les envois des messages à un serveur de mid-sourcing distant via des appels SOAP (sur HTTP ou HTTPS).

>[!NOTE]
>
> Campaign v8 repose sur une architecture hybride. Si vous effectuez une transition à partir de Campaign Classic v7, veuillez noter que toutes les diffusions passent par le serveur de midsourcing.
> Par conséquent, le routage interne est **impossible** dans Campaign v8 et le compte externe a été désactivé en conséquence.

## Architecture de Message Center{#transac-msg-archi}

La messagerie transactionnelle (Message Center) est le module de Campaign conçu pour gérer les messages de déclenchement.

[!DNL :bulb:] Découvrez comment envoyer des messages transactionnels dans [cette section](../send/transactional.md).

En réponse à l’action d’un client sur un site web, un événement est envoyé à Campaign par l’intermédiaire d’une API REST et le modèle de message est renseigné avec les informations ou les données fournies par le biais de l’appel API. En outre, un message transactionnel est envoyé en temps réel au client. Ces messages peuvent être envoyés individuellement ou par lots via e-mail, SMS ou notifications push.

Dans cette architecture spécifique, la cellule d’exécution est séparée de l’instance de pilotage, ce qui offre une grande disponibilité et une meilleure gestion de la charge.

* L’**instance de pilotage** (ou instance marketing) est utilisée par les spécialistes marketing et les équipes informatiques pour créer, configurer et publier des modèles de messages. Cette instance centralise également la surveillance et l’historique des événements.

   [!DNL :bulb:] Découvrez comment créer et publier des modèles de messages dans  [cette section](../send/transactional.md).

* L’**instance d’exécution** renvoie les événements entrants (réinitialisation du mot de passe ou commandes à partir d’un site web, par exemple) et envoie des messages personnalisés. Il peut y avoir plusieurs instances d’exécution pour traiter les messages par l’intermédiaire de la répartition de charge et mettre à l’échelle le nombre d’événements à poursuivre pour une disponibilité maximale.

>[!CAUTION]
>
>L’instance de pilotage et la ou les instance(s) d’exécution doivent être installées sur des machines différentes. Elles ne peuvent pas partager la même instance Campaign.

![](assets/messagecenter_diagram.png)

### Authentification

Pour utiliser ces fonctionnalités, les utilisateurs d’Adobe Campaign se connectent à l’instance de pilotage afin de créer les modèles de messages transactionnels, générer la prévisualisation du message grâce à une adresse de contrôle, afficher des rapports et suivre les instances d’exécution.

* Instance d’exécution unique
Lors de l’interaction avec une instance d’exécution Message Center hébergée par un Adobe, un système externe peut d’abord récupérer un jeton de session (qui, par défaut, expire dans 24 heures), en effectuant un appel d’api vers la méthode de connexion de session, à l’aide d’un identifiant de compte et d’un mot de passe fournis.
Ensuite, avec le jeton de session fourni par l’instance d’exécution en réponse à l’appel ci-dessus, l’application externe peut lancer des appels API SOAP (rtEvents ou batchEvents) pour envoyer des communications, et ce, sans qu’il y ait besoin d’inclure le nom d’utilisateur et le mot de passe du compte dans chaque appel SOAP.

* Instances d’exécution multiples
Dans une architecture d’exécution multi-cellules avec des instances d’exécution multiples derrière une répartition de charge, la méthode de connexion invoquée par l’application externe passe par la répartition de charge. Pour cette raison, une authentification par jeton ne peut pas être utilisée. Une authentification par utilisateur/mot de passe est requise.

[!DNL :arrow_upper_right:] En savoir plus sur les événements de messages transactionnels dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)