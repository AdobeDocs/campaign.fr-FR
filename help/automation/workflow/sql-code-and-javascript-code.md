---
product: campaign
title: Code SQL et code JavaScript
description: En savoir plus sur les activités de workflow de code SQL et JavaScript
feature: Workflows
Role: User
level: Experienced
version: Campaign v8, Campaign Classic v7
exl-id: 8c385847-a320-4cd9-9048-2bf9daf2ee07
TQID: https://experienceleague.adobe.com/J1oZUE7vCyJvodf0-09QoG24gWY9P9sSgqsH7rXibgk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 423
ht-degree: 59%

---

# Code SQL et code JavaScript{#sql-code-and-javascript-code}

## Code SQL {#sql-code}

Une activité **[!UICONTROL Code SQL]** exécute un script SQL. Le script est un modèle JST.

![](assets/sql_code.png)

* **[!UICONTROL Script]**

  La zone centrale de l&#39;éditeur contient le script à exécuter. Ce script est un template JST et peut donc être configuré en fonction du contexte du workflow.

* **[!UICONTROL Traiter les erreurs]**

  Pour plus d&#39;informations, consultez la section [Erreurs de traitement](monitor-workflow-execution.md#processing-errors).

### Remarques importantes {#important-notes}

À partir de la version 8.9.1, les activités de workflow **[!UICONTROL Code SQL]** et **[!UICONTROL Gestion des données SQL]** ont été améliorées afin de mieux protéger les bases de données PostgreSQL et de garantir le bon fonctionnement de vos workflows lorsque le code SQL personnalisé est exécuté à partir de Campaign. Voici quelques bonnes pratiques à suivre en cas d’erreur.

Les options sont disponibles sous **[!UICONTROL Administration]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Options]**. Deux solutions sont disponibles en cas d&#39;erreur :

**Solution 1**

Définissez `XtkSecurity_FeatureFlag_SqlSensitive` sur `0`. La fonction est désactivée.

**Solution 2**

Modifiez `XtkSecurity_SqlSensitive_Methods`. Vous pouvez remplacer `<method name="TRUNCATE" action="block"/>` par `<method name="TRUNCATE" action="warn"/>`

D&#39;autres méthodes telles que VACUUM FULL, REINDEX, CREATE INDEX, DROP INDEX sont également bloquées par défaut afin de protéger l&#39;intégrité de la base de données. Soyez prudent si vous souhaitez les définir sur Avertissement plutôt que sur Bloc. Ces méthodes peuvent avoir un impact important sur les performances de la base de données lors de l’exécution.

## Code JavaScript et code JavaScript avancé {#javascript-code}

Les activités **[!UICONTROL Code JavaScript]** et **[!UICONTROL Code JavaScript avancé]** exécutent un script JavaScript dans le cadre d’un workflow. Pour plus d’informations sur les scripts, reportez-vous aux sections suivantes :

* [Scripts et modèles JavaScript](javascript-scripts-and-templates.md)
* [Exemples de code JavaScript dans les workflows](javascript-in-workflows.md)

### Délai d‘exécution {#exec-delay}

À compter de la version 20.2, un délai d‘exécution a été ajouté aux activités **[!UICONTROL code JavaScript]** et **[!UICONTROL code JavaScript avancé]**. Par défaut, la phase d’exécution ne peut pas dépasser 1 heure. Après ce délai, le processus est abandonné avec un message d‘erreur et l‘échec de l’exécution.

Vous pouvez modifier ce délai dans le champ **[!UICONTROL Arrêter l’exécution après]**, disponible dans ces activités.

Pour ignorer cette limite, vous devez définir la valeur sur **0**.

### Code JavaScript {#js-code-desc}

![](assets/javascript_code.png)

* **[!UICONTROL Script]** : la zone centrale de l’éditeur contient le script à exécuter.

* **[!UICONTROL Traiter les erreurs]** : voir la section [Traitement des erreurs](monitor-workflow-execution.md#processing-errors).

### Code JavaScript avancé {#adv-js-code-desc}

![](assets/advanced_javascript_code.png)

* **[!UICONTROL Premier appel]** : la première zone de l’éditeur contient le script à exécuter lors du premier appel.
* **[!UICONTROL Appels suivants]** : la deuxième zone de l’éditeur contient le script à exécuter lors des appels suivants.
* **[!UICONTROL Transitions]** : vous pouvez définir plusieurs transitions en sortie de l’activité.
* **[!UICONTROL Planificateur]**: l’onglet **[!UICONTROL Planning]** permet de planifier le déclenchement de l’activité.

JavaScript avancé est une tâche persistante et est régulièrement rappelé s’il n’a pas été marqué comme terminé. Pour terminer la tâche et empêcher les rappels ultérieurs, vous devez utiliser la méthode **task.setCompleted()** dans la section **[!UICONTROL Appels suivants]** :

```
task.postEvent(task.transitionByName("ok")); // to transition to Ok branch
task.setCompleted();

return 0;
```
