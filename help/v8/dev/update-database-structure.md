---
product: Adobe Campaign
title: Mise à jour de la structure de la base de données
description: Mise à jour de la structure de la base de données
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: ht
source-wordcount: '97'
ht-degree: 100%

---

# Mise à jour de la structure de la base de données{#updating-the-database-structure}

Pour appliquer les modifications apportées aux schémas, lancez l’Assistant de mise à jour de la base de données. Cet assistant est accessible via **[!UICONTROL Outils > Avancé > Mise à jour de la structure de la base de données]**. Il vérifie que la structure physique de la base de données correspond bien à sa description logique et exécute les scripts de mise à jour SQL.

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
