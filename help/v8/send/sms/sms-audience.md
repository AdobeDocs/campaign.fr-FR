---
title: Sélection de l'audience par SMS
description: Découvrez comment configurer l'audience d'une diffusion SMS
feature: SMS
role: User
level: Beginner, Intermediate
source-git-commit: 24a6d56a79995cd0113d8438d1bd3314a3872e35
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 17%

---


# Sélectionner l&#39;audience de votre diffusion SMS {#sms-audience}

Avant de sélectionner votre audience, [apprenez-en plus sur l’audience ici](../../audiences/gs-audiences.md).

Dans la plupart des cas, la cible principale d&#39;une diffusion est extraite de la base de données Adobe Campaign (mode par défaut). Cependant, l&#39;audience peut également être stockée dans un fichier externe. [En savoir plus dans cette section](#external-audience).

## Audience dans Adobe Campaign

Pour sélectionner l&#39;audience de votre diffusion, procédez comme suit :

1. Dans l&#39;éditeur de diffusion, cliquez sur le lien **[!UICONTROL Pour]**. Une fenêtre **[!UICONTROL Sélectionner la cible]** s’ouvre.

1. L&#39;audience étant stockée dans la base de données Adobe Campaign, dans l&#39;onglet **[!UICONTROL Cible principale]**, sélectionnez l&#39;option **[!UICONTROL Définie dans la base de données]** .

   ![](assets/audience_to.png){zoomable="yes"}

1. Sélectionnez le **[!UICONTROL Mapping de ciblage]** dans la liste déroulante. Le mapping de ciblage par défaut d’Adobe Campaign est Destinataires, basé sur le schéma **[!UICONTROL nms:recipient]** .

   D’autres mappings de ciblage sont disponibles et certains d’entre eux peuvent être liés à votre configuration spécifique. Pour plus d&#39;informations sur les mappings de ciblage, reportez-vous à la section [Utilisation des mappings de ciblage](../../audiences/target-mappings.md).

1. Cliquez sur le bouton **[!UICONTROL Ajouter]** pour définir les filtres de restriction.

   Vous pouvez alors sélectionner le type de filtrage à appliquer :

   ![](assets/audience_filters.png){zoomable="yes"}

   Pour utiliser un type de cible, sélectionnez-le et cliquez sur le bouton **[!UICONTROL Suivant]** .

   Voici les types de cibles proposés par défaut :

   * **[!UICONTROL Conditions de filtrage]** : permet de définir une requête et d&#39;afficher le résultat.
   * **[!UICONTROL Une liste de destinataires]** : vous permet de sélectionner une liste que vous avez préparée contenant votre audience
   * **[!UICONTROL Un destinataire]** : permet de sélectionner directement un destinataire dans la table.
   * **[!UICONTROL Destinataires inclus dans un dossier]** : permet de sélectionner un dossier dans l’arborescence de navigation de l’explorateur
   * **[!UICONTROL Destinataires d&#39;une diffusion]** : permet de sélectionner l&#39;audience d&#39;une diffusion précédente
   * **[!UICONTROL Destinataires des diffusions appartenant à un dossier]** : permet de sélectionner l&#39;audience de toutes les diffusions d&#39;un dossier donné
   * **[!UICONTROL Abonnés d&#39;un service d&#39;information]** : cette option vous permet de sélectionner une newsletter à laquelle les destinataires doivent être abonnés pour être ciblés par la diffusion en cours de création.
   * **[!UICONTROL Filtres utilisateur]** : permet d’utiliser les filtres prédéfinis.

   L&#39;option **[!UICONTROL Exclure les destinataires de ce segment]** vous permet de cibler sur les destinataires qui ne répondent pas aux critères de ciblage définis. Pour utiliser cette option, cochez la case correspondante puis opérez un ciblage, comme défini précédemment, pour exclure les profils en résultant.

1. Saisissez le nom de votre audience dans le champ libellé, puis cliquez sur le bouton **[!UICONTROL Terminer]** pour valider votre audience.

   ![](assets/audience_finish.png){zoomable="yes"}

   Vous pouvez ajouter autant de population cible que nécessaire en cliquant de nouveau sur le bouton **[!UICONTROL Ajouter]** . Vous pouvez également en supprimer certains en cliquant sur la croix située après leur libellé.

## Audience dans un fichier externe {#external-audience}

Vous pouvez utiliser Adobe Campaign pour envoyer une diffusion sur une audience qui ne se trouve pas dans sa base mais dans un fichier externe.

Pour cela, procédez comme suit :

1. Dans l&#39;éditeur de diffusion, cliquez sur le lien **[!UICONTROL Pour]**. Une fenêtre **[!UICONTROL Sélectionner la cible]** s’ouvre.

1. Choisissez l&#39;option **[!UICONTROL Définie dans un fichier externe]** .

   ![](assets/audience_externalfile.png){zoomable="yes"}

1. Par défaut, les destinataires sont importés dans la base de données. Vous devez sélectionner le **[!UICONTROL mapping de ciblage]** dans ce cas. Pour plus d&#39;informations sur les mappings de ciblage, reportez-vous à la section [Utilisation des mappings de ciblage](../../audiences/target-mappings.md).

   Sinon, vous pouvez également choisir **[!UICONTROL Ne pas importer les destinataires dans la base de données]**.

1. Lors de l&#39;import de votre fichier, cliquez sur le lien **[!UICONTROL Définition du format du fichier...]** pour sélectionner et configurer le fichier externe.

1. Cliquez sur le bouton **[!UICONTROL Terminer]** pour valider votre audience.
