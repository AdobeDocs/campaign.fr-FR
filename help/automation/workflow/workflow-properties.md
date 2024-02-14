---
product: campaign
title: Propriétés d’exécution
description: En savoir plus sur les propriétés des workflows de Campaign
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 60%

---

# Propriétés d&#39;exécution        {#workflow-properties}



## Onglet Exécution {#execution-tab}

L&#39;onglet **[!UICONTROL Exécution]** de la fenêtre **[!UICONTROL Propriétés]** d&#39;un workflow est organisée en 3 sections :

![](assets/wf_execution_tab.png)

### Planificateur {#scheduler}

Cette section n&#39;apparaît que dans les workflows d&#39;opérations.

* **[!UICONTROL Priorité]**

  Le moteur de workflow traite les workflows à exécuter selon le critère de priorité défini dans ce champ. Par exemple, tous les workflows avec une **[!UICONTROL Moyenne]** La priorité est exécutée avant celles qui comportent une **[!UICONTROL Faible]** priorité.

* **[!UICONTROL Différer l&#39;exécution vers une plage horaire de faible activité]**

  Cette option reporte le démarrage du workflow à une période moins chargée. Certains workflows peuvent être coûteux en termes de ressources pour le moteur de base de données. Nous vous recommandons de planifier l&#39;exécution pour une période de faible activité (la nuit par exemple). Les périodes de faible activité sont définies dans la variable **[!UICONTROL Traitements sur les opérations]** workflow technique.

### Exécution {#execution}

* **[!UICONTROL Affinité par défaut]**

  Si votre installation comprend plusieurs serveurs de workflow, utilisez ce champ pour choisir sur quelle machine le workflow s&#39;exécutera. Si la valeur définie dans ce champ n&#39;existe au niveau d&#39;aucun serveur, le workflow restera en attente.

* **[!UICONTROL Jours d&#39;historique]**

  Les tables de travail de la base conservent un historique des exécutions (tâches, évènements, journal). Définissez ici le nombre de jours d&#39;historique que vous voulez conserver pour ce workflow : les processus de nettoyage de la base supprimeront chaque jour les historiques plus anciens. Si la valeur de ce champ est zéro, l&#39;historique ne sera jamais supprimé.

* **[!UICONTROL Enregistrer les requêtes SQL dans le journal]**

  Cette fonctionnalité est réservée aux utilisateurs experts. Elle concerne les workflows qui contiennent des activités de ciblage (requête, union, intersection, etc.). Lorsque cette option est cochée, les requêtes SQL envoyées vers la base lors de l&#39;exécution du workflow sont affichées dans Adobe Campaign : vous pouvez ainsi les analyser afin d&#39;optimiser les requêtes ou diagnostiquer d&#39;éventuels problèmes.

  Les requêtes s’affichent dans une **[!UICONTROL Journaux SQL]** de l&#39;onglet qui est ajouté au workflow (à l&#39;exception des workflows d&#39;opération) et au **[!UICONTROL Propriétés]** lorsque l’option est activée. La variable **[!UICONTROL Audit]** comprend également des requêtes SQL.

  ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL Exécuter dans le moteur]**

  Cette option ne doit être utilisée qu&#39;à des fins de débuggage et jamais en production. Lorsque cette option est activée, le workflow devient prioritaire, et tous les autres workflows sont stoppés par le moteur de workflow tant qu&#39;il n&#39;est pas terminé.

### Gestion des erreurs        {#error-management}

* **[!UICONTROL Résolution des problèmes]**

  Ce champ vous permet de définir l&#39;action à effectuer lorsqu&#39;une tâche du workflow est en erreur. Deux options sont disponibles :

   * **[!UICONTROL Arrêter le processus]**: le workflow est automatiquement suspendu. le statut du workflow passe à **[!UICONTROL En échec]**. Une fois le problème résolu, redémarrez le workflow à l’aide de la fonction **[!UICONTROL Début]** ou **[!UICONTROL Redémarrer]** des boutons.
   * **[!UICONTROL Ignorer]** : la tâche ayant provoqué l&#39;erreur prend le statut **[!UICONTROL En échec]**, mais le workflow garde le statut **[!UICONTROL Démarré]**. Ce paramétrage est pertinent dans le cas de tâches récurrentes : si la branche comporte un planificateur, celui-ci se déclenchera normalement à sa prochaine date d&#39;exécution.

* **[!UICONTROL Erreurs consécutives]**

  Ce champ devient disponible lorsque la variable **[!UICONTROL Ignorer]** est sélectionnée dans la variable **[!UICONTROL En cas d&#39;erreur]** champ . Vous pouvez spécifier le nombre d’erreurs qui peuvent être ignorées avant l’arrêt du processus. Une fois ce nombre atteint, le statut du workflow passe à **[!UICONTROL Échec]**. Si la valeur de ce champ est 0, le workflow ne sera jamais arrêté, quel que soit le nombre d’erreurs.

* **[!UICONTROL Template]**

  Dans ce champ, choisissez le modèle de notification à envoyer au groupe de supervision du workflow lorsque celui-ci passe sur **[!UICONTROL En échec]**.

  Les opérateurs concernés seront notifiés par email, s&#39;ils possèdent une adresse email dans leur profil. Pour définir les superviseurs de workflow, accédez à la **[!UICONTROL Superviseurs]** champ des propriétés (**[!UICONTROL Général]** ).

  ![](assets/wf-properties_select-supervisors.png)

  La variable **[!UICONTROL Notification du responsable d&#39;un workflow]** le modèle par défaut comprend un lien permettant d&#39;accéder à la console cliente Adobe Campaign via le Web afin que le destinataire puisse travailler sur le problème une fois connecté.

  Vous pouvez créer un modèle personnalisé dans **[!UICONTROL Administration > Gestion de campagne > Modèles et diffusions techniques]**.
