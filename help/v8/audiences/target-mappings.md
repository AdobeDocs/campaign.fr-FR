---
title: Utiliser les mappings de ciblage
description: Découvrez comment utiliser et créer des mappings de ciblage
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 100%

---

# Utiliser les mappings de ciblage{#gs-target-mappings}

Par défaut, les modèles de diffusion ciblent les **[!UICONTROL Destinataires]**. Leur mapping de ciblage utilise donc les champs du tableau **nms:recipient**.

Vous pouvez utiliser d’autres mappings de ciblage pour vos diffusions ou créer un nouveau mapping de ciblage.

## Mappings de ciblage intégrés {#ootb-mappings}

Adobe Campaign est fourni avec les mappings de ciblage intégrés suivants :

| Nom | Utilisation à | Schéma |
|---|---|---|
| Destinataires | Diffuser aux destinataires (tableau de destinataires intégré) | nms:recipient |
| Visiteurs | Diffuser aux visiteurs dont les profils ont été collectés par le biais d’une recommandation (marketing viral), par exemple. | mns:visitor |
| Abonnements  | Diffuser aux destinataires abonnés à un service d&#39;information, par exemple une newsletter | nms:subscription |
| Abonnements des visiteurs | Diffuser à des visiteurs abonnés à un service d&#39;information | nms:visitorSub |
| Les opérateurs | Diffuser aux opérateurs Adobe Campaign | nms:operator |
| Fichier externe | Diffuser depuis un fichier contenant les toutes informations nécessaires à la diffusion | Aucun schéma associé, aucune cible renseignée |

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
