---
title: Modification de votre table de destinataires par défaut
description: Découvrez comment utiliser une table de destinataires personnalisée
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 100%

---

# Utilisation d’une table des destinataires personnalisée{#gs-ac-custom-recipient}

Adobe Campaign s&#39;accompagne d&#39;une table des profils native : **nmsRecipient**. Cette table comporte un certain nombre de champs prédéfinis et de tables faciles à étendre. En savoir plus au sujet de cette table sur [cette page](datamodel.md#ootb-profiles).

L&#39;extension de table native offre de la flexibilité. Toutefois, elle ne permet pas de supprimer certains champs ou liens inutilisés. Par conséquent, l&#39;utilisation d&#39;une table de destinataires personnalisée est une option qui peut s&#39;avérer pratique lorsque votre modèle de données diffère considérablement de la structure de table de destinataires native Campaign, ou encore ou si vous disposez d&#39;un grand nombre de profils.  Toutefois, cette méthode nécessite de prendre certaines précautions lors de son implémentation.

Cette fonctionnalité permet à Adobe Campaign de traiter les données d&#39;une base externe. Ces données sont ensuite utilisées comme un ensemble de profils pour les diffusions. L&#39;implémentation de ce processus implique des limitations, telles que :

* Pas de flux de mise à jour vers et depuis la base de données cloud de Campaign : les données de cette table peuvent être mises à jour directement via le moteur de base de données qui l&#39;héberge.
* Les processus s&#39;exécutant sur la base de données existante doivent être stables.
* Utilisation d&#39;une base de données de profils avec une structure différente de celle proposée en standard : possibilité de diffuser avec une même instance vers des profils enregistrés dans des tables différentes, avec des structures différentes.

Cette section décrit les points clés à connaître pour le mapping des tables existantes dans Adobe Campaign, ainsi que les paramètres de configuration à appliquer pour exécuter des diffusions en fonction de n&#39;importe quelle table. Elle décrit également comment concevoir des interfaces de requête pour les utilisateurs finaux.

>[!CAUTION]
>
>La personnalisation d&#39;Adobe Campaign est réservée aux utilisateurs experts. Elle nécessite en effet une expertise en matière de conception de schémas et de formulaires de saisie.

