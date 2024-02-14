---
product: campaign
title: Validation
description: Validation
feature: Workflows, Approvals
role: User
exl-id: 9e57d21c-ce16-448d-97f1-8c6844acb37b
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 88%

---

# Validation{#approval}



Une tâche de type **Validation** attend un signal ou une décision d&#39;un opérateur. L&#39;opérateur se voit assigner une tâche à laquelle il peut répondre depuis un email et via le web ou directement depuis la console.

## Assignation de la tâche {#task-assignment}

Par défaut, une validation est assignée à un groupe d&#39;opérateurs. Ce groupe représente un rôle, par exemple &#39;Groupe contenu newsletter&#39; ou &#39;Groupe ciblage newsletter&#39;. Chaque opérateur du groupe peut répondre mais seule la première réponse est prise en compte (sauf en cas de validation multiple).

Au besoin, vous pouvez affecter la tâche de validation à un opérateur unique ou à un ensemble d&#39;opérateurs défini par un filtre.

* Pour sélectionner un opérateur unique, sélectionnez la valeur **[!UICONTROL Opérateur]** dans le champ **[!UICONTROL Type d&#39;affectation]** et sélectionnez l&#39;opérateur concerné dans la liste déroulante du champ **[!UICONTROL Assignation]**.

  ![](assets/s_advuser_validation_box_assign.png)

  >[!CAUTION]
  >
  >Seul l&#39;opérateur sélectionné sera habilité à valider la tâche.

* Vous pouvez définir une requête pour filtrer les opérateurs validants. Pour ce faire, sélectionnez l’option **[!UICONTROL Filtrer]** dans la variable **[!UICONTROL Type d&#39;affectation]** et cliquez sur le champ **[!UICONTROL Paramètres avancés...]** pour définir les conditions de filtrage, comme dans l&#39;exemple ci-dessous :

  ![](assets/s_advuser_validation_box_filter.png)

Dans le cas d&#39;une validation simple, la transition correspondant au choix de l&#39;opérateur est activée et la tâche est terminée : les autres opérateurs ne peuvent plus répondre.

Dans le cas d&#39;une validation multiple, les transitions correspondant au choix de chaque opérateur sont activées. La tâche est terminée lorsque tous les opérateurs du groupe ont répondu ou lorsque la tâche a expiré.

Cette activité n&#39;est pas bloquante et le workflow peut effectuer d&#39;autres traitements dans l&#39;attente d&#39;une réponse.

Un opérateur peut valider les tâches qui lui sont assignées depuis la console cliente. Un opérateur ou une opératrice doté de droits d’administrateur peut visualiser et supprimer les tâches assignées aux opérateurs, mais il n’est pas possible d’y répondre.

La modification du titre ou du corps du message de l&#39;activité n&#39;affecte pas les tâches en cours, en revanche, la modification des choix possibles affecte directement les tâches en cours qui héritent automatiquement de la nouvelle liste de choix.

Les tâches de type **Validation** sont accessibles depuis le noeud **[!UICONTROL Administration > Exploitation > Objets créés automatiquement > Validations en attente]** : les opérateurs peuvent accéder directement au formulaire de validation depuis cette vue.

![](assets/s_advuser_validation_from_console.png)

## Propriétés {#properties}

Les variables de personnalisation peuvent être utilisées dans le message envoyé au(x) validant(s). Elles peuvent être insérées dans le titre ou dans le contenu du message.

![](assets/edit_validation.png)

Le champ **[!UICONTROL Titre]** contient le titre du message : il s’agit de l’objet de l’e-mail envoyé. Le titre, comme le corps du message, sont des modèles JavaScript et peuvent donc contenir des valeurs calculées en fonction du contexte du workflow.

La section inférieure de l&#39;éditeur permet de définir la liste des réponses possibles. A chaque réponse correspond une transition. Le nom est l&#39;identifiant interne et le libellé est le texte qui sera affiché dans la liste des choix.

Cliquez sur le lien **[!UICONTROL Paramètres avancés...]** pour sélectionner le modèle de diffusion à utiliser pour notifier les opérateurs. Le modèle par défaut (nom interne &#39;notifyAssignee&#39;) reprend le titre et le message et ajoute un lien vers la page web permettant de répondre.

Ce modèle peut être modifié pour personnaliser la mise en page du message, mais il est préférable d&#39;en faire une copie. Le mécanisme de ciblage (fichier externe, mapping de ciblage) ne doit pas être modifié car il est nécessaire au bon fonctionnement de la notification.

Un exemple de validation est proposé dans la section [Définir les validations](define-approvals.md).

## Paramètres de sortie {#output-parameters}

* **[!UICONTROL response]**

  Commentaire associé à la réponse

* **[!UICONTROL responseOperator]**

  Identifiant de l&#39;opérateur qui a répondu. Ce champ est une valeur numérique, mais une valeur **[!UICONTROL Chaîne]** champ .
