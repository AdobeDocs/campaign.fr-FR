---
product: Adobe Campaign
title: Prise en main de l'architecture de Campaign
description: Découvrez les environnements et notions de base du déploiement
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 100%

---

# Prise en main de l&#39;architecture de Campaign{#gs-ac-archi}

## Environnements

Campaign est disponible sous forme d&#39;instances individuelles, où chaque instance représente un environnement Campaign complet.

Trois types d&#39;environnements sont disponibles avec le Cloud Service de Campaign :

* **Environnement de production** : héberge les applications destinées aux professionnels.

* **Environnement d&#39;évaluation** : utilisé pour divers tests de performances et de qualité avant que les modifications apportées à l&#39;application ne soient envoyées à l&#39;environnement de production.

* **Environnement de développement** : permet aux développeurs d&#39;implémenter Campaign dans les mêmes conditions d&#39;exécution que les environnements d&#39;évaluation et de production.

Vous pouvez exporter et importer des packages d&#39;un environnement à l&#39;autre.

↗️ Apprenez-en davantage sur les packages en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html?lang=fr)

## Déploiement Mid-sourcing{#mid-sourcing-deployment}

La communication générale entre les serveurs et les processus est réalisée conformément au schéma suivant :

![](assets/architecture.png)

* Les modules de diffusion et de gestion des mails rebonds sont désactivés sur l&#39;instance.

* L&#39;application est configurée pour déléguer les envois des messages à un serveur de mid-sourcing distant via des appels SOAP (sur HTTP ou HTTPS).

>[!NOTE]
>
> Campaign v8 repose sur une architecture hybride. Si vous effectuez une transition à partir de Campaign Classic v7, veuillez noter que toutes les diffusions passent par le serveur de midsourcing.
> Par conséquent, le routage interne est **impossible** dans Campaign v8 et le compte externe a été désactivé en conséquence.

## Architecture de Message Center{#transac-msg-archi}

La messagerie transactionnelle (Message Center) est le module de Campaign conçu pour gérer les messages de déclenchement.

💡 Découvrez comment envoyer des messages transactionnels dans [cette section](../send/transactional.md).

En réponse à l&#39;action d&#39;un client sur un site web, un événement est envoyé à Campaign par l&#39;intermédiaire d&#39;une API REST et le modèle de message est renseigné avec les informations ou les données fournies par le biais de l&#39;appel API. En outre, un message transactionnel est envoyé en temps réel au client. Ces messages peuvent être envoyés individuellement ou par lots via e-mail, SMS ou notifications push.

Dans cette architecture spécifique, la cellule d&#39;exécution est séparée de l&#39;instance de pilotage, ce qui offre une grande disponibilité et une meilleure gestion de la charge.

* L&#39;**instance de pilotage** (ou instance marketing) est utilisée par les spécialistes marketing et les équipes informatiques pour créer, configurer et publier des modèles de messages. Cette instance centralise également la surveillance et l&#39;historique des événements.

   💡 Découvrez comment créer et publier des modèles de messages dans [cette section](../send/transactional.md).

* L&#39;**instance d&#39;exécution** renvoie les événements entrants (réinitialisation du mot de passe ou commandes à partir d&#39;un site web, par exemple) et envoie des messages personnalisés. Il peut y avoir plusieurs instances d&#39;exécution pour traiter les messages par l&#39;intermédiaire de la répartition de charge et mettre à l&#39;échelle le nombre d&#39;événements à poursuivre pour une disponibilité maximale.

>[!CAUTION]
>
>L&#39;instance de pilotage et la ou les instance(s) d&#39;exécution doivent être installées sur des machines différentes. Elles ne peuvent pas partager la même instance Campaign.

![](assets/messagecenter_diagram.png)

### Authentification

Pour utiliser ces fonctionnalités, les utilisateurs d&#39;Adobe Campaign se connectent à l&#39;instance de pilotage afin de créer les modèles de messages transactionnels, générer la prévisualisation du message grâce à une adresse de contrôle, afficher des rapports et suivre les instances d&#39;exécution.

* Instance d&#39;exécution unique
Lors de l&#39;interaction avec une instance d&#39;exécution Message Center hébergée par Adobe, un système externe peut d&#39;abord récupérer un jeton de session (qui expire par défaut dans les 24 heures), en effectuant un appel API à la méthode de connexion à la session, et ce, à l&#39;aide d&#39;un nom d&#39;utilisateur et d&#39;un mot de passe fournis pour le compte.
Ensuite, avec le jeton de session fourni par l&#39;instance d&#39;exécution en réponse à l&#39;appel ci-dessus, l&#39;application externe peut lancer des appels API SOAP (rtEvents ou batchEvents) pour envoyer des communications, et ce, sans qu&#39;il y ait besoin d&#39;inclure le nom d&#39;utilisateur et le mot de passe du compte dans chaque appel SOAP.

* Instances d&#39;exécution multiples
Dans une architecture d&#39;exécution multi-cellules avec des instances d&#39;exécution multiples derrière une répartition de charge, la méthode de connexion invoquée par l&#39;application externe passe par la répartition de charge. Pour cette raison, une authentification par jeton ne peut pas être utilisée. Une authentification par utilisateur/mot de passe est requise.

↗️ Apprenez-en davantage sur les événements de messagerie transactionnelle en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html?lang=fr#about-transactional-messaging-datamodel)