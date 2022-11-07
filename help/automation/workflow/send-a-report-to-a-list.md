---
product: campaign
title: Envoi d’un rapport à une liste
description: Découvrez comment envoyer un rapport à une liste à l’aide d’un workflow
feature: Workflows
source-git-commit: e211c0f01a4813ad29f47652fffac2b44bc0f867
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 35%

---


# Envoi d’un rapport à une liste{#send-a-report-to-a-list}

Ce cas pratique présente comment générer, chaque mois, le rapport d&#39;usine **[!UICONTROL Indicateurs de tracking]** au format PDF et l&#39;envoyer à une liste de destinataires.

![](assets/use_case_report_intro.png)

Les étapes principales de mise en oeuvre de ce cas pratique sont les suivantes :

* Créez une liste de destinataires pour ce rapport. [En savoir plus](#step-1--create-the-recipient-list).
* Créez un modèle de diffusion qui crée une diffusion à chaque exécution du workflow. [En savoir plus](#step-2--create-the-delivery-template).
* Créez un workflow qui génère le rapport au format PDF et l&#39;envoie à la liste des destinataires. [En savoir plus](#step-3--create-the-workflow).

## Étape 1 : Création de la liste des destinataires {#step-1--create-the-recipient-list}

Pour créer la liste des destinataires ciblés, procédez comme suit :

1. Accédez au **[!UICONTROL Profils et cibles]** , cliquez sur l’onglet **[!UICONTROL Listes]** lien.
1. Cliquez sur le bouton **[!UICONTROL Créer]**.
1. Sélectionnez **[!UICONTROL Nouvelle liste]** et créez une liste de destinataires à laquelle envoyer le rapport.

Pour plus d&#39;informations sur la création de listes, reportez-vous à la section [cette section](../../v8/audiences/create-audiences.md).

## Étape 2 : Créer le modèle de diffusion {#step-2--create-the-delivery-template}

Pour créer le modèle de diffusion, procédez comme suit :

1. Accédez au **[!UICONTROL Ressources > Modèles > Modèles de diffusion]** noeud de l’explorateur Adobe Campaign et dupliquez l’objet **[!UICONTROL Diffusion Email]** modèle intégré.

   Pour plus d&#39;informations sur la création d&#39;un modèle de diffusion, reportez-vous à la section [cette section](../../v8/send/create-templates.md).

1. Renseignez les paramètres du modèle : libellé, cible (liste des destinataires précédemment créés), objet et contenu.

   Chaque fois que le workflow est exécuté, la variable **[!UICONTROL Indicateurs de tracking]** Le rapport est mis à jour comme expliqué dans la section [Étape 3 : Créer le workflow](#step-3--creating-the-workflow)).

1. Pour inclure la dernière version du rapport dans la diffusion, vous devez ajouter un **[!UICONTROL Attachement calculé]** :

   * Cliquez sur le bouton **[!UICONTROL Pièces jointes]** et cliquez sur la flèche en regard de l’option **[!UICONTROL Ajouter]** bouton . Sélectionner **[!UICONTROL Pièce jointe calculée..]**.

      ![](assets/use_case_report_4.png)

   * Dans le **[!UICONTROL Type]** , sélectionnez la dernière option : **[!UICONTROL Le nom de fichier est calculé au moment de l&#39;envoi pour chaque message (il peut alors dépendre du profil du destinataire)]**.

      ![](assets/use_case_report_5.png)

      La valeur renseignée dans le champ **[!UICONTROL Libellé]** n&#39;apparaîtra pas dans la diffusion finale.

   * Dans la zone de texte, saisissez le chemin d&#39;accès et le nom du fichier.

      ![](assets/use_case_report_6.png)

      >[!CAUTION]
      >
      >Le chemin et le nom doivent être identiques à ceux saisis dans la variable **[!UICONTROL Code JavaScript]** activité de type du workflow, comme expliqué dans la section [Étape 3 : Créer le workflow](#step-3--creating-the-workflow).

   * Sélectionnez la **[!UICONTROL Avancé]** onglet et vérification **[!UICONTROL Script le nom du fichier affiché dans les courriers envoyés]**. Dans la zone de texte, saisissez le nom de la pièce jointe dans la diffusion finale.

      ![](assets/use_case_report_6bis.png)

## Étape 3 : Créer le workflow {#step-3--creating-the-workflow}

Créez le workflow suivant pour ce cas pratique.

![](assets/use_case_report_8.png)

Il utilise trois activités :

* A **[!UICONTROL Planificateur]** activité qui exécute le workflow une fois par mois,
* A **[!UICONTROL Code JavaScript]** activité qui génère le rapport au format PDF,
* A **[!UICONTROL Diffusion]** activité référençant le modèle de diffusion créé précédemment.

Pour créer ce workflow, procédez comme suit :

1. Accédez au **[!UICONTROL Administration > Exploitation > Workflows techniques]** de Campaign. Créez un dossier pour stocker vos workflows.
1. Créez un nouveau workflow.

   ![](assets/use_case_report_7.png)

1. Ajoutez tout d&#39;abord une activité de type **[!UICONTROL Planificateur]** et configurez-la pour que le workflow s&#39;exécute le premier lundi de chaque mois.

   ![](assets/use_case_report_9.png)

   Pour plus d&#39;informations sur la configuration du planificateur, consultez la section [Planificateur](scheduler.md).

1. Ajoutez ensuite une activité de type **[!UICONTROL Code JavaScript]**.

   ![](assets/use_case_report_10.png)

   Dans la zone d&#39;édition, saisissez le code suivant :

   ```sql
   var reportName = "indicators";
   var path = "/tmp/indicators.pdf";
   var exportFormat = "PDF";
   var reportURL = "<PUT THE URL OF THE REPORT HERE>";
   var _ctx = <ctx _context="global" _reportContext="deliveryFeedback" />
   var isAdhoc = 0;
   
   xtk.report.export(reportName, _ctx, exportFormat, path, isAdhoc);
   ```


   avec les variables suivantes :

   * **var reportName** : saisissez, entre guillemets, le nom interne du rapport. Dans notre exemple, le nom interne du rapport **Indicateur de tracking** est &quot;deliveryFeedback&quot;.
   * **var path**: saisissez le chemin d’enregistrement du fichier (&quot;tmp&quot;), le nom que vous souhaitez donner au fichier (&quot;deliveryFeedback&quot;) et l’extension du fichier (&quot;.pdf&quot;). Dans ce cas, nous avons utilisé le nom interne comme nom de fichier. Les valeurs doivent être entre guillemets doubles et séparées par le caractère &quot;+&quot;.

      >[!CAUTION]
      >
      >Le fichier doit être enregistré sur le serveur. Vous devez saisir le même chemin et le même nom que dans la variable **[!UICONTROL Général]** de la fenêtre d&#39;édition de l&#39;attachement calculé, comme indiqué [here](#step-2--create-the-delivery-template)).

   * **var exportFormat** : saisissez le format d&#39;export du fichier (&quot;PDF&quot;).
   * **var _ctx** (contexte) : dans notre exemple, nous utilisons le rapport **[!UICONTROL Indicateurs de tracking]** dans son contexte global.

1. Ajoutez enfin une activité de **[!UICONTROL Diffusion]** et choisissez les options suivantes :

   ![](assets/use_case_report_11.png)

   * **[!UICONTROL Diffusion]** : sélectionnez **[!UICONTROL Nouvelle, créée depuis un modèle]**, et sélectionnez le modèle de diffusion créé précédemment.
   * Pour les champs **[!UICONTROL Destinataires]** et **[!UICONTROL Contenu]**, sélectionnez **[!UICONTROL Spécifiés dans la diffusion]**.
   * **[!UICONTROL Action à effectuer]**: select **[!UICONTROL Préparation et démarrage]**.
   * Décochez la case **[!UICONTROL Générer une transition sortante]** et **[!UICONTROL Traiter les erreurs]** options.

1. Enregistrez vos modifications et démarrez le workflow. Le message est envoyé à la liste des destinataires tous les premiers lundis du mois, avec le rapport joint.