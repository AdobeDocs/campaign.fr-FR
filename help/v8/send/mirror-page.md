---
title: Ajouter un lien vers la page miroir
description: Découvrez comment ajouter et configurer un lien vers la page miroir.
feature: Email
role: User
level: Beginner
exl-id: 7bf3937c-484d-4404-8a9b-de7a10f5455a
source-git-commit: b333db04dd10cc28956959a446f6567e2a89b2d4
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 100%

---

# Lien vers la page miroir {#mirror-page}

## À propos de la page miroir {#about-mirror-page}

La page miroir est une version en ligne de votre e-mail.

La plupart des clients de messagerie affichent les images sans problème. Toutefois, certains préréglages peuvent empêcher le rendu des images, notamment pour des raisons de sécurité. Les utilisateurs et utilisatrices consultent la page miroir d’un e-mail en cas de problème d’affichage des images dans leur boîte de réception ou lorsque ces dernières sont endommagées. Il est également recommandé de fournir une version en ligne pour des raisons d’accessibilité ou pour faciliter le partage sur les réseaux sociaux.

La page miroir générée par Adobe Campaign contient toutes les données de personnalisation.

![exemple de lien miroir](assets/mirror-page-link.png){width="600" align="left"}

## Ajouter un lien vers la page miroir {#link-to-mirror-page}

Il est recommandé d’insérer un lien vers la page miroir. Vous pouvez nommer le lien « Afficher cet e-mail dans votre navigateur » ou « Lire ceci en ligne », par exemple. Il se trouve généralement dans l’en-tête ou le pied de page de l’e-mail.

Dans Adobe Campaign, vous pouvez insérer un lien vers la page miroir dans le contenu de l’e-mail à l’aide du **bloc de personnalisation** dédié. Le bloc de personnalisation intégré **Lien vers la page miroir** insère le code suivant dans le contenu de votre e-mail : `<%@ include view='MirrorPage' %>`.

![](assets/mirror-page-insert.png){width="800" align="left"}


Pour plus d’informations sur l’insertion de blocs de contenu de personnalisation, reportez-vous aux [blocs de personnalisation](personalization-blocks.md).

## Gérer la génération des pages miroir {#mirror-page-generation}

Par défaut, la page miroir est automatiquement générée par Adobe Campaign si le contenu de l’e-mail n’est pas vide et s’il comporte un lien vers la page miroir (ou lien miroir).

Vous pouvez choisir le mode de génération de la page miroir de l’e-mail. Plusieurs options s’offrent à vous dans les propriétés de la diffusion. Pour accéder à ces options, procédez comme suit :

1. Accédez à l’onglet **[!UICONTROL Validité]** des propriétés de l’e-mail.
1. Dans la section **Gestion de la page miroir**, consultez la liste déroulante **[!UICONTROL Mode]** pour découvrir toutes les options.

![](assets/mirror-page-generation.png){width="800" align="left"}

Outre le mode par défaut, les options suivantes sont disponibles :

* **[!UICONTROL Forcer la génération de la page miroir]** : ce mode permet de générer la page miroir même si aucun lien vers la page miroir n’est inséré dans la diffusion.
* **[!UICONTROL Ne pas générer de page miroir]** : ce mode permet d’éviter de générer une page miroir, même si le lien est présent dans la diffusion.
* **[!UICONTROL Générer une page miroir accessible uniquement depuis l’identifiant du message]** : lorsque le lien de la page miroir n’est pas présent dans le contenu de l’e-mail, utilisez cette option pour permettre l’accès au contenu de la page miroir, dans la fenêtre du log de diffusion, comme décrit ci-dessous.

## Vérifier la page miroir pour un ou une destinataire {#mirror-page-access}

Vous pouvez accéder au contenu de la page miroir telle qu’elle s’affiche pour un ou une destinataire spécifique d’une diffusion et renseignée avec les données de personnalisation de cette personne.

Pour accéder à cette page miroir, procédez comme suit :

1. Une fois la diffusion envoyée, ouvrez-la et accédez à l’onglet **[!UICONTROL Diffusion]**.

1. Sélectionnez un ou une destinataire, puis cliquez sur le lien **[!UICONTROL Afficher la page miroir de ce message...]**.

   ![](assets/mirror-page-display.png){width="800" align="left"}

   La page miroir s’affiche dans un écran dédié, avec les données de personnalisation du ou de la destinataire sélectionné(e).
