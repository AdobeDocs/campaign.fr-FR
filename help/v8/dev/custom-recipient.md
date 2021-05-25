---
solution: Campaign v8
product: Adobe Campaign
title: Modifier la table des destinataires par défaut
description: Découvrez comment utiliser une table de destinataires personnalisée
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 11%

---

# Utilisation d’une table des destinataires personnalisée{#gs-ac-custom-recipient}

Adobe Campaign est fourni avec une table de profils intégrée : **nmsRecipient**. Cette table comporte un certain nombre de champs prédéfinis et de tables qui peuvent être facilement étendus. Pour en savoir plus sur ce tableau, consultez [cette page](datamodel.md#ootb-profiles).

L’extension de table intégrée offre une certaine flexibilité, mais elle ne permet pas de supprimer certains champs ou liens inutilisés. Par conséquent, l’utilisation d’une table de destinataires personnalisée peut s’avérer une bonne option lorsque votre modèle de données diffère considérablement de la structure de la table de destinataires intégrée à Campaign ou si vous disposez d’un grand nombre de profils.  Toutefois, cette méthode requiert certaines précautions lors de sa mise en oeuvre.

Cette fonctionnalité permet à Adobe Campaign de traiter les données d’une base de données externe : ces données seront utilisées comme ensemble de profils pour les diffusions. La mise en oeuvre de ce processus implique des restrictions telles que :

* Aucun flux de mise à jour vers et depuis la base de données Campaign Cloud : les données de ce tableau peuvent être mises à jour directement à partir du moteur de base de données qui l’héberge.
* Les processus qui opèrent sur la base existante doivent être stables.
* Utilisation d&#39;une base de profils avec une structure différente de celle proposée en standard : possibilité de diffuser avec une même instance vers des profils enregistrés dans des tables différentes, avec des structures différentes.

Cette section décrit les points clés à associer aux tables existantes dans Adobe Campaign et les paramètres de configuration à appliquer pour exécuter des diffusions en fonction de n’importe quelle table. Il décrit également comment concevoir des interfaces de requêtage pour les utilisateurs finaux.

>[!CAUTION]
>
>La personnalisation d’Adobe Campaign est réservée à des utilisateurs experts uniquement. Elle nécessite une expertise dans la conception de formulaires et de schémas de saisie.

