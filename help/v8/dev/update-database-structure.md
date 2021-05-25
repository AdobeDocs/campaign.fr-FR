---
solution: Campaign v8
product: Adobe Campaign
title: Mettre à jour la structure de la base de données
description: Mettre à jour la structure de la base de données
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 44%

---

# Mettre à jour la structure de la base{#updating-the-database-structure}

Pour appliquer les modifications apportées aux schémas, lancez l&#39;assistant Mise à jour de la base . Cet assistant est accessible via **[!UICONTROL Outils > Avancé > Mettre à jour la structure de la base de données]** . Il vérifie si la structure physique de la base de données correspond à sa description logique et exécute les scripts SQL de mise à jour.

![](assets/schema_update.png)

Les modules présents dans la base de données sont automatiquement renseignés et activés.

![](assets/schema_update_select2.png)

Suivez les étapes et visualisez le script SQL de mise à jour de la base de données :

![](assets/schema_update2.png)

>[!NOTE]
>
>Cette zone est en édition et peut être modifiée afin de supprimer ou ajouter du code SQL.

Lancez ensuite la mise à jour de la base de données :

![](assets/schema_update3.png)
