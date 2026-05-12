---
title: Utilisation de Campaign et SFDC
description: Découvrez comment utiliser Campaign et Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
TQID: https://experienceleague.adobe.com/N50ecfMFC641fveGfyxx4W9XvZgWPgddrdpj9KrCHBY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 97%

---

# Utilisation de Campaign et SFDC{#crm-sfdc}

Découvrez comment configurer le connecteur CRM Campaign pour connecter Campaign v8 à **Salesforce.com**.

Une fois le paramétrage effectué, la synchronisation des données entre les systèmes s&#39;effectue via une activité de workflow dédiée. [En savoir plus](crm-data-sync.md).

>[!NOTE]
>
>Les versions de SFDC prises en charge sont présentées dans la [matrice de compatibilité](../start/compatibility-matrix.md) de Campaign.

Suivez les étapes ci-dessous pour configurer un compte externe dédié afin d’importer et d’exporter des données Salesforce vers Adobe Campaign.

## Création de la connexion{#new-sfdc-external-account}

Tout d’abord, vous devez créer le compte externe Salesforce.

1. Parcourez le nœud **[!UICONTROL Administration > Plateforme > Comptes externes]** de l&#39;explorateur Campaign et créez un compte externe.
1. Sélectionnez le compte externe **[!UICONTROL Salesforce.com]** dans la section **Type**.
1. Saisissez les paramètres pour activer la connexion.

   ![](assets/sfdc-external-account.png)

   Pour configurer le compte externe Salesforce CRM afin de l’utiliser avec Adobe Campaign, vous devez fournir les détails suivants :

   * Saisissez votre identifiant Salesforce dans le champ **[!UICONTROL Compte]**.
   * Saisissez votre mot de passe Salesforce.
   * Vous pouvez ignorer le champ **[!UICONTROL Identifiant du client]**.
   * Copiez/collez votre **[!UICONTROL Jeton de sécurité]** Salesforce.
   * Sélectionnez votre **[!UICONTROL Version de l’API]**. Les versions d’API SFDC prises en charge sont répertoriées dans la [matrice de compatibilité](../start/compatibility-matrix.md) de Campaign.

1. Sélectionnez l’option **Activer** pour activer le compte dans Campaign.

>[!NOTE]
>
>Pour approuver la configuration, vous devez procéder à une déconnexion/reconnexion à la console cliente Adobe Campaign.

## Sélection des tables à synchroniser{#sfdc-create-tables}

Vous pouvez maintenant configurer les tables à synchroniser.

1. Cliquez sur l’**[!UICONTROL Assistant de configuration Salesforce CRM...]**.
1. Sélectionnez les tables à synchroniser et démarrez le processus.
1. Vérifiez le schéma généré dans Adobe Campaign, sous le noeud **[!UICONTROL Administration > Paramétrage > Schéma de données]**.

   Exemple d’un schéma **Salesforce** importé dans Campaign :

   ![](assets/sfdc-schemas.png)

## Synchronisation des énumérations{#sfdc-enum-sync}

Une fois le schéma créé, vous pouvez synchroniser automatiquement les énumérations entre Salesforce et Adobe Campaign.

1. Ouvrez l’assistant à partir du lien **[!UICONTROL Synchronisation des énumérations...]**.
1. Sélectionnez l’énumération d’Adobe Campaign correspondant à l’énumération Salesforce.
Vous pouvez remplacer toutes les valeurs d&#39;une énumération Adobe Campaign par celles du CRM : pour cela, sélectionnez **[!UICONTROL Oui]** dans la colonne **[!UICONTROL Remplacer]**.

   ![](assets/sfdc-enum.png)

1. Cliquez sur **[!UICONTROL Suivant]** puis **[!UICONTROL Démarrer]** pour lancer l&#39;import des énumérations.

1. Parcourez le nœud **[!UICONTROL Administration > Plateforme > Énumérations]** pour vérifier les valeurs importées. Pour en savoir plus sur les énumérations, consultez [cette page](../config/ui-settings.md#enumerations).

Adobe Campaign et Salesforce.com sont maintenant connectés. Vous pouvez configurer la synchronisation des données entre les deux systèmes.

Pour synchroniser les données entre Adobe Campaign et SFDC, créez un workflow et utilisez l’activité **[!UICONTROL Connecteur CRM]**.

Pour en savoir plus sur la synchronisation des données, consultez [cette page](crm-data-sync.md).

En savoir plus sur la gestion des énumérations dans Campaign [sur cette page](../config/enumerations.md).
