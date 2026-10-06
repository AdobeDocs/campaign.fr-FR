---
product: campaign
title: Gestion de contenu
description: Gestion de contenu
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9b225f78-1959-4e4f-aa4e-ff8a63051154
TQID: 'https://experienceleague.adobe.com/7owt-TM494cZq-Knz55qMpCAAtGhlpaKOlf2iXXeqo4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 100%
---
# Gestion de contenu{#content-management}

Une activité **Gestion de contenu** vous permet de créer et de manipuler un contenu ainsi que de générer les fichiers à partir de ce contenu. Ce contenu peut ensuite être diffusé à l’aide d’une activité « Diffusion ».

>[!CAUTION]
>
>La gestion de contenu est un module optionnel d’Adobe Campaign. Veuillez vérifier votre contrat de licence.

>[!NOTE]
>
>L’interface d’utilisation d’Adobe Campaign Web vous permet d’utiliser des fragments de contenu pour votre contenu. Cela permet aux utilisateurs et utilisatrices marketing de précréer plusieurs blocs de contenu personnalisés, grâce à des composants réutilisables pouvant être référencés dans un ou plusieurs messages, ce qui vous permet d’assembler rapidement le contenu des messages dans un processus de conception amélioré. Pour en savoir plus sur les fragments de contenu, reportez-vous à la [documentation de l’interface d’utilisation d’Adobe Campaign Web.](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments){target=_blank}

Les propriétés de l&#39;activité se divisent en trois étapes :

* **Sélection du contenu**: le contenu peut avoir été créé précédemment ou peut être créé depuis l&#39;activité.
* **Mise à jour du contenu**: la tâche peut modifier l&#39;objet du contenu ou importer tout le contenu XML.
* **Action**: le contenu résultant peut être enregistré ou généré.

  ![](assets/content_mgmt_edit.png)

1. **Content**

   * **[!UICONTROL Spécifié par la transition]**

     Cette option vous permet d’utiliser le contenu spécifié dans la transition, c’est-à-dire que l’événement qui active la gestion de contenu doit contenir une variable **[!UICONTROL contentId]**. Cette variable peut avoir été définie par une gestion de contenu précédente ou par un quelconque script.

   * **[!UICONTROL Explicite]**

     Cette option permet de sélectionner un contenu déjà créé, à partir du champ **[!UICONTROL Contenu]**. Ce champ n&#39;est visible que lorsque l&#39;option **[!UICONTROL Explicite]** est sélectionnée.

     ![](assets/content_mgmt_explicit.png)

   * **[!UICONTROL Calculé par un script]**

     L&#39;identifiant du contenu est calculé par un script. Le champ **[!UICONTROL Script]** permet de définir un template JavaScript évaluant l&#39;identifiant (la clé primaire) du contenu. Ce champ n&#39;est visible que lorsque l&#39;option **[!UICONTROL Calculé par un script]** est sélectionnée.

     ![](assets/content_mgmt_script.png)

   * **[!UICONTROL Nouveau, créé depuis un modèle de publication]**

     Créer un nouveau contenu depuis un modèle de publication. Ce nouveau contenu sera enregistré dans le dossier indiqué dans le champ **[!UICONTROL Chaîne]**. Le champ **[!UICONTROL Modèle]** indique le modèle de publication à utiliser pour créer le contenu.

     ![](assets/content_mgmt_new.png)

1. **Mettre à jour le contenu**

   * **[!UICONTROL Objet]**

     Ce champ permet de modifier l&#39;objet du contenu.

   * **[!UICONTROL Accès aux données provenant d&#39;un flux XML]**

     Cette option permet de construire le contenu à partir d&#39;un document XML téléchargé depuis un serveur Web et éventuellement de le transformer via une feuille de style XSL. Lorsque cette option est cochée, le champ **[!UICONTROL URL]** indique l&#39;URL de téléchargement du contenu XML. Le champ **[!UICONTROL Feuille de style XSL]** permet d&#39;indiquer la feuille de style à utiliser pour transformer le document XML téléchargé. Cette propriété est optionnelle.

     ![](assets/content_mgmt_xmlcontent.png)

1. **Action à effectuer**

   * **[!UICONTROL Enregistrer]**

     Cette option enregistre le contenu créé ou modifié.

     La transition sortante est activée une seule fois avec pour paramètre l&#39;identifiant du contenu enregistré dans la variable **[!UICONTROL contentId]**.

   * **[!UICONTROL Générer]**

     Cette option enregistre le contenu puis génère les fichiers de sortie pour chacun des modèles de transformation dont le type de publication est &#39;Fichier&#39;.

     ![](assets/content_mgmt_generate.png)

     La transition sortante est activée pour chacun des fichiers générés avec pour paramètre l&#39;identifiant du contenu enregistré dans la variable **[!UICONTROL contentId]** et le nom du fichier dans la variable **[!UICONTROL filename]**.

## Paramètres d&#39;entrée {#input-parameters}

* contentId

Identifiant du contenu à utiliser, si l&#39;option **[!UICONTROL Spécifié par la transition]** est activée.

## Paramètres de sortie {#output-parameters}

* contentId

  Identifiant du contenu.

* filename

  Nom complet du fichier généré, si l&#39;action sélectionnée est **[!UICONTROL Générer]**.
