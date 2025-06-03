---
product: campaign
title: Propriétés d’exécution
description: En savoir plus sur les propriétés des workflows de Campaign
feature: Workflows
exl-id: 7fef434e-f6bd-46a4-9ec2-0182f081c928
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 86%

---

# Propriétés d&#39;exécution        {#workflow-properties}

## Onglet Exécution {#execution-tab}

L&#39;onglet **[!UICONTROL Exécution]** de la fenêtre **[!UICONTROL Propriétés]** d&#39;un workflow est organisée en 3 sections :

![](assets/wf_execution_tab.png)

### Planificateur {#scheduler}

Cette section n&#39;apparaît que dans les workflows d&#39;opérations.

* **[!UICONTROL Priorité]**

  Le moteur de workflow traite les workflows à exécuter selon le critère de priorité défini dans ce champ. Par exemple, tous les workflows de priorité **[!UICONTROL moyenne]** sont exécutés avant ceux de priorité **[!UICONTROL faible]**.

* **[!UICONTROL Différer l’exécution vers une plage horaire de faible activité]**

  Cette option reporte le lancement du workflow vers une plage horaire moins chargée. Certains workflows peuvent être très coûteux en termes de ressources pour le moteur de base de données. Il peut donc être utile de décaler l’exécution des workflows moins urgents vers une plage de faible activité (la nuit par exemple). Les plages horaires de faible activité sont définies dans le workflow technique **[!UICONTROL Traitements sur les campagnes]**.

### Exécution {#execution}

* **[!UICONTROL Affinité par défaut]**

  Si votre installation comprend plusieurs serveurs de workflow, utilisez ce champ pour choisir sur quelle machine le workflow s&#39;exécutera. Si la valeur définie dans ce champ n&#39;existe au niveau d&#39;aucun serveur, le workflow restera en attente.

* **[!UICONTROL Jours d&#39;historique]**

  Les tables de travail de la base conservent un historique des exécutions (tâches, évènements, journal). Définissez ici le nombre de jours d&#39;historique que vous voulez conserver pour ce workflow : les processus de nettoyage de la base supprimeront chaque jour les historiques plus anciens. Si la valeur de ce champ est zéro, l&#39;historique ne sera jamais supprimé.

* **[!UICONTROL Enregistrer les requêtes SQL dans le journal]**

  Cette fonctionnalité est réservée aux utilisateurs experts. Elle concerne les workflows qui contiennent des activités de ciblage (requête, union, intersection, etc.). Lorsque cette option est cochée, les requêtes SQL envoyées vers la base lors de l&#39;exécution du workflow sont affichées dans Adobe Campaign : vous pouvez ainsi les analyser afin d&#39;optimiser les requêtes ou diagnostiquer d&#39;éventuels problèmes.

  Les requêtes sont affichées dans un onglet **[!UICONTROL Journaux SQL]** ajouté au workflow (sauf pour les workflows de campagne) et à l’activité **[!UICONTROL Propriétés]** lorsque l’option est activée. L’onglet **[!UICONTROL Audit]** comprend également des requêtes SQL.

  ![](assets/wf_tab_log_sql.png)

* **[!UICONTROL Exécuter dans le moteur]**

  Cette option ne doit être utilisée qu&#39;à des fins de débuggage et jamais en production. Lorsque cette option est activée, le workflow devient prioritaire, et tous les autres workflows sont stoppés par le moteur de workflow tant qu&#39;il n&#39;est pas terminé.

* **[!UICONTROL Autorisez le superviseur watchdog à maintenir le workflow en cours d&#39;exécution de manière permanente]**

  Cette option force le redémarrage automatique des workflows en cas d’erreur. Lorsqu’il est activé, le redémarrage vérifie toutes les 30 secondes le statut du workflow et le redémarre si nécessaire. Pour ajuster l’intervalle de 30 secondes, vous pouvez créer l’option technique `XtkWorkflow_WatchdogRestartTimerTimeout` et utiliser un type de données entier pour spécifier le délai souhaité.

  >[!NOTE]
  >
  >* Cette option est disponible à partir de la version 8.6.4.
  >
  >* Cette option est destinée aux utilisateurs avancés et ne doit être activée que pour les **workflows techniques**.
  >
  >* Cette option est activée par défaut pour les workflows de réplication centralisée disponibles dans un déploiement [ Entreprise (FFDA)](../../v8/architecture/enterprise-deployment.md). [En savoir plus](../../v8/architecture/replication.md)

### Gestion des erreurs {#error-management}

* **[!UICONTROL Résolution des problèmes]**

  Ce champ vous permet de définir l&#39;action à effectuer lorsqu&#39;une tâche du workflow est en erreur. Deux options sont disponibles :

   * **[!UICONTROL Arrêter le processus]** : le workflow est automatiquement mis en pause. Sinon, le statut du workflow devient **[!UICONTROL Échec]**. Une fois le problème résolu, redémarrez le workflow à l’aide des boutons **[!UICONTROL Démarrer]** ou **[!UICONTROL Redémarrer]**.
   * **[!UICONTROL Ignorer]** : la tâche ayant provoqué l&#39;erreur prend le statut **[!UICONTROL En échec]**, mais le workflow garde le statut **[!UICONTROL Démarré]**. Ce paramétrage est pertinent dans le cas de tâches récurrentes : si la branche comporte un planificateur, celui-ci se déclenchera normalement à sa prochaine date d&#39;exécution.

* **[!UICONTROL Erreurs consécutives]**

  Ce champ devient disponible lorsque la valeur **[!UICONTROL Ignorer]** est sélectionnée dans le champ **[!UICONTROL En cas d’erreur]**. Vous pouvez spécifier le nombre d’erreurs qui peuvent être ignorées avant l’arrêt du processus. Une fois ce nombre atteint, le statut du workflow passe à **[!UICONTROL Échec]**. Si la valeur de ce champ est 0, le workflow ne sera jamais arrêté, quel que soit le nombre d’erreurs.

* **[!UICONTROL Template]**

  Dans ce champ, choisissez le modèle de notification à envoyer au groupe de supervision du workflow lorsque celui-ci passe sur **[!UICONTROL En échec]**.

  Les opérateurs et opératrices recevront un e-mail, à l’adresse indiquée dans leur profil, le cas échéant. Pour définir les responsable des workflows, accédez au champ **[!UICONTROL Personnes chargées de la supervision]** de l’onglet **[!UICONTROL Général]** des propriétés.

  ![](assets/wf-properties_select-supervisors.png)

  Le modèle par défaut **[!UICONTROL Notification du responsable d’un workflow]** comprend un lien qui permet d’accéder via le Web à la console cliente Adobe Campaign et, après connexion, d’agir sur le workflow en erreur.

  Vous pouvez créer un modèle personnalisé dans **[!UICONTROL Administration > Gestion de campagne > Modèles et diffusions techniques]**.
