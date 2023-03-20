---
title: Champs de personnalisation
description: Découvrez comment insérer des données de personnalisation dans le contenu de votre message
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 45%

---


# Champs de personnalisation{#personalization-fields}

Utilisez des champs de personnalisation pour diffuser du contenu personnalisé en un à un, selon les règles que vous avez définies pour chaque destinataire.

Un champ de personnalisation est une référence de champ de données unique utilisée lors de la personnalisation d’une diffusion pour un destinataire spécifique. La valeur réelle des données est insérée lors de la phase d’analyse de la diffusion.

![exemple de personnalisation des messages](assets/perso-name-sample.png)

## Syntaxe

Une balise de personnalisation utilise toujours la syntaxe suivante : `<%=table.field%>`.

Par exemple, pour insérer le nom du destinataire, stocké dans la table des destinataires, le champ de personnalisation utilise la variable `<%= recipient.lastName %>` syntaxe.

>[!CAUTION]
>
>Le contenu des champs de personnalisation ne peut pas dépasser 1 024 caractères.

## Insérer un champ de personnalisation {#insert-a-personalization-field}

Pour insérer des champs de personnalisation, cliquez sur l&#39;icône déroulante accessible à partir de n&#39;importe quel champ d&#39;en-tête, d&#39;objet ou de corps de message.

![insérer un champ de personnalisation](assets/perso-field-insert.png)

Les champs de personnalisation sont insérés et peuvent être interprétés par Adobe Campaign : lors de la préparation du message, les champs sont remplacés par leur valeur pour un destinataire donné.

![champs de personnalisation d&#39;un email](assets/perso-fields-in-msg.png)

Ce remplacement peut ensuite être testé dans la variable **[!UICONTROL Aperçu]** .

<!--Learn more about message preview in [this page]().-->

## Cas pratique : personnaliser l’objet de l’email {#personalization-fields-uc}

Dans le cas d&#39;utilisation ci-dessous, apprenez à personnaliser un objet et un corps d&#39;email avec des données de destinataire :

1. Créez une nouvelle diffusion ou ouvrez une diffusion existante de email.
1. Accédez au **[!UICONTROL Objet]** lien pour éditer l&#39;objet du message.
1. Saisissez le texte &quot;**Offre spéciale pour**&quot; et utilisez le dernier bouton de la barre d&#39;outils pour insérer un champ de personnalisation. Choisissez **[!UICONTROL Destinataire>Prénom]**.
1. Répétez l&#39;opération pour insérer le nom du destinataire. Insérez des espaces entre chacun de ces champs de personnalisation.
1. Cliquez sur **[!UICONTROL OK]** pour valider.
1. Insérez ensuite la personnalisation dans le corps du message. Pour cela, cliquez dans le contenu du message et cliquez sur le bouton d&#39;insertion de champs.
1. Choisissez **[!UICONTROL Destinataire > Autre...]**.
1. Sélectionnez le champ contenant l&#39;information à afficher et cliquez sur **[!UICONTROL Ok]**.
1. Cliquez sur l&#39;onglet **[!UICONTROL Aperçu]** pour visualiser le résultat de la personnalisation. Vous devez sélectionner un destinataire pour afficher son message.



## Tutoriel vidéo {#personalization-field-video}

Découvrez comment ajouter un champ de personnalisation à l’objet et au contenu d’une diffusion email dans la vidéo suivante.

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)

