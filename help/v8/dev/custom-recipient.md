---
solution: Campaign Classic
product: campaign
title: Modifier votre tableau de destinataires par défaut
description: Découvrez comment utiliser un tableau de destinataire personnalisé
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
translation-type: tm+mt
source-git-commit: fc258cac85f1f96b6d03d69eff4e7ac70ba4247d
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 11%

---

# Utilisation d’une table des destinataires personnalisée{#gs-ac-custom-recipient}

Adobe Campaign est livré avec une table de profil intégrée : **nmsRecipient**. Ce tableau comporte un certain nombre de champs et de tableaux prédéfinis qui peuvent être facilement étendus. Pour en savoir plus sur ce tableau, consultez [cette page](datamodel.md#ootb-profiles).

L&#39;extension de table intégrée offre une bonne flexibilité, mais elle ne permet pas de supprimer certains champs ou liens inutilisés. Par conséquent, l’utilisation d’une table de destinataires personnalisée peut s’avérer une bonne option lorsque votre modèle de données diffère considérablement de la structure de table de destinataires intégrée à Campaign ou si vous disposez d’un grand nombre de profils.  Toutefois, cette méthode requiert certaines précautions lors de sa mise en oeuvre.

Cette fonctionnalité permet à Adobe Campaign de traiter les données d’une base de données externe : ces données seront utilisées comme un ensemble de profils pour les diffusions. La mise en oeuvre de ce processus implique des limitations telles que :

* Aucun flux de mise à jour vers et depuis la base de données Campaign Cloud : les données de cette table peuvent être mises à jour directement via le moteur de base de données qui les héberge.
* Les processus qui fonctionnent sur la base de données existante doivent être stables.
* Utilisation d&#39;une base de profils avec une structure différente de celle proposée en standard : possibilité de diffuser avec une même instance vers des profils enregistrés dans des tables différentes, avec des structures différentes.

Cette section décrit les points clés pour mapper les tables existantes en Adobe Campaign et les paramètres de configuration à appliquer pour exécuter des diffusions en fonction de n&#39;importe quelle table. Il décrit également comment concevoir des interfaces d&#39;interrogation pour les utilisateurs finaux.


>[!CAUTION]
>
>La personnalisation Adobe Campaign est réservée aux utilisateurs experts uniquement. Il nécessite une expertise dans la conception de schémas et de formulaires d&#39;entrée.

Voir ce qui est valide/non valide ici : https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html?lang=en#configuring-campaign-classic
