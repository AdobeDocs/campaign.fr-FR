---
title: Opérateurs de Campaign Interaction
description: Créer des opérateurs de gestion des offres
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: bda1fc37181396d295ee23a7161053d839d9cfc7
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 83%

---

# Profils des opérateurs {#operator-profiles}

Deux types d&#39;opérateurs peuvent utiliser l&#39;interaction Campaign : **chargés d&#39;offres** et **chargés de diffusion**. Chacun d&#39;eux a des autorisations et des restrictions spécifiques. Pour en savoir plus sur les opérateurs et les autorisations Campaign, consultez [cette page](../start/permissions.md).

* Le **[!UICONTROL Chargé d&#39;offres]** crée et maintient les offres.
* Le **[!UICONTROL Chargé de diffusion]** valide et utilise les offres

## Créer un opérateur Chargé d&#39;offres{#offer-manager}

1. Créez votre nouvel opérateur.

   ↗️ Les étapes de création d&#39;un opérateur dans Campaign sont présentées dans la [documentation de Campaign Classic v7.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html?lang=fr)

1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé d&#39;offres]**.

Les droits attribués au Chargé d&#39;offres lui permettent d&#39;effectuer les opérations suivantes :

* Modifier des environnements **[!UICONTROL En édition]**.
* Consulter des environnements **[!UICONTROL En ligne]**.
* Paramétrer des fonctions d&#39;administration (emplacements et filtres prédéfinis).
* Créer et modifier des catégories.
* Créer des offres.
* Paramétrer l&#39;éligibilité des offres.
* Valider des offres.

Notez que si des offres sont utilisées dans le workflow, l&#39;opérateur doit être ajouté au le groupe d&#39;opérateurs **[!UICONTROL Administrateur]** ou **[!UICONTROL Chargés d&#39;offres]** pour l&#39;exécuter.

>[!NOTE]
>
>**Les** gestionnaires d&#39;offres ne peuvent valider une offre que si aucun opérateur validant n&#39;est spécifié ou s&#39;ils ont été déclarés comme validants dans le modèle d&#39;offre.

## Créer un opérateur Chargé de diffusion {#delivery-manager}

1. Créez votre nouvel opérateur.

   ↗️ Les étapes de création d&#39;un opérateur dans Campaign sont présentées dans la [documentation de Campaign Classic v7.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé de diffusion]**.

Les droits attribués aux responsables de diffusion leur permettent d&#39;effectuer les tâches suivantes :

* Afficher les environnements **[!UICONTROL En ligne]**.
* Afficher et modifier des catégories d&#39;offres.
* Validez les offres si elles sont les réviseurs.

   >[!NOTE]
   >
   >**Le** responsable de diffusion ne peut valider une offre que s&#39;il a été déclaré validant dans le paramétrage de l&#39;offre.

## Matrice des autorisation par opérateur d&#39;interaction {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Chargé d'offres (environnement en édition)</strong><br /> </td> 
   <td> <strong>Chargé d'offres (environnement en ligne)</strong><br /> </td> 
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
   <td> <strong>Chargé de diffusion (environnement en édition)</strong><br /> </td> 
   <td> <strong>Chargé de diffusion (environnement en ligne)</strong><br /> </td> 
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
