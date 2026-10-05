---
product: campaign
title: Validation
description: Validation
feature: Workflows, Approvals
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9e57d21c-ce16-448d-97f1-8c6844acb37b
TQID: 'https://experienceleague.adobe.com/wmqV-ZCTwYaGQHTxIZ3iZpv9cTR4TrGDtXuV-YfF1Io'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ce296ecd-3d06-45ab-83c3-37214e8ce31c
    internal-label: Approvals
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 100%
---
# Validation{#approval}



Une tâche **Validation** requiert la participation d’un opérateur ou d’une opératrice. La personne se voit attribuer une tâche à laquelle elle peut répondre par e-mail, à l’aide de la page web liée dans l’e-mail ou via la console.

## Assignation de la tâche {#task-assignment}

Par défaut, la validation est attribuée à un groupe d’opérateurs et d’opératrices. Ce groupe représente un rôle, par exemple « Groupe de contenus de newsletter » ou « Groupe de ciblage de newsletter ». Chaque opérateur ou opératrice du groupe peut répondre, mais seule la première réponse est prise en compte (sauf en cas de validations multiples).

Au besoin, vous pouvez affecter la tâche de validation à un opérateur unique ou à un ensemble d&#39;opérateurs défini par un filtre.

* Pour sélectionner un opérateur unique, sélectionnez la valeur **[!UICONTROL Opérateur]** dans le champ **[!UICONTROL Type d&#39;affectation]** et sélectionnez l&#39;opérateur concerné dans la liste déroulante du champ **[!UICONTROL Assignation]**.

  ![](assets/s_advuser_validation_box_assign.png)

  >[!CAUTION]
  >
  >Seul l&#39;opérateur sélectionné sera habilité à valider la tâche.

* Vous pouvez définir une requête pour filtrer les opérateurs et opératrices en charge de la validation. Pour cela, sélectionnez la valeur **[!UICONTROL Filtre]** dans le champ **[!UICONTROL Type d’affectation]**, puis cliquez sur le lien **[!UICONTROL Paramètres avancés...]** pour définir les critères de filtrage, comme dans l’exemple ci-dessous :

  ![](assets/s_advuser_validation_box_filter.png)

Dans le cas d&#39;une validation simple, la transition correspondant au choix de l&#39;opérateur est activée et la tâche est terminée : les autres opérateurs ne peuvent plus répondre.

Dans le cas de validations multiples, les transitions correspondant au choix de chaque opérateur ou opératrice sont activées. La tâche est terminée lorsque tous les opérateurs et opératrices du groupe ont répondu ou lorsque la tâche a expiré.

Cette activité n&#39;est pas bloquante et le workflow peut effectuer d&#39;autres traitements dans l&#39;attente d&#39;une réponse.

Un opérateur ou une opératrice peut approuver les tâches qui lui sont affectées à partir de la console cliente. Un opérateur ou une opératrice doté de droits d’administrateur peut visualiser et supprimer les tâches assignées aux opérateurs, mais il n’est pas possible d’y répondre.

La modification du titre ou du corps du message de l&#39;activité n&#39;affecte pas les tâches en cours, en revanche, la modification des choix possibles affecte directement les tâches en cours qui héritent automatiquement de la nouvelle liste de choix.

Les tâches de type **Validation** sont accessibles depuis le noeud **[!UICONTROL Administration > Exploitation > Objets créés automatiquement > Approbations en attente]** : les opérateurs peuvent accéder directement au formulaire de validation depuis cette vue.

![](assets/s_advuser_validation_from_console.png)

## Propriétés {#properties}

Les variables de personnalisation peuvent être utilisées dans le message envoyé aux réviseurs et réviseuses. Elles peuvent être insérées dans le titre ou dans le corps du message.

![](assets/edit_validation.png)

Ce champ **[!UICONTROL Titre]** contient le titre du message : il s’agit de l’objet de l’e-mail envoyé. Le titre, comme le corps du message, sont des modèles JavaScript et peuvent donc contenir des valeurs calculées en fonction du contexte du workflow.

La section inférieure de l’éditeur vous permet de définir la liste des réponses possibles. À chaque réponse correspond une transition. Le nom est l’identifiant interne et le libellé est le texte qui sera affiché dans la liste des choix.

Cliquez sur le lien **[!UICONTROL Paramètres avancés…]** pour sélectionner le modèle de diffusion à utiliser pour informer les opérateurs et opératrices. Le modèle par défaut (nom interne « notifyAssignee ») reprend le titre et le message, et ajoute un lien vers la page web permettant de répondre.

Ce modèle peut être modifié pour personnaliser la mise en page du message, mais il est préférable d’en faire une copie. Le mécanisme de ciblage (fichier externe, mapping de ciblage) ne doit pas être modifié, car il est nécessaire au bon fonctionnement des notifications.

Un exemple de validation est proposé dans la section [Définir les validations](define-approvals.md).

## Paramètres de sortie {#output-parameters}

* **[!UICONTROL response]**

  Commentaire associé à la réponse

* **[!UICONTROL responseOperator]**

  Identifiant de l’opérateur ou opératrice qui a répondu. Ce champ est une valeur numérique, mais un champ **[!UICONTROL Chaîne]**.
