---
title: Points d’entrée
description: En savoir plus sur les points d’entrée des API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
TQID: https://experienceleague.adobe.com/1ajh28ZpUsuyTh-qHnto3GsH4J25WSsyK7TqTjlhHfg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 100%

---

# Points d’entrée {#endpoints}

Points d’entrée disponibles des API REST d’Adobe Campaign :

* **/profileAndServices** : permet d’interagir avec les champs d’usine. Les champs étendus ne sont pas accessibles par ce point d’entrée.
* **/profileAndServicesExt** : permet d’interagir avec les champs personnalisés ajoutés lors de l’extension des ressources personnalisées Profile ou Services. Pour plus d’informations sur les ressources personnalisées, reportez-vous à [cette section](custom-resources.md).
* **/&lt;transactionalAPI>** : permet d’interagir avec l’API des messages transactionnels (le nom du point d’entrée de l’API des messages transactionnels dépend de la configuration de votre instance). Pour plus d’informations, consultez [cette section](managing-transactional-messages.md).
* **/workflow/exécution** : permet d’interagir avec les workflows. Pour plus d’informations, consultez [cette section](controlling-a-workflow.md).

Par défaut, les principales ressources disponibles pour les API **profileAndServices** et **profileAndServicesExt** sont les suivantes :

* **/profile** : permet d’interagir avec les profils issus de la base de données Campaign. Pour ajouter des profils à un service, utilisez le point d’entrée **/service**. Pour plus d’informations sur les profils dans Campaign, reportez-vous à la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/audiences/using/about-profiles.html).
* **/service** : permet de gérer les services d’abonnement. Pour plus d’informations sur les services dans Campaign, reportez-vous à la [documentation de Campaign](https://helpx.adobe.com/fr/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Toutes les autres ressources étendues ou créées sont exclusivement disponibles via l’API **ProfileAndServicesExt**. Elles doivent être liées à la ressource **Profile** pour être accessibles.
