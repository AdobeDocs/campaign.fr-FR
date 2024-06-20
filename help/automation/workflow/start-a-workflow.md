---
product: campaign
title: Démarrer un workflow
description: Découvrez comment démarrer un workflow et la barre d’outils des actions de workflows ainsi que le menu contextuel
feature: Workflows
level: Beginner
role: User, Admin
exl-id: 6d9789e3-d721-4ffd-b3fb-a0c522ab1c0a
source-git-commit: ab6c16af7652f2e8dbfa5c899c2152cefb7fc7c6
workflow-type: tm+mt
source-wordcount: '1209'
ht-degree: 94%

---

# Démarrer, mettre en pause et arrêter un workflow {#starting-a-workflow}

Un workflow est toujours démarré manuellement. Au démarrage, il peut toutefois rester inactif en fonction des informations spécifiées par le biais d&#39;un planificateur (voir [Planificateur](scheduler.md)) ou d&#39;une planification d&#39;activité.

Les actions liées à l&#39;exécution du workflow de ciblage (lancement, arrêt, pause, etc.) sont des processus **asynchrones** : la commande est enregistrée et est effective dès que le serveur est disponible pour l’appliquer.

La barre d&#39;outils permet de lancer et suivre l&#39;exécution du workflow.

La liste des options disponibles dans le menu **[!UICONTROL Actions]** et le menu contextuel sont présentées dans les sections suivantes.

>[!IMPORTANT]
>
>Gardez à l&#39;esprit que, lorsqu&#39;un opérateur exécute une action sur un workflow (démarrer, arrêter, mettre en pause, etc.), l&#39;action n&#39;est pas exécutée immédiatement, mais placée dans une file d&#39;attente pour être traitée par le module de workflow.

## Barre d&#39;outils des actions {#actions-toolbar}

Le bouton **[!UICONTROL Actions]** de la barre d’outils permet d’accéder à des options d’exécution supplémentaires sur les workflows sélectionnés. Vous pouvez également utiliser le menu **[!UICONTROL Fichier > Actions]** ou cliquez avec le bouton droit de la souris sur un workflow et sélectionnez **[!UICONTROL Actions]**.

![](assets/purge_historique.png)

* **[!UICONTROL Début]**

  Cette action permet de lancer l&#39;exécution d&#39;un workflow : un workflow **Terminé**, **En édition** ou **En pause** passe alors en état **Démarré**. Le moteur de workflow va prendre en charge l&#39;exécution de ce workflow. Si le workflow était en pause, il s&#39;agit d&#39;une reprise, sinon il s&#39;agit d&#39;un démarrage et les activités initiales sont alors activées.

  Le démarrage est un processus asynchrone : la demande est enregistrée et sera traitée dès que possible par un serveur de workflow.

* **[!UICONTROL Pause]**

  Cette action a pour effet de passer le workflow **En pause**. Aucune activité ne sera activée jusqu&#39;à la prochaine reprise mais les opérations en cours ne seront pas suspendues.

* **[!UICONTROL Stopper]**

  Cette action arrête un workflow en cours d’exécution. Le statut de l’instance est défini sur **Terminé**. Les opérations en cours sont interrompues, si possible. Les imports et requêtes SQL sont immédiatement annulés.

  >[!IMPORTANT]
  >
  >L’arrêt d’un workflow suit un processus asynchrone : la demande est enregistrée, puis le ou les serveurs de workflow annulent les opérations en cours. L’arrêt d’une instance de workflow peut donc prendre du temps, surtout si le workflow est exécuté sur plusieurs serveurs, car chacun d’eux doit alors prendre le contrôle pour annuler les tâches en cours. Pour éviter tout problème, attendez que l’opération d’arrêt soit terminée et n’effectuez pas plusieurs demandes d’arrêt sur le même workflow.

* **[!UICONTROL Arrêt inconditionnel]**

  Lorsque cette option est sélectionnée, l&#39;état du workflow passe à **[!UICONTROL Terminé]**. Cette action ne doit être utilisée qu&#39;en dernier recours, lorsqu&#39;un arrêt normal ne fonctionne pas après plusieurs minutes. N&#39;utilisez l&#39;arrêt inconditionnel que si vous êtes sûr qu&#39;il n&#39;y a aucun traitement réel en cours sur le workflow.

  >[!CAUTION]
  >
  >Cette option est réservée à un utilisateur expert.

* **[!UICONTROL Redémarrer]**

  Cette action consiste à arrêter puis démarrer un workflow. Dans la plupart des cas, elle permet de redémarrer plus vite. Elle est également utile pour automatiser le redémarrage lorsque l&#39;arrêt prend un certain temps : en effet la commande &#39;Démarrer&#39; n&#39;est disponible que lorsque l&#39;arrêt est effectif.

  Notez que la variable **Redémarrer** L’action n’efface pas les variables d’instance de workflow par rapport à **Exécution**, **Arrêter**, et **Début** actions (l’effacement des variables d’instance survenant lors de l’action Démarrer). Lors du redémarrage d’un workflow, les variables d’instance peuvent toujours être utilisées avec des valeurs conservées. Pour les effacer, vous pouvez effectuer l’une des opérations suivantes :
   * Effectuer **Arrêter** et **Début** actions.
   * Ajoutez le code JavaScript ci-dessous à la fin de l’exécution de votre workflow :

     ```
     var wkf = xtk.workflow.load(instance.id)
     wkf.variables='<variables/>'
     wkf.save()
     ```

* **[!UICONTROL Purge de l&#39;historique]**

  Cette action vous permet de purger l&#39;historique du workflow. Pour plus d&#39;informations, consultez la section [Purger l&#39;historique](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Démarrer en mode simulation]**

  Cette option permet de lancer le workflow en mode simulation et non en mode réel. Cela signifie que lorsque vous activez ce mode, seules les activités qui n&#39;ont pas d&#39;impact sur la base de données ou le système de fichiers sont exécutées (par exemple : **[!UICONTROL Requête]**, **[!UICONTROL Union]**, **[!UICONTROL Intersection]**, etc.). Les activités qui ont un impact (par exemple, **[!UICONTROL Exporter]**, **[!UICONTROL Importer]**, etc.) ainsi que celles qui les suivent (dans la même branche) ne sont pas exécutées.

* **[!UICONTROL Traitement anticipé des tâches en attente]**

  Cette action permet de lancer dès que possible toutes les tâches en attente. Si vous souhaitez lancer une tâche particulière, cliquez avec le bouton droit sur l&#39;activité correspondante et sélectionnez **[!UICONTROL Traitement anticipé de la (des) tâche(s)]**.


* **[!UICONTROL Sauver comme modèle]**

  Cette action crée un nouveau modèle de workflow à partir du workflow sélectionné. Vous devez indiquer son dossier d&#39;enregistrement (dans le champ **[!UICONTROL Dossier]**).


## Bonnes pratiques relatives à l’exécution des workflows {#workflow-execution-best-practices}

Améliorez la stabilité de votre instance en implémentant les bonnes pratiques suivantes :

* **Ne planifiez pas l’exécution d’un workflow à une fréquence supérieure à toutes les 15 minutes**, car cela peut nuire aux performances générales du système et créer des blocs dans la base de données.

* **Évitez de laisser vos workflows en pause**. Si vous créez un workflow temporaire, assurez-vous qu’il se terminera correctement et qu’il ne restera pas dans l’état **[!UICONTROL en pause]**. S’il est en pause, cela signifie que vous devez conserver les tables temporaires et ainsi augmenter la taille de la base de données. Affectez des superviseurs dans les propriétés du workflow pour envoyer une alerte en cas d’échec ou de suspension d’un workflow par le système.

  Pour éviter que les workflows soient dans un état en pause :

   * Vérifiez vos workflows régulièrement pour vous assurer qu&#39;il n&#39;y a pas d&#39;erreurs inattendues.
   * Faites en sorte que vos workflows soient aussi simples que possible, en fractionnant par exemple les workflows volumineux en plusieurs workflows différents. Vous pouvez utiliser des activités **[!UICONTROL Signal externe]** pour déclencher leur exécution selon celle d&#39;autres workflows.
   * Évitez de conserver dans vos workflows des activités désactivées contenant des flux. Cette situation conduit à maintenir des threads ouverts et de nombreuses tables temporaires qui consomment beaucoup d’espace. Ne conservez pas, dans vos workflows, des activités se trouvant dans les états **[!UICONTROL Ne pas activer]** ou **[!UICONTROL Activer, mais ne pas exécuter]**.

* **Arrêtez les workflows qui ne sont pas utilisés**. En continuant à s’exécuter, ils maintiennent les connexions avec la base de données.

* **N’utilisez l’arrêt inconditionnel quʼavec une extrême parcimonie**. Cette action ne doit pas être appliquée régulièrement. Une fermeture incorrecte des connexions générées par les workflows vers la base de données nuit aux performances.

* **N’effectuez pas plusieurs demandes d’arrêt sur le même workflow**. L’arrêt d’un workflow suit un processus asynchrone : la demande est enregistrée, puis le ou les serveurs de workflow annulent les opérations en cours. L’arrêt d’une instance de workflow peut donc prendre du temps, surtout si le workflow est exécuté sur plusieurs serveurs, car chacun d’eux doit alors prendre le contrôle pour annuler les tâches en cours. Pour éviter tout problème, attendez que l’opération d’arrêt soit terminée et évitez d’arrêter un workflow à de multiples reprises.

## Menu contextuel {#right-click-menu}

Lorsqu&#39;une ou plusieurs activités d&#39;un workflow sont sélectionnées, vous pouvez cliquer avec le bouton droit de la souris afin d&#39;agir sur votre sélection.

![](assets/contextual_menu.png)

Les options disponibles dans le menu contextuel sont les suivantes :

**[!UICONTROL Ouvrir :]** cette option permet d&#39;accéder aux propriétés de l&#39;activité.

**[!UICONTROL Afficher le journal :]** cette option permet de visualiser le journal d&#39;exécution des tâches de l&#39;activité sélectionnée. Pour plus d&#39;informations, consultez la section [Afficher le journal](monitor-workflow-execution.md#displaying-logs).

**[!UICONTROL Traitement anticipé de la (des) tâche(s) :]** cette action permet de lancer dès que possible la ou les tâches en attente de l&#39;activité.

**[!UICONTROL Redémarrage du workflow à partir d&#39;une tâche :]** cette option permet de redémarrer le workflow en utilisant les résultats précédemment stockés pour cette activité.

**[!UICONTROL Couper/Copier/Coller/Supprimer :]** ces options permettent de couper, copier, coller et supprimer les activités.

**[!UICONTROL Copier en tant qu&#39;image :]** cette option permet d&#39;effectuer une capture d&#39;écran de l&#39;ensemble des activités.

**[!UICONTROL Exécution normale / Activer mais ne pas exécuter / Ne pas activer :]** ces options sont également disponibles dans l&#39;onglet **[!UICONTROL Avancé]** des propriétés de l&#39;activité. Elles sont présentées dans la section [Exécution](advanced-parameters.md#execution).

**[!UICONTROL Enregistrer/Annuler :]** permet d&#39;enregistrer ou d&#39;annuler les modifications effectuées sur le workflow.

>[!NOTE]
>
>Vous pouvez sélectionner un groupe d&#39;activités pour leur appliquer une de ces commandes.

