---
solution: Campaign
product: Adobe Campaign
title: Opérateurs d’interaction Campaign
description: Créer des opérateurs de gestion des Offres
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 4bc62dcf806abd71e8230ce209d9151a4188b62e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 40%

---


# Profils d&#39;opérateurs {#operator-profiles}

Deux types d’opérateurs peuvent utiliser l’interaction Campaign : **gestionnaires d&#39;Offres** et **gestionnaires de Diffusions**. Chacun d&#39;eux a des autorisations et des restrictions spécifiques. Pour en savoir plus sur les opérateurs Campaign et les autorisations, consultez [cette page](../start/permissions.md).

* Le **[!UICONTROL gestionnaire d&#39;Offres]** crée et conserve des offres.
* Le **[!UICONTROL gestionnaire de Diffusions]** approuve et utilise les offres

## Créer un opérateur de gestionnaire d’Offres{#offer-manager}

1. Créez votre nouvel opérateur.

   :flèche_supérieur_droite : Les étapes de création d’un opérateur dans Campaign sont détaillées dans [la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html).

1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé d&#39;offres]**.

Les droits attribués au responsable de l&#39;Offre lui permettent d&#39;exécuter les tâches suivantes :

* Modifier des environnements **[!UICONTROL En édition]**.
* Consulter des environnements **[!UICONTROL En ligne]**.
* Paramétrer des fonctions d&#39;administration (emplacements et filtres prédéfinis).
* Créer et modifier des catégories.
* Créer des offres.
* Paramétrer l&#39;éligibilité des offres.
* Valider des offres.

Notez que si des offres sont utilisées dans un processus, l’opérateur doit être ajouté au groupe d’opérateurs **[!UICONTROL Administrator]** ou **[!UICONTROL Offres managers]** pour exécuter le processus.

>[!NOTE]
>
>Un **gestionnaire d&#39;Offres** ne peut approuver une offre que si aucun réviseur n&#39;est spécifié ou s&#39;il a été déclaré comme réviseur dans le modèle d&#39;offre sur lequel l&#39;offre était basée.

## Créer un opérateur de gestionnaire de Diffusions {#delivery-manager}

1. Créez votre nouvel opérateur.

   :flèche_supérieur_droite : Les étapes de création d’un opérateur dans Campaign sont détaillées dans [la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html).

1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé de diffusion]**.

Les droits attribués au responsable de la Diffusion lui permettent d&#39;exécuter les tâches suivantes :

* Afficher les environnements **[!UICONTROL En ligne]**.
* Afficher et modifier des catégories d&#39;offres.
* Valider des offres s&#39;il y est spécifié comme validant.

   >[!NOTE]
   >
   >Un **gestionnaire de Diffusions** ne peut approuver une offre que s&#39;il a été déclaré comme réviseur lors de la configuration de l&#39;offre.

## Matrice d&#39;autorisation par opérateur d&#39;interaction {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gestionnaire d’Offres (Design Env)</strong><br /> </td> 
   <td> <strong>Gestionnaire d’Offres (Live Env)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Niveau de l'arborescence</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Offres en édition / Offres en ligne<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Environnement - Destinataire<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Administration<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Emplacements<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtres prédéfinis d'offres<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologie<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Règles de typologie<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Catalogue d'offres<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Catégorie d'offres<br /> </td> 
   <td> Lecture / Ecriture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gestionnaire de diffusions (env. conception)</strong><br /> </td> 
   <td> <strong>Gestionnaire de diffusions (version en direct)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Niveau de l'arborescence</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Offres en édition / Offres en ligne<br /> </td> 
   <td> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Environnement - Destinataire<br /> </td> 
   <td> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Administration<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Emplacements<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Filtres prédéfinis d'offres<br /> </td> 
   <td> Lecture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologie<br /> </td> 
   <td> Lecture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Règles de typologie<br /> </td> 
   <td> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Catalogue d'offres<br /> </td> 
   <td> Lecture<br /> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
  <tr> 
   <td> Catégorie d'offres<br /> </td> 
   <td> </td> 
   <td> Lecture<br /> </td> 
  </tr> 
 </tbody> 
</table>
