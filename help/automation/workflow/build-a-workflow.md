---
product: campaign
title: Création d’un workflow
description: Découvrez comment créer un workflow
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
TQID: https://experienceleague.adobe.com/EzHUErLy7-OcfF0lxH4UHXm1N1HYGt6kP9Io1LIyJi4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 875
ht-degree: 87%

---

# Création d’un workflow {#build-a-workflow}

## Création dʼun workflow {#create-a-new-workflow}

Le flux de création de workflow dépend du type de workflow. Vous pouvez ainsi :

* Créer des [workflows de ciblage](#targeting-workflows) à partir du nœud **[!UICONTROL Profils et cibles]** > **[!UICONTROL Traitements]** > **[!UICONTROL Workflows de ciblage]** de l’Explorateur ou de l’onglet **[!UICONTROL Profils et cibles]** de la page d’accueil, via le sous-onglet **[!UICONTROL Workflows de ciblage]**.

  ![](assets/create-targeting-wf.png)

* Créer des [workflows de campagne](#campaign-workflows) à partir de l&#39;onglet **[!UICONTROL Ciblage et workflows]** d&#39;une campagne.

* Créer des [workflows techniques](#technical-workflows) à partir du nœud **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Workflows techniques]** de l&#39;Explorateur. Il est pratique de créer un dossier de workflow spécifique pour enregistrer vos workflows techniques.

Pour créer un workflow, cliquez sur le bouton **[!UICONTROL Nouveau]** situé au-dessus de la liste des workflows.

![](assets/create_a_wf_icon.png)

Saisissez un libellé puis cliquez sur **[!UICONTROL Enregistrer]**.

## Ajout et liaison dʼactivités {#add-and-link-activities}

Vous devez maintenant définir les différentes activités et les relier entre elles dans un diagramme. À ce stade de la configuration, nous pouvons voir le libellé du diagramme et le statut du workflow (Modification en cours). La section inférieure de la fenêtre est utilisée uniquement pour modifier le diagramme. Il contient une barre d&#39;outils, une palette d&#39;activités (à gauche) et le diagramme lui-même (à droite).

![](assets/new-workflow-2.png)

>[!NOTE]
>
>Si la palette n&#39;est pas visible, cliquez sur le premier bouton de la barre d&#39;outils de workflow pour qu&#39;elle s&#39;affiche.

Les activités sont regroupées par catégories sous les onglets de la palette. Les onglets et activités disponibles peuvent varier en fonction du type de workflow (technique, de ciblage ou workflow de campagne).

* Le premier onglet contient les activités de ciblage et de manipulation de données. Ces activités sont détaillées dans la section [Activités de ciblage](targeting-activities.md).
* Le deuxième Onglet contient les activités de planification qui servent principalement à coordonner les autres. Elles sont détaillées dans la section [Activités d&#39;ordonnancement](flow-control-activities.md).
* Le troisième onglet contient les outils et les actions utilisables dans le workflow. Ces activités sont décrites en détail dans la section [Activités d&#39;action](action-activities.md).
* Le quatrième onglet regroupe les activités qui dépendent d&#39;un événement particulier, par exemple la réception d&#39;un email ou l&#39;arrivée d&#39;un fichier sur un serveur. Ces activités sont décrites en détail dans la section [Activités événementielles](event-activities.md).

Pour construire le diagramme

1. Ajoutez une activité en la sélectionnant dans la palette et en la déplaçant jusqu&#39;au diagramme par un glisser-déposer.

   Positionnez une activité de type **Début**, puis une activité de type **Diffusion** sur le diagramme.

   ![](assets/new-workflow-3.png)

1. Reliez les deux activités en sélectionnant la transition de l&#39;activité **Début** et en la relâchant sur l&#39;activité **Diffusion**.

   ![](assets/new-workflow-4.png)

   Vous pouvez relier automatiquement une activité à celle qui la précède en déposant la nouvelle activité directement sur l&#39;extrémité de la transition.

1. Ajoutez les activités dont vous avez besoin et reliez-les entre elles, comme sur le diagramme ci-dessous.

   ![](assets/new-workflow-5.png)

>[!CAUTION]
>
>Vous pouvez copier et coller des activités dans un même workflow. Toutefois, nous vous déconseillons de copier et coller des activités dans différents workflows. Certains paramètres associés à des activités telles que Diffusions et Planificateur peuvent entraîner des conflits et des erreurs lors de l&#39;exécution du workflow de destination. Nous vous recommandons plutôt de **dupliquer** les workflows. Pour plus dʼinformations, consultez la section [Duplication des workflows](#duplicate-workflows).

Lʼaffichage et la mise en page du diagramme peuvent être modifiés à lʼaide des éléments suivants :

* **Utilisation de la barre d’outils**

  La barre d&#39;outils de l&#39;éditeur de diagramme permet d&#39;accéder aux fonctions de mise en page et d&#39;exécution du workflow.

  ![](assets/wf-toolbar.png)

  Vous pouvez ainsi adapter la mise en page de l&#39;éditeur : affichage de la palette et de la vue d&#39;ensemble, taille et alignement des objets graphiques.

  ![](assets/s_user_segmentation_toolbar.png)

  Les icônes relatives à la progression et l’affichage des logs sont présentées en détail dans les sections suivantes :

   * [Afficher la progression](monitor-workflow-execution.md#displaying-progress)
   * [Afficher les logs](monitor-workflow-execution.md#displaying-logs)

* **Alignement des objets**

  Pour aligner les icônes, sélectionnez-les et cliquez sur l&#39;icône **[!UICONTROL Aligner verticalement]** ou **[!UICONTROL Aligner horizontalement]**.

  Utilisez la touche **CTRL** pour sélectionner plusieurs activités dispersées ou pour désélectionner une ou plusieurs activités. Cliquez sur l’arrière-plan du diagramme pour tout désélectionner.

* **Gestion des images**

  Vous pouvez personnaliser l’image d’arrière-plan du diagramme et les images associées aux différentes activités. Consultez la section [Modification des images dʼactivité](change-activity-images.md).

## Configuration des activités {#configure-activities}

Double-cliquez sur une activité pour la paramétrer ou cliquez avec le bouton droit et choisissez **[!UICONTROL Ouvrir…]**.

>[!NOTE]
>
>Les activités de workflow d’opérations disponibles sont présentées dans [cette section](activities.md).

Le premier onglet contient le paramétrage de base. L’onglet **[!UICONTROL Avancé]** contient des paramètres supplémentaires, qui permettent notamment de définir le comportement en cas d’erreur ainsi que la durée d’exécution de l’activité, et de saisir un script d’initialisation.

Pour une meilleure compréhension des activités et une meilleure lisibilité des workflows, vous pouvez saisir des commentaires dans les activités.

![](assets/example1-comment.png)

Ces commentaires s&#39;afficheront automatiquement quand des opérateurs balayeront du curseur l&#39;activité.

![](assets/example2-comment.png)


## Les modèles de workflows {#workflow-templates}

Les modèles de workflow contiennent la configuration globale des propriétés et éventuellement une plage d’activités concaténées dans un diagramme. Cette configuration peut être réutilisée pour créer de nouveaux workflows contenant un certain nombre d&#39;éléments préconfigurés

Vous pouvez créer de nouveaux modèles de workflows à partir de modèles existants ou transformer directement un workflow en modèle.

Les modèles de workflows sont stockés dans le nœud **[!UICONTROL Ressources > Modèles > Modèles de workflow]** de l&#39;Explorateur.

En plus des propriétés habituelles des workflows, les propriétés du modèle permettent d&#39;indiquer le dossier d&#39;exécution des workflows créés à partir de ce modèle.

![](assets/wf-template-properties.png)

## Duplication de workflows {#duplicate-workflows}

Vous pouvez dupliquer différents types de workflows. Une fois le workflow dupliqué, ses modifications ne sont pas appliquées à la copie de celui-ci.

Adobe recommande de dupliquer un workflow plutôt que d’effectuer un copier/coller d’activités. Lorsqu’une activité est copiée, tous ses paramètres sont conservés. Pour les activités de canal, l’objet de diffusion associé à l’activité est également copié, ce qui peut entraîner des problèmes majeurs.

1. Cliquez avec le bouton droit de la souris sur un workflow.
1. Cliquez sur **Dupliquer**.

   ![](assets/duplicate-workflows.png)

1. Dans la fenêtre du workflow, modifiez le libellé du workflow.
1. Cliquez sur **Enregistrer**.

