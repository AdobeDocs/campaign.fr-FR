---
product: campaign
title: Définir la disposition des formulaires web
description: Définir la disposition des formulaires web
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 23ca17f8-de1a-4f9c-8357-3965dc3329b1
TQID: 'https://experienceleague.adobe.com/-0PZWl-79Q-MXZ-jHjp-VF12IUPeMcq27aGSgWl5Ans'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 72%
---
# Définir la disposition des formulaires web{#defining-web-forms-layout}



## Créer des conteneurs {#creating-containers}

Les conteneurs vous permettent de combiner les champs d’une page, de configurer leur disposition et d’organiser les éléments dans la page.

Pour chaque page du formulaire, les conteneurs sont créés à partir du bouton **[!UICONTROL Conteneurs]** de la barre d&#39;outils.

![Éditeur de page de formulaire web avec le bouton Conteneurs de la barre d&#39;outils ouvert, offrant l&#39;option Conteneur standard](assets/s_ncs_admin_survey_containers_add.png)

Utilisez un conteneur pour regrouper des éléments de la page sans ajouter de libellé dans le rendu final. Les éléments sont regroupés dans la sous-arborescence du conteneur. Les conteneurs standards vous permettent de gérer la disposition.

Par exemple :

![Propriétés de page avec une arborescence de deux conteneurs, Informations générales et Vos contrats, et leurs champs de formulaire](assets/s_ncs_admin_survey_containers_std_arbo.png)

La position des libellés est appliquée aux éléments placés sous le conteneur dans la hiérarchie. Elle peut être surchargée pour chaque élément si nécessaire. Ajoutez ou supprimez des colonnes pour modifier la disposition. Voir [Placer les champs de la page](#positioning-the-fields-on-the-page).

Dans l&#39;exemple ci-dessus, le rendu sera le suivant :

![Page de formulaire générée avec deux conteneurs : des champs de détails personnels et une liste de cases à cocher de contrat, plus un bouton Valider](assets/s_ncs_admin_survey_containers_std_ex.png)

## Placer les champs de la page {#positioning-the-fields-on-the-page}

La mise en page du formulaire web est définie page par page, pour chaque conteneur et peut être surchargée si nécessaire.

Les pages sont organisées en colonnes : chaque page contient un certain nombre de colonnes. Chaque champ de la page occupe **n** cellules. Les conteneurs s’étendent eux aussi sur un certain nombre de colonnes et les champs qu’ils contiennent s’étendent sur un certain nombre de cellules.

Par défaut, les pages sont construites sur une seule colonne et chaque élément occupe une cellule. Ainsi, les champs sont affichés les uns en dessous des autres, chacun occupant toute la ligne, comme ci-dessous :

![Page de formulaire à une seule colonne générée avec les champs Genre, Nom, Prénom et E-mail empilés sur des lignes distinctes](assets/s_ncs_admin_survey_container_ex.png)

Dans l’exemple suivant, la configuration par défaut a été conservée. La page occupe une seule colonne qui comprend quatre conteneurs.

![Propriétés de page avec quatre conteneurs et Nombre de colonnes défini sur 1 mis en surbrillance](assets/s_ncs_admin_survey_container_ex0.png)

Chaque conteneur s&#39;étend sur une colonne et chaque élément occupe une cellule :

![Propriétés des éléments d&#39;information avec le nombre de cellules défini sur 1 mis en surbrillance dans les paramètres d&#39;affichage](assets/s_ncs_admin_survey_container_ex0a.png)

Le rendu est le suivant :

![Rendu de page à une seule colonne avec quatre conteneurs, chacun avec une colonne, empilés verticalement](assets/s_ncs_admin_survey_container_ex0_rend.png)

Vous pouvez adapter les paramètres d&#39;affichage pour obtenir le rendu suivant :

![Rendu de page à deux colonnes où les conteneurs 1 et 3 remplissent la colonne de gauche et les conteneurs 2 et 4 la colonne de droite](assets/s_ncs_admin_survey_container_ex1_rend.png)

Dans l&#39;exemple de rendu ci-dessus, chaque zone de saisie, chaque titre et chaque image occupent une seule cellule dans les colonnes des conteneurs.

Vous pouvez modifier la mise en forme dans chaque conteneur. Dans notre exemple, vous pouvez passer le contenu du conteneur 4 sur deux colonnes et répartir les éléments.

![Conteneur 4 à deux colonnes : le titre et la zone de liste déroulante prennent une cellule chacun, la case à cocher s&#39;étend sur deux cellules](assets/s_ncs_admin_survey_container_ex2_rend.png)

Le titre et la liste occupent une cellule chacun (et donc une ligne entière du conteneur) et la case à cocher s’étend sur deux cellules. Le nombre de cellules attribuées au champ de saisie est défini dans l’onglet **[!UICONTROL Général]** ou l’onglet **[!UICONTROL Avancé]** , en fonction du type de champ :

![Onglet Avancé de l’élément de case à cocher avec le nombre de cellules défini sur 2 sous Paramètres d’affichage](assets/s_ncs_admin_survey_container_ex2.png)

## Définir la position des libellés {#defining-the-position-of-labels}

Vous pouvez définir l&#39;alignement des champs et des libellés du formulaire.

Par défaut, les paramètres d&#39;affichage des champs et autres contenus de la page sont hérités du paramétrage général du formulaire, le paramétrage de la page ou celui du conteneur parent, s&#39;il existe.

Les paramètres d&#39;affichage globaux pour tout le formulaire sont indiqués dans la boîte de propriétés du formulaire. L&#39;onglet **[!UICONTROL Rendu]** permet de sélectionner la position des libellés.

![Boîte de dialogue Propriétés du formulaire Web, onglet Rendu, avec la liste Position du libellé : Hérité, Gauche, Droite, Au-dessus, En dessous, Masqué](assets/s_ncs_admin_survey_label_position.png)

Cette position peut être surchargée au niveau de chaque page, puis de chaque conteneur et enfin au niveau de chaque champ, à partir de l&#39;onglet **[!UICONTROL Avancé]**.

Les alignements supportés sont les suivants :

* Hérité : l&#39;alignement est hérité de l&#39;élément parent (valeur par défaut), c&#39;est-à-dire le conteneur parent, ou, à défaut, la page.
* Gauche/Droite : le libellé est positionné à droite ou à gauche du champ,
* Au-dessus/En-dessous : le libellé est positionné au-dessus ou en-dessous du champ,
* Caché : le libellé n&#39;est pas affiché.
