---
solution: Campaign v8
product: Adobe Campaign
title: Opérateurs d'interaction Campaign
description: Créer des opérateurs Gestion des offres
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: 167730cc3e81ee47f02bcdbc2c39fe793a99c534
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 40%

---


# Profils des opérateurs {#operator-profiles}

Deux types d&#39;opérateurs peuvent utiliser l&#39;interaction Campaign : **Chargés d’offres** et **Chargés de diffusions**. Chacun d’eux a des autorisations et des restrictions spécifiques. Pour en savoir plus sur les opérateurs et les permissions Campaign, consultez [cette page](../start/permissions.md).

* Le **[!UICONTROL Chargé d&#39;offres]** crée et maintient les offres.
* **[!UICONTROL Chargé de diffusion]** valide et utilise les offres

## Créer un opérateur Chargé d&#39;offres{#offer-manager}

1. Créez votre nouvel opérateur.

   [!DNL :arrow_upper_right:] Les étapes de création d&#39;un opérateur dans Campaign sont présentées dans la documentation de  [Campaign Classic v7.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé d&#39;offres]**.

Les droits attribués au chargé d&#39;offres lui permettent d&#39;effectuer les tâches suivantes :

* Modifier des environnements **[!UICONTROL En édition]**.
* Consulter des environnements **[!UICONTROL En ligne]**.
* Paramétrer des fonctions d&#39;administration (emplacements et filtres prédéfinis).
* Créer et modifier des catégories.
* Créer des offres.
* Paramétrer l&#39;éligibilité des offres.
* Valider des offres.

Notez que si des offres sont utilisées dans un workflow, l&#39;opérateur doit être ajouté au groupe d&#39;opérateurs **[!UICONTROL Administrateur]** ou **[!UICONTROL Chargés d&#39;offres]** pour exécuter le workflow.

>[!NOTE]
>
>Un **Chargé d&#39;offres** ne peut valider une offre que si aucun validant n&#39;est spécifié ou s&#39;il a été déclaré validant dans le modèle d&#39;offre sur lequel l&#39;offre a été basée.

## Créer un opérateur Chargé de diffusion {#delivery-manager}

1. Créez votre nouvel opérateur.

   [!DNL :arrow_upper_right:] Les étapes de création d&#39;un opérateur dans Campaign sont présentées dans la documentation de  [Campaign Classic v7.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Dans la fenêtre **[!UICONTROL Groupes et droits nommés]**, cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le groupe **[!UICONTROL Chargé de diffusion]**.

Les droits attribués au chargé de diffusion sont/permettent d&#39;effectuer les tâches suivantes :

* Afficher les environnements **[!UICONTROL En ligne]**.
* Afficher et modifier des catégories d&#39;offres.
* Valider des offres s&#39;il y est spécifié comme validant.

   >[!NOTE]
   >
   >Un **chargé de diffusion** ne peut valider une offre que s&#39;il a été déclaré validant lors du paramétrage de l&#39;offre.

## Matrice des permissions par opérateur Interaction {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Chargé d’offres (environnement de conception)</strong><br /> </td> 
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
   <td> <strong>Chargé de diffusion (environnement de conception)</strong><br /> </td> 
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
