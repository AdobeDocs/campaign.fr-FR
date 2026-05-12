---
title: Profils des opérateurs
description: Créer des opérateurs de gestion des offres
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
TQID: https://experienceleague.adobe.com/0Nx5tAtCSIZ3Ctm8MHRU7Aa2-8CyX6IbDgj9RF5KlSI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 264
ht-degree: 100%

---

# Profils des opérateurs {#operator-profiles}

Deux types d&#39;opérateurs peuvent utiliser l&#39;interaction Campaign : **chargés d&#39;offres** et **chargés de diffusion**. Chacun d&#39;eux a des autorisations et des restrictions spécifiques. Pour en savoir plus sur les opérateurs et les autorisations Campaign, consultez [cette page](../start/gs-permissions.md).

* Le **[!UICONTROL Chargé d&#39;offres]** crée et maintient les offres.
* Le **[!UICONTROL Chargé de diffusion]** valide et utilise les offres

## Créer un opérateur Chargé d&#39;offres{#offer-manager}

1. Créez un opérateur/une opératrice. [En savoir plus](../start/manage-permissions.md#add-users)
1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé d’offres]**.

Les autorisations associées aux chargés d’offres sont décrites [ici](../start/manage-permissions.md#ootb-productprofiles).

## Créer un opérateur/une opératrice Chargé(e) de diffusion {#delivery-manager}

1. Créez un opérateur/une opératrice. [En savoir plus](../start/manage-permissions.md#add-users)
1. Accédez à l’onglet **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]**, puis sélectionnez le groupe **[!UICONTROL Chargé de diffusion]**.

Les droits attribués aux chargés de diffusion leur permettent d&#39;effectuer les opérations suivantes :

* Afficher les environnements **[!UICONTROL En ligne]**.
* Afficher et modifier des catégories d&#39;offres.
* Valider les offres s&#39;ils sont validants de celles-ci.

  >[!NOTE]
  >
  >Les **Chargés de diffusion** ne peuvent valider une offre que s&#39;ils ont été définis comme validants lors du paramétrage de l&#39;offre.

## Matrice des autorisations par opérateur d&#39;interaction {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Chargé d'offres (environnement Design)</strong><br /> </td> 
   <td> <strong>Chargé d'offres (environnement Live)</strong><br /> </td> 
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
   <td> filtres d'offres prédéfinis<br /> </td> 
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
   <td> filtres d'offres prédéfinis<br /> </td> 
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
