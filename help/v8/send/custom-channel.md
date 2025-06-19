---
title: Commencer avec les canaux externes personnalisés
description: Découvrir comment créer et envoyer des diffusions de canaux externes personnalisées à l’aide d’Adobe Campaign Web
role: User
level: Beginner, Intermediate
exl-id: d2d92de6-3974-41c5-a0fd-09bbf6cf0020
source-git-commit: f94074d954137c4db39b2ef9f85141b79fe3356b
workflow-type: ht
source-wordcount: '268'
ht-degree: 100%

---

# Commencer avec les canaux externes personnalisés {#gs-custom-channel}

Adobe Campaign vous permet de créer des canaux externes personnalisés intégrés à des tiers. Vous pouvez ensuite orchestrer et exécuter des diffusions en fonction de ces canaux.

La création et l’envoi de la diffusion peuvent être effectués dans la console cliente et dans l’interface d’utilisation web. Toutefois, le canal externe personnalisé est effectué uniquement dans la console cliente.

Pour savoir comment créer et envoyer une diffusion basée sur un canal externe personnalisé, consultez cette [page](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html?lang=fr).

Pour créer un canal personnalisé externe dans la console cliente, procédez comme suit :

1. Configurer le schéma, [en savoir plus](#configure-schema)
1. Créer un compte externe, [en savoir plus](#create-ext-account)
1. Créer un modèle de diffusion, [en savoir plus](#create-template)

## Configurer le schéma{#configure-schema}

Tout d’abord, configurez le schéma pour ajouter le nouveau canal à la liste des canaux disponibles.

1. Dans l’explorateur Campaign, sélectionnez **Administration** > **Configuration** > **Schémas de données**.

1. Créez une extension de schéma pour étendre l’énumération messageType au nouveau canal.

   Par exemple :

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## Créer un compte externe{#create-ext-account}

Ensuite, vous devez créer un compte externe de routage.

1. Dans l’explorateur Campaign, sélectionnez **Administration** > **Plateforme** > **Comptes externes**.

1. Créez un compte externe.

1. Sélectionnez le canal et modifiez le mode de diffusion sur **Externe**.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## Créer un modèle de diffusion{#create-template}

À présent, nous allons créer le modèle associé au nouveau canal.

1. Dans l’explorateur Campaign, sélectionnez **Ressources** > **Modèles** > **Modèles de diffusion**.

1. Créez un modèle.

1. Cliquez sur **Propriétés** et sélectionnez le dossier et le routage appropriés.

   ![](assets/cus-template.png){zoomable="yes"}

Le nouveau canal est désormais disponible. Vous pouvez créer et exécuter des diffusions qui se déroulent sur ce canal.
