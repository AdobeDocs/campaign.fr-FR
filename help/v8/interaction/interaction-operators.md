---
title: Profils des opérateurs
description: Créer des opérateurs de gestion des offres
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 8a43f0fad9f84849745f3a0d426329efbf228105
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 100%

---

# Profils des opérateurs {#operator-profiles}

Deux types d&#39;opérateurs peuvent utiliser l&#39;interaction Campaign : **chargés d&#39;offres** et **chargés de diffusion**. Chacun d&#39;eux a des autorisations et des restrictions spécifiques. Pour en savoir plus sur les opérateurs et les autorisations Campaign, consultez [cette page](../start/permissions.md).

* Le **[!UICONTROL Chargé d&#39;offres]** crée et maintient les offres.
* Le **[!UICONTROL Chargé de diffusion]** valide et utilise les offres

## Créer un opérateur Chargé d&#39;offres{#offer-manager}

1. Création d’un opérateur.

   ![](../assets/do-not-localize/book.png) Les étapes de création d&#39;un opérateur dans Campaign sont présentées dans la [documentation de Campaign Classic v7.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html?lang=fr)

1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé d&#39;offres]**.

Les droits attribués au Chargé d&#39;offres lui permettent d&#39;effectuer les opérations suivantes :

* Modifier des environnements **[!UICONTROL En édition]**.
* Consulter des environnements **[!UICONTROL En ligne]**.
* Paramétrez des fonctions dʼadministration (emplacements et filtres prédéfinis).
* Créer et modifier des catégories.
* Créer des offres.
* Paramétrer l&#39;éligibilité des offres.
* Valider des offres.

Notez que si des offres sont utilisées dans le workflow, l’opérateur doit être ajouté au groupe d’opérateurs **[!UICONTROL Administrateur]** ou **[!UICONTROL Chargés d’offres]** pour exécuter le workflow.

>[!NOTE]
>
>**Les chargés d’offres** ne peuvent valider une offre que si aucun validant n’est spécifié ou s’ils ont été déclarés comme validants dans le modèle d’offre.

## Créer un opérateur Chargé de diffusion {#delivery-manager}

1. Création d’un opérateur.

   ![](../assets/do-not-localize/book.png) Les étapes de création d&#39;un opérateur dans Campaign sont présentées dans la [documentation de Campaign Classic v7.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé de diffusion]**.

Les droits attribués aux chargés de diffusion leur permettent d’effectuer les opérations suivantes :

* Afficher les environnements **[!UICONTROL En ligne]**.
* Afficher et modifier des catégories d&#39;offres.
* Valider les offres s’ils sont validants de celles-ci.

   >[!NOTE]
   >
   >Les **Chargés de diffusion** ne peuvent valider une offre que sʼils ont été définis comme validants lors du paramétrage de lʼoffre.

## Matrice des autorisations par opérateur d’interaction {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Chargé d’offres (environnement Design)</strong><br /> </td> 
   <td> <strong>Chargé d’offres (environnement Live)</strong><br /> </td> 
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
   <td> filtres dʼoffres prédéfinis<br /> </td> 
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
   <td> filtres dʼoffres prédéfinis<br /> </td> 
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
