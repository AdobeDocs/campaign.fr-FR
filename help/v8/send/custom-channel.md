---
title: Prise en main des canaux externes personnalisés
description: Découvrez comment créer et envoyer des diffusions de canal externe personnalisées avec Adobe Campaign Web
role: User
level: Beginner, Intermediate
source-git-commit: 4a62c551c43cd5a4866df36cce10e294f35db363
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 4%

---


# Prise en main des canaux externes personnalisés {#gs-custom-channel}

Adobe Campaign vous permet de créer des canaux externes personnalisés intégrés à des tiers. Vous pouvez ensuite orchestrer et exécuter des diffusions en fonction de ces canaux.

La création et l’envoi de la diffusion peuvent être effectués dans la console cliente et dans l’interface utilisateur web. Cependant, le canal externe personnalisé n’est exécuté que dans la console cliente.

Pour savoir comment créer et envoyer une diffusion basée sur un canal externe personnalisé, consultez cette [page](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html).

Pour créer un canal personnalisé externe dans la console cliente, procédez comme suit :

1. Configurez le schéma, [en savoir plus](#configure-schema)
1. Créez un compte externe, [en savoir plus](#create-ext-account)
1. Créez un modèle de diffusion, [en savoir plus](#create-template)

## Configuration du schéma{#configure-schema}

Tout d’abord, vous devez configurer le schéma pour ajouter le nouveau canal à la liste des canaux disponibles.

1. Dans l&#39;Explorateur Campaign, sélectionnez **Administration** > **Configuration** > **Schémas de données**.

1. Créez une extension de schéma pour étendre l’énumération messageType avec le nouveau canal.

   Par exemple :

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## Création d&#39;un nouveau compte externe{#create-ext-account}

Ensuite, vous devez créer un compte externe de routage.

1. Dans l&#39;Explorateur Campaign, sélectionnez **Administration** > **Plateforme** > **Comptes externes**.

1. Créez un compte externe.

1. Sélectionnez le canal et définissez le mode de diffusion sur **Externe**.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## Créer un modèle de diffusion{#create-template}

À présent, nous allons créer le nouveau modèle associé au nouveau canal.

1. Dans l&#39;Explorateur Campaign, sélectionnez **Ressources** > **Modèles** > **Modèles de diffusion**.

1. Créez un modèle.

1. Cliquez sur **Propriétés** et sélectionnez le dossier et le routage appropriés.

   ![](assets/cus-template.png){zoomable="yes"}

Le nouveau canal est désormais disponible. Vous pouvez créer et exécuter des diffusions en fonction de ce canal.


