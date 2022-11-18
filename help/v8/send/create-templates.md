---
product: campaign
title: Utiliser des modèles de diffusion
description: Découvrez comment créer et utiliser des modèles de diffusion dans Campaign
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 42%

---

# Utilisation d’un modèle de diffusion{#work-with-delivery-template}

Utilisez les modèles de diffusion pour normaliser l’aspect créatif afin d’être plus rapide dans l’exécution et le lancement des campagnes.

Un modèle peut systématiquement inclure :

* Typologies
* Adresses d&#39;expéditeur et destinataire
* Blocs de personnalisation de base
* Liens vers les pages miroir et désinscription links
* Contenu, logo de la société ou signature
* Autres propriétés de diffusion, telles que la validité des ressources, les paramètres de reprise ou les paramètres de mise en quarantaine.

![](assets/do-not-localize/how-to-video.png) [Découvrez cette fonctionnalité en vidéo](#delivery-template-video)


## Créer un modèle{#create-a-delivery-template}

Pour créer un modèle de diffusion, vous pouvez dupliquer un modèle intégré, convertir une diffusion existante en modèle ou créer entièrement un modèle de diffusion.

### Dupliquer un modèle d&#39;offre existant{#copy-an-existing-template}

Campaign est fourni avec un ensemble de modèles intégrés pour chaque canal : e-mail, push, SMS, courrier, etc.

Le moyen le plus simple de créer un modèle de diffusion consiste à dupliquer et personnaliser un modèle intégré.

Pour dupliquer un modèle de diffusion, procédez comme suit :

1. Accédez à **[!UICONTROL Ressources > Modèles > Modèles de diffusion]** dans l’explorateur Adobe Campaign.
1. Sélectionnez un modèle de diffusion intégré. Les modèles natifs sont affichés dans la liste.
1. Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Dupliquer]**.

   ![](assets/duplicate-built-in-template.png)

1. Définissez les paramètres du modèle et enregistrez le nouveau modèle.

   ![](assets/delivery-template-new.png)

Le modèle est alors ajouté dans la liste des modèles de diffusion. Vous pouvez maintenant la sélectionner lors de la création d&#39;une nouvelle diffusion.

![](assets/select-the-new-template.png)

### Convertir une diffusion existante en modèle {#convert-an-existing-delivery}

Une diffusion peut être convertie en modèle pour de nouvelles actions de diffusion répétées.

Pour convertir une diffusion en modèle, procédez comme suit :

1. Sélectionnez la diffusion dans la liste des diffusions, accessible à partir du **[!UICONTROL Gestion de campagne]** noeud de l&#39;explorateur Campaign.

1. Cliquez sur le bouton droit de la souris et choisissez **[!UICONTROL Actions > Sauver comme modèle...]**.

   ![](assets/save-as-template.png)

1. Editez les propriétés de la diffusion et sélectionnez le dossier dans lequel le nouveau modèle doit être enregistré (dans la section **[!UICONTROL Dossier]** ) et le dossier dans lequel les diffusions créées à partir de ce modèle doivent être créées (dans la variable **[!UICONTROL Dossier d’exécution]** ).

   ![](assets/template-select-folders.png)

### Créer un modèle {#create-a-new-template}

>[!NOTE]
>
>Pour éviter les erreurs de configuration, Adobe vous recommande de [dupliquer un modèle intégré](#copy-an-existing-template) et personnalisez ses propriétés plutôt que de créer un modèle.

Pour paramétrer entièrement un modèle de diffusion, procédez comme suit :

1. Accédez au **Ressources** dans l’explorateur Campaign, puis sélectionnez **Modèles** then **Modèles de diffusion**.
1. Cliquez sur **Nouveau** dans la barre d&#39;outils pour créer un modèle de diffusion.
1. Définissez la variable **Libellé** et le **Nom interne** du dossier .
1. Enregistrez le modèle et rouvrez-le.
1. Dans la **Propriétés** , adaptez les paramètres.
1. Dans l&#39;onglet **Général**, validez ou modifiez les emplacements sélectionnés dans les menus déroulants **Dossier d&#39;exécution**, **Dossier** et **Routage**.
1. Remplissez la catégorie **Paramètres de l&#39;email** avec le sujet de l&#39;email et la population ciblée.
1. Ajoutez votre **contenu HTML** afin de personnaliser votre modèle. Vous pouvez afficher une page miroir et un lien de désinscription.
1. Sélectionnez l&#39;onglet **Aperçu**. Dans le menu déroulant **Tester la personnalisation**, sélectionnez **Destinataire** pour obtenir un aperçu du modèle en tant que profil choisi.
1. Cliquez sur **Enregistrer**. Le modèle peut maintenant être utilisé dans une diffusion.


## Utilisation de modèles{#use-a-delivery-template}

### Création d’une diffusion depuis un modèle{#create-a-delivery-from-a-template}

Pour créer une diffusion basée sur un modèle existant, vous devez sélectionner le modèle dans la liste des modèles de diffusion proposés.

![](assets/select-the-new-template.png)

Si le modèle ne s’affiche pas, cliquez sur le bouton **[!UICONTROL Choisir le lien]** dossier situé à droite du champ pour parcourir les dossiers Campaign.

![](assets/browse-templates.png)

Sélectionnez le répertoire visé depuis le champ **[!UICONTROL Dossier]** ou cliquez sur l&#39;icône **[!UICONTROL Afficher les fils]** pour afficher le contenu des répertoires situés en sous-arborescence du répertoire courant.

Sélectionnez le modèle de diffusion à utiliser et cliquez sur **[!UICONTROL Ok]**.

### Exécuter un modèle {#execute-a-template}

Vous pouvez lancer l&#39;exécution d&#39;un modèle directement depuis la liste des modèles sans créer de diffusion au préalable.

Pour cela, sélectionnez le modèle à exécuter et cliquez avec le bouton droit de la souris. Sélectionner **[!UICONTROL Actions>Exécuter le modèle de diffusion...]**.

Vous pouvez aussi utiliser le menu **[!UICONTROL Fichier > Actions > Exécuter le modèle de diffusion...]**.

![](assets/execute-delivery-template.png)

Renseignez ensuite les paramètres de la diffusion et cliquez sur **[!UICONTROL Envoyer]**.

Cette action génère une diffusion dans le dossier associé au modèle. Le nom de cette diffusion est le nom du modèle de diffusion à partir duquel elle a été créée.


## Tutoriels vidéo {#delivery-template-video}

### Comment configurer un modèle de diffusion

La vidéo suivante montre comment configurer un modèle pour une diffusion ad hoc.

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### Comment configurer les propriétés des modèles de diffusion

La vidéo suivante montre comment définir les propriétés des modèles de diffusion et explique en détail chaque propriété.

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### Comment déployer un modèle de diffusion ad hoc

Cette vidéo montre comment déployer un modèle de diffusion email ad hoc. Elle explique aussi la différence entre une diffusion email et un workflow de diffusion.

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

D’autres vidéos pratiques sur Campaign Classic sont disponibles [ici](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=fr).