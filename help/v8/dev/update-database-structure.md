---
solution: Campaign Classic
product: campaign
title: Mettre à jour la structure de la base de données
description: Mettre à jour la structure de la base de données
translation-type: tm+mt
source-git-commit: e509feb4624b26e33d43f2a1d926b563ab52a8c4
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 44%

---

# Mettre à jour la structure de la base de données{#updating-the-database-structure}

Pour appliquer les modifications apportées aux schémas, lancez l&#39;Assistant Mise à jour de la base de données. Cet assistant est accessible via **[!UICONTROL Outils > Avancé > Mettre à jour la structure de base de données]**. Il vérifie si la structure physique de la base de données correspond à sa description logique et exécute les scripts de mise à jour SQL.

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
