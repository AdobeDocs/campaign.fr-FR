---
product: campaign
title: Journal d’audit
description: Découvrez comment surveiller votre instance à lʼaide du journal dʼaudit Campaign
feature: Audit Trail, Monitoring, Workflows
exl-id: 6a937575-42d4-4dc5-8168-43c25bb2cde6
source-git-commit: b4b361a4aabd1b33554166c2638989b99a02baec
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 100%

---

# Journal d’audit{#audit-trail}

La fonctionnalité **[!UICONTROL Journal d’audit]** d’Adobe Campaign offre un enregistrement granulaire de toutes les modifications apportées à des entités importantes de votre instance, généralement celles qui ont un impact significatif sur le bon fonctionnement de l’instance. Fonctionnant en tant que journal en temps réel, elle capture une liste détaillée des actions et événements au fur et à mesure qu’ils se produisent.

>[!NOTE]
>
>Adobe Campaign n’effectue pas le suivi des modifications apportées aux droits des utilisateurs, aux modèles, aux personnalisations ni aux campagnes.\
>Le journal d’audit peut uniquement être géré par les administrateurs de l’instance.

+++ En savoir plus sur les entités disponibles du journal d’audit

* **Journal d’audit du schéma** : permet d’explorer les modifications apportées à vos schémas, ainsi que d’identifier qui a effectué ces modifications et quand elles ont eu lieu.

  Pour plus d’informations sur les schémas, consultez cette [page](../dev/schemas.md).

* **Journal d’audit des workflows** : effectue le suivi de toutes les actions liées à vos workflows, notamment :

   * Démarrer
   * Pause
   * Arrêter
   * Redémarrer
   * Nettoyer qui correspond à l’action Purge de l’historique
   * Simuler qui correspond à l’action Démarrer en mode simulation
   * Réveiller qui correspond à l’action Traitement anticipé des tâches en attente
   * Arrêt inconditionnel

  Pour plus d’informations sur les workflows, consultez [cette page](../../automation/workflow/about-workflows.md).

  Pour plus d’informations sur la surveillance des workflows, consultez la [section dédiée](../../automation/workflow/monitor-workflow-execution.md).

* **Journal d’audit des options** : permet de vérifier les activités et les dernières modifications apportées à vos options.

  Pour plus d’informations sur les options, consultez [cette page](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options).

* **Journal d’audit des diffusions** : permet de vérifier les activités et les dernières modifications apportées à vos diffusions.

  Pour plus d’informations sur les diffusions, consultez cette [page](../start/create-message.md).

* **Compte externe** : permet de vérifier les modifications apportées aux comptes externes, utilisé par des processus techniques tels que des workflows techniques ou des workflows de campagne.

  Pour plus d’informations sur les comptes externes, consultez cette [page](../config/external-accounts.md).

* **Mapping de diffusion** : permet de surveiller les activités et les modifications récentes apportées à vos mappings de diffusion.

  Pour plus d’informations sur les mappings de diffusion, consultez cette [page](../audiences/target-mappings.md).

* **Application web** : permet de vérifier les modifications apportées aux formulaires web dans Campaign v8 servant à créer des pages avec des champs de saisie et de sélection et pouvant inclure des données de la base de données.

  Pour plus d’informations sur les applications web, consultez cette [page](../dev/webapps.md).

* **Offre** : permet de vérifier les activités et les dernières modifications apportées à vos offres.

  Pour plus d’informations sur l’offre, consultez cette [page](../interaction/interaction.md).

* **Opérateur ou opératrice** : permet de surveiller les activités et les modifications récentes apportées à vos opérateurs et opératrices.

  Pour plus d’informations sur les opérateurs et opératrices, consultez cette [page](../interaction/interaction-operators.md).

+++

## Accéder au journal d’audit {#accessing-audit-trail}

Pour accéder au **[!UICONTROL journal d’audit]** de votre instance, procédez comme suit :

1. Accédez au menu **[!UICONTROL Explorateur]** de votre instance.

1. Sous le menu **[!UICONTROL Administration]**, sélectionnez **[!UICONTROL Audit]**, puis **[!UICONTROL Journal d’audit]**.

   ![](assets/audit-trail-1.png)

1. La fenêtre **[!UICONTROL Journal d’audit]** s’ouvre avec la liste de vos entités. Adobe Campaign effectuera l’audit des actions de création, de modification et de suppression pour vos différentes entités.

   Sélectionnez l’une des entités pour en savoir plus sur les dernières modifications.

1. La fenêtre **[!UICONTROL Entité d’audit]** vous donne des informations plus détaillées sur l’entité choisie, telles que :

   * **[!UICONTROL Type]** : workflow, options, diffusions ou schémas.
   * **[!UICONTROL Entité]** : nom interne de vos activités.
   * **[!UICONTROL Modifié par]** : nom d’utilisateur ou d’utilisatrice de la dernière personne à avoir modifié cette entité.
   * **[!UICONTROL Action]** : dernière action réalisée sur cette entité (création, édition ou suppression).
   * **[!UICONTROL Date de modification]** : date de la dernière action effectuée sur cette entité.

   ![](assets/audit-trail-2.png)

>[!NOTE]
>
>Par défaut, la période de rétention est définie sur 180 jours pour les **[!UICONTROL logs d’audit]**. Cette valeur peut-être modifiée dans l’assistant de déploiement.

## Activer/désactiver le journal d’audit {#enable-disable-audit-trail}

Le journal d’audit peut être facilement activé ou désactivé pour une activité spécifique, par exemple si vous voulez économiser de l’espace sur la base de données.

Pour ce faire :

1. Accédez au menu **[!UICONTROL Explorateur]** de votre instance.

1. Sous le menu **[!UICONTROL Administration]**, sélectionnez **[!UICONTROL Plateforme]**, puis **[!UICONTROL Options]**.

1. Sélectionnez l’une des options suivantes selon l’entité que vous voulez activer/désactiver :

   * Pour un workflow : **[!UICONTROL XtkAudit_Workflows]**
   * Pour un schéma : **[!UICONTROL XtkAudit_DataSchema]**
   * Pour une option : **[!UICONTROL XtkAudit_Option]**
   * Pour les diffusions : **[!UICONTROL XtkAudit_Delivery]**
   * Pour le compte externe : **[!UICONTROL XtkAudit_ExtAccount]**
   * Pour le mapping de diffusion : **[!UICONTROL XtkAudit_DeliveryMapping]**
   * Pour les applications web : **[!UICONTROL XtkAudit_WebApp]**
   * Pour l’offre : **[!UICONTROL XtkAudit_Offer]**
   * Pour l’opérateur : **[!UICONTROL XtkAudit_Operator]**
   * Pour chaque entité : **[!UICONTROL XtkAudit_Enable_All]**

   ![](assets/audit-trail-3.png)

1. Définissez la **[!UICONTROL Valeur]** sur 1 si vous voulez activer l’entité, ou sur 0 si vous voulez la désactiver.

   ![](assets/audit-trail-4.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.
