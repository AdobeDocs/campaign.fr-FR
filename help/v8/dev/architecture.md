---
solution: Campaign Classic
product: campaign
title: Prise en main de l’architecture Campaign
description: Prise en main de l’architecture Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
translation-type: tm+mt
source-git-commit: cd6691fc04999927c5c50fecfb03cac6139729df
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 11%

---

# Commencer avec l’architecture Campaign{#gs-ac-archi}

## Environnements

Campaign est rendu disponible en tant qu’instances individuelles avec chaque instance représentant un environnement Campaign complet.

Trois types d&#39;environnements disponibles avec le Cloud Service Campaign :

* Environnement de production : héberge les applications destinées aux professionnels de l’entreprise.

* Environnement d’étape : utilisé pour divers tests de performances et de qualité avant que les modifications apportées à l&#39;application ne soient répercutées sur l&#39;environnement de production.

* Environnement de développement : permet aux développeurs d’implémenter Campaign dans les mêmes conditions d’exécution que les environnements d’étape et de production.

Vous pouvez exporter et importer des packages d’un environnement à l’autre.

:flèche_supérieur_droite : En savoir plus sur les packages dans la [documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html?lang=en#about-data-packages)

## Déploiement Mid-sourcing{#mid-sourcing-deployment}

La communication générale entre les serveurs et les processus est réalisée conformément au schéma suivant :

![](assets/architecture.png)

* Les modules de diffusion et de gestion des mails rebonds sont désactivés sur l&#39;instance.

* L&#39;application est configurée pour déléguer les envois des messages à un serveur de mid-sourcing distant via des appels SOAP (sur HTTP ou HTTPS).

>[!NOTE]
>
> Campaign v8 repose sur une architecture hybride. Si vous effectuez une transition à partir de Campaign Classic v7, notez que toutes les diffusions passent par le serveur de midsourcing.
> Par conséquent, le routage interne est **impossible** dans Campaign v8 et le compte externe a été désactivé en conséquence.


## Architecture du Centre de messages{#transac-msg-archi}

La messagerie transactionnelle (Centre de messages) est le module Campaign conçu pour gérer les messages de déclenchement.

: bulb: Découvrez comment envoyer des messages transactionnels dans [cette section](../send/transactional.md).

En réponse à l’action d’un client sur un site Web, un événement est envoyé à Campaign par l’intermédiaire d’une API REST et le modèle de message est renseigné avec les informations ou les données fournies par le biais de l’appel d’API, et un message transactionnel est envoyé en temps réel au client. Ces messages peuvent être envoyés individuellement ou par lots par courriel, SMS ou notifications Push.

Dans cette architecture spécifique, la cellule d’exécution est séparée de l’instance de pilotage pour garantir une haute disponibilité et une gestion de la charge.

* L&#39;**Instance de pilotage** (ou instance de marketing) est utilisée par les spécialistes du marketing et les équipes informatiques pour créer, configurer et publier des modèles de messages. Cette instance centralise également la surveillance et l&#39;historique des événements.

   :flèche_supérieur_droite : Découvrez comment créer et publier des modèles de message dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/message-templates/introduction.html?lang=en#transactional-messaging)

* L&#39;**Instance d&#39;exécution** renvoie les événements entrants (réinitialisation du mot de passe ou commandes à partir d&#39;un site Web, par exemple) et envoie des messages personnalisés. Il peut y avoir plusieurs instances d&#39;exécution pour traiter les messages par l&#39;intermédiaire de l&#39;équilibreur de charge et mettre à l&#39;échelle le nombre de événements à effectuer pour une disponibilité maximale.

>[!CAUTION]
>
>L&#39;instance de contrôle et la ou les instances d&#39;exécution doivent être installées sur des machines différentes. Elles ne peuvent pas partager la même instance Campaign.

![](assets/messagecenter_diagram.png)

:flèche_supérieur_droite : L&#39;architecture du Centre de messages est décrite dans la [documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/transactional-messaging-architecture.html?lang=en#transactional-messaging)


### Authentification

Pour utiliser ces fonctionnalités, les utilisateurs d’Adobe Campaign se connectent à l’instance de pilotage pour créer des modèles de message transactionnel, générer la prévisualisation de messages à l’aide d’une liste initiale, afficher des rapports et surveiller les instances d&#39;exécution.

* Instance d&#39;exécution unique
Lors de l&#39;interaction avec une instance d&#39;exécution Message Center hébergée par un Adobe, un système externe peut d&#39;abord récupérer un jeton de session (qui expire par défaut dans 24 heures), en effectuant un appel d&#39;api à la méthode de connexion de la session, à l&#39;aide d&#39;un identifiant de compte et d&#39;un mot de passe fournis.
Ensuite, avec le jeton session fourni par l&#39;instance d&#39;exécution en réponse à l&#39;appel ci-dessus, l&#39;application externe peut lancer des appels d&#39;api SOAP (rtEvents ou batchEvents) pour envoyer des communications, sans avoir à inclure dans chaque appel SOAP l&#39;identifiant de compte et le mot de passe.

* Instances d&#39;exécution multiples
Dans une architecture d&#39;exécution à plusieurs cellules avec plusieurs instances d&#39;exécution derrière un équilibreur de charge, la méthode d&#39;ouverture de session invoquée par l&#39;application externe passe par l&#39;équilibreur de charge : pour cette raison, une authentification par jeton ne peut pas être utilisée. Une authentification par utilisateur/mot de passe est requise.

:flèche_supérieur_droite : En savoir plus sur les événements de messagerie transactionnelle dans [la documentation Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/event-description.html?lang=en#about-transactional-messaging-datamodel)