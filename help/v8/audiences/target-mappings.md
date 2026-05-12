---
title: Utiliser les mappings de ciblage
description: Découvrez comment utiliser et créer des mappings de ciblage
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
exl-id: 5256fc15-1878-4064-9c75-7876a3826b83
TQID: https://experienceleague.adobe.com/ArJJi775HkzlpPOu-SoKg8UTcYTperTC1ySmXrHHpJg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 100%

---

# Utiliser les mappings de ciblage{#gs-target-mappings}

Par défaut, les modèles de diffusion par e-mail et SMS ciblent les **[!UICONTROL destinataires]**. Leur mapping de ciblage utilise donc les champs de la table **nms:recipient**.

Pour les notifications push, le mapping de ciblage par défaut est **Applications abonnées (nms:appSubscriptionRcp)**, qui est lié à la table des personnes destinataires.

Vous pouvez utiliser d’autres mappings de ciblage pour vos diffusions ou créer un nouveau mapping de ciblage.

## Mappings de ciblage intégrés {#ootb-mappings}

Adobe Campaign est fourni avec les mappings de ciblage intégrés suivants :

| Nom | Utilisation | Schéma |
|---|---|---|
| Destinataires | Diffuser aux destinataires (tableau de destinataires intégré) | nms:recipient |
| Visiteurs et visiteuses | Diffuser aux visiteurs dont les profils ont été collectés par le biais d’une recommandation (marketing viral), par exemple. | mns:visitor |
| Abonnements | Diffuser aux destinataires abonnés à un service d&#39;information, par exemple une newsletter | nms:subscription |
| Abonnements des visiteurs et visiteuses | Diffuser à des visiteurs abonnés à un service d&#39;information | nms:visitorSub |
| Les opérateurs | Diffuser aux opérateurs Adobe Campaign | nms:operator |
| Fichier externe | Diffuser depuis un fichier contenant les toutes informations nécessaires à la diffusion | Aucun schéma associé, aucune cible renseignée |
| Applications abonnés | Diffuser aux destinataires abonnés à une application | nms:appSubscriptionRcp |


## Créer un mapping de ciblage {#new-mapping}

Vous pouvez également créer un mapping de ciblage. Vous devrez peut-être ajouter un mapping de ciblage personnalisé, par exemple si :

* vous utilisez un tableau de destinataires personnalisé,
* vous paramétrez une dimension de filtrage différente de la dimension de ciblage intégrée dans l’écran des mappings de ciblage.

Pour en savoir plus sur la création des tableaux de destinataires personnalisés, consultez [cette page](../dev/custom-recipient.md).

L’assistant de création de mapping de ciblage Adobe Campaign vous permet de créer tous les schémas nécessaires pour utiliser votre mapping de ciblage personnalisé.

1. Accédez à **[!UICONTROL Administration]** `>` **[!UICONTROL Gestion de campagne]** `>` **[!UICONTROL Mappings de ciblage]** à partir de l&#39;explorateur Adobe Campaign.

1. Créez un nouveau mapping de ciblage et sélectionnez votre schéma personnalisé comme dimension de ciblage.

   ![](assets/new-target-mapping.png)


1. Indiquez les champs où sont stockées les informations de profil : nom, prénom, e-mail, adresse, etc.

   ![](assets/wf_new_mapping_define_join.png)

1. Indiquez les paramètres relatifs au stockage des informations, et notamment le suffixe des schémas d&#39;extension, pour qu&#39;ils soient facilement identifiables.

   ![](assets/wf_new_mapping_define_names.png)

   Vous pouvez choisir de stocker ou non les exclusions (**excludelog**), avec les messages (**broadlog**) ou dans une table distincte.

   Vous pouvez également gérer ou non le tracking pour ce mapping de diffusion (**trackinglog**).

1. Sélectionnez ensuite les extensions à prendre en compte. Le type d’extension dépend de vos paramètres de campagne et de vos modules complémentaires.

   ![](assets/wf_new_mapping_define_extensions.png)

   Cliquez sur le bouton **[!UICONTROL Enregistrer]** pour lancer la création du mapping de diffusion : toutes les tables liées sont créées automatiquement, selon les paramètres sélectionnés.
