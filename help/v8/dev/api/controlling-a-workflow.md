---
title: Contrôle d’un workflow
description: Découvrez comment contrôler un workflow à l’aide des API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 100%

---

# Contrôle d&#39;un workflow {#controlling-a-workflow}

Vous pouvez contrôler un workflow directement à partir de l’API REST, par le biais d’une requête POST contenant l’identifiant du workflow et la commande d’exécution requise :

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Si l’identifiant du workflow est modifié dans Adobe Campaign, la requête d’API ne fonctionnera plus.

Quatre commandes d’exécution sont disponibles pour contrôler un workflow :

* Démarrer
* Pause
* Reprendre
* Arrêter

Pour plus d’informations sur les commandes d’exécution, reportez-vous à la [documentation de Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html?lang=fr).

<br/>

***Exemples de demande***

* Démarrer un workflow.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"start"}'
  ```

  <!-- + réponse -->

* Arrêter un processus.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"stop"}'
  ```

  <!-- + réponse -->
