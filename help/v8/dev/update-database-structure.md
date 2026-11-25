---
title: Mise à jour de la structure de la base de données
description: Mise à jour de la structure de la base de données
feature: Configuration
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
TQID: 'https://experienceleague.adobe.com/1UBvvvkN-05BqOe4aOMpYFtKEMp0Yf-q9ECtbtmHzb0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 61%
---
# Mise à jour de la structure de la base de données {#updating-the-database-structure}

Pour appliquer les modifications apportées aux schémas, lancez l’Assistant de mise à jour de la base de données. Cet assistant est accessible via **[!UICONTROL Outils > Avancé > Mise à jour de la structure de la base de données]**. Il vérifie que la structure physique de la base de données correspond bien à sa description logique et exécute les scripts de mise à jour SQL.

![Assistant de mise à jour de la base de données : mettez à jour la page des paramètres avec le bouton Suivant pour lancer le processus de découverte automatique](assets/schema_update.png)

Les modules présents dans la base de données sont automatiquement renseignés et activés.

![Assistant de mise à jour de la base de données : page Modifier les tables répertoriant les tables, la table CusContracts étant définie pour se synchroniser](assets/schema_update_select2.png)

Suivez les étapes et visualisez le script SQL de mise à jour de la base de données :

![Assistant de mise à jour de la base de données : page Mettre à jour le script avec le script SQL CREATE TABLE pour CusContracts](assets/schema_update2.png)

>[!NOTE]
>
>Cette zone est en édition et peut être modifiée afin de supprimer ou ajouter du code SQL.

Lancez ensuite la mise à jour de la base de données :

![Assistant de mise à jour de la base de données Démarrez la page de mise à jour de la base de données avec le journal indiquant la mise à jour effectuée à 100 %](assets/schema_update3.png)
