---
product: campaign
title: Ajouter des champs à un formulaire web
description: Ajouter des champs à un formulaire web
feature: Web Forms, Landing Pages
version: Campaign v8, Campaign Classic v7
exl-id: 827b6575-7206-4dfc-b2c6-b95a6d5730b1
TQID: 'https://experienceleague.adobe.com/uHsP-67EhxMoCun8GEh1CzbeU5FJaDc1cdlsSVyayU4'
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '3245'
ht-degree: 74%
---
# Ajouter des champs à un formulaire web{#adding-fields-to-a-web-form}



Dans un formulaire web, les champs permettent aux utilisateurs et utilisatrices de saisir des informations et de sélectionner des options. Les formulaires web peuvent proposer des champs de saisie, des champs de sélection, ainsi que des contenus statiques et avancés (captcha, abonnements, etc.).

Lorsque vous utilisez l’assistant d’ajout de champs, le type de champ est automatiquement détecté en fonction du champ ou de la variable de stockage sélectionnée. Au besoin, vous pouvez le modifier à partir de la liste déroulante **[!UICONTROL Type]** de l&#39;onglet **[!UICONTROL Général]**.

Boîte de dialogue ![Page, onglet Général, avec la liste déroulante Type ouverte pour remplacer un champ de la zone de liste déroulante par un autre type de champ](assets/s_ncs_admin_webform_change_type.png)

Lorsque vous utilisez les boutons de la barre d&#39;outils, sélectionnez directement le type de champ à ajouter.

Les types de champs disponibles sont les suivants :

* Entrée texte/nombre. Voir [Ajouter des champs de saisie](#adding-input-fields).
* Sélection d&#39;une liste déroulante. Voir [Ajouter des listes déroulantes](#adding-drop-down-lists).
* Choix multiple via des cases à cocher. Voir [Ajouter des cases à cocher](#adding-checkboxes).
* Sélection exclusive via des boutons radio. Voir [Ajouter des boutons radio](#adding-radio-buttons).
* Vote dans une grille d&#39;options. Voir [Ajouter des matrices](#adding-grids).
* Nombres et dates. Voir [Ajouter des dates et des nombres](#adding-dates-and-numbers).
* Abonnement/désabonnement à un service d&#39;informations. Voir [Cases à cocher d&#39;abonnement](#subscription-checkboxes).
* Validation de captcha. Voir [Insérer un captcha](#inserting-a-captcha).
* Bouton de téléchargement. [Télécharger un fichier](#uploading-a-file).
* Constante masquée. Voir [Insérer une constante masquée](#inserting-a-hidden-constant).

Spécifiez le mode de stockage des réponses : mise à jour d&#39;un champ de la base (seule la dernière valeur enregistrée est conservée) ou stockage dans une variable (la réponse ne sera pas stockée). Voir à ce sujet la section [Champs de stockage des réponses](web-forms-answers.md#response-storage-fields).

>[!NOTE]
>
>Par défaut, le champ est inséré à la fin de l’arborescence actuelle. Il peut être déplacé vers le haut ou vers le bas en utilisant les flèches de la barre d’outils.

## Assistant de création de champs {#field-creation-assistant}

Pour chaque page du formulaire, vous pouvez ajouter un champ à l’aide du premier bouton de la barre d’outils. Pour ce faire, accédez au menu **[!UICONTROL Ajouter à l’aide de l’assistant]**.

![Assistant de création de champs permettant de répondre à une question, de modifier un destinataire, d&#39;ajouter une variable et d&#39;importer une question existante](assets/s_ncs_admin_survey_add_field_menu.png)

Sélectionnez le type de champ que vous souhaitez créer : vous pouvez choisir d&#39;ajouter un champ de la base, une variable ou d&#39;importer un groupe de champs créé dans un autre formulaire et regroupés dans un conteneur.

Cliquez sur le bouton **[!UICONTROL Suivant]** et choisissez le champ ou la variable de stockage, ou le conteneur à importer.

![Assistant de création de champ, étape Modifier le profil, avec le champ Base de données Salutation sélectionné avant de cliquer sur Terminer](assets/s_ncs_admin_webform_wz_confirm_db.png)

Cliquez sur **[!UICONTROL Terminer]** pour insérer le champ sélectionné dans la page.

Boîte de dialogue de la page ![Affichage du champ de zone de liste Salutation inséré dans la page Bienvenue après l’assistant](assets/s_ncs_admin_webform_wz_insert_field.png)

## Ajouter des champs de saisie {#adding-input-fields}

Pour ajouter un champ de saisie, cliquez sur le bouton **[!UICONTROL Contrôle de saisie]** et sélectionnez le type de champ à ajouter.

![Menu Contrôle de saisie répertoriant les types de champs de texte Texte, Nombre, Mot de passe, Texte multiligne et Texte HTML](assets/s_ncs_admin_webform_select_field.png)

### Types de champs de saisie {#types-of-input-fields}

Dans une page de formulaire, vous pouvez insérer cinq types de champs texte :

* **Texte** : permet à l&#39;utilisateur de saisir du texte sur une ligne.

  ![Champ de texte rendu intitulé Votre nom contenant une valeur d&#39;une ligne](assets/s_ncs_admin_survey_txt_ex.png)

* **Nombre** : permet à l&#39;utilisateur de saisir un nombre sur une ligne. Pour plus d&#39;informations, consultez la section [Ajouter des numéros](#adding-numbers).

  Lors de la validation de la page, le contenu des champs est contrôlé afin de vérifier que la valeur saisie est compatible avec le champ. Voir à ce sujet la section [Définir les paramètres de contrôle](form-rendering.md#defining-control-settings).

* **Mot de passe** : permet à l’utilisateur ou à l’utilisatrice de saisir du texte sur une seule ligne. Lors de la saisie, les caractères sont remplacés par des points :

  ![Champ de mot de passe rendu intitulé Votre mot de passe avec les caractères saisis masqués sous forme de points](assets/s_ncs_admin_survey_passwd_ex.png)

  >[!CAUTION]
  >
  >Les mots de passe sont stockés en clair dans la base, sans chiffrement.

* **Texte multi-lignes** : permet à l&#39;utilisateur de saisir du texte sur plusieurs lignes.

  ![Champ de texte multiligne rendu intitulé Votre message avec une barre de défilement et un exemple de texte](assets/s_ncs_admin_survey_txtmulti_ex.png)

  >[!CAUTION]
  >
  >Les champs de texte multiligne sont des champs spécifiques pouvant contenir des retours à la ligne. Leur espace de stockage doit être associé à un champ mappé sur un élément XML et non sur un attribut XML.
  >   

* **Texte multi-lignes enrichi** : permet à l&#39;utilisateur de saisir du texte avec une certaine disposition, qui sera stocké au format HTML.

  ![Éditeur de texte enrichi rendu avec barre d&#39;outils de mise en forme, gras, liens et une image insérée](assets/s_ncs_admin_survey_txthtmli_ex.png)

  Vous pouvez sélectionner le type d&#39;éditeur qui sera proposé aux utilisateurs. Pour cela, utilisez la liste déroulante du champ **[!UICONTROL Editeur Html]** de l&#39;onglet **[!UICONTROL Avancé]**.

  ![Onglet Avancé avec la liste déroulante de l’éditeur HTML qui répertorie Minimaliste, De base, Intermédiaire et Avancé](assets/webapp_enrich_text_type.png)

  Le nombre d’icônes affichées varie en fonction du type d’éditeur. Pour un éditeur **[!UICONTROL Avancé]**, le rendu sera le suivant :

  ![Éditeur HTML avancé sur une page de formulaire avec une barre d’outils complète et le menu déroulant Taille de police s’ouvre](assets/webapp_enrich_text_max.png)

### Paramétrage des champs de saisie {#configure-input-fields}

Les champs de saisie sont tous paramétrés selon le même mode, au travers des options suivantes :

![Onglet général d&#39;un champ de saisie de texte avec Libellé, Obligatoire, Stockage, Modifier le lien de stockage et Valeur par défaut](assets/s_ncs_admin_survey_txt_param.png)

L&#39;onglet **[!UICONTROL Général]** permet de saisir le nom du champ et éventuellement de lui attribuer une valeur par défaut.

Vous pouvez modifier le mode de stockage des réponses à partir du lien **[!UICONTROL Modifier le stockage…]**. Les valeurs peuvent être enregistrées dans un champ existant de la base de données, mais vous pouvez choisir de ne pas enregistrer les informations dans la base, en utilisant une variable locale.

>[!NOTE]
>
>Les modes de stockage sont détaillés dans [Champs de stockage des réponses](web-forms-answers.md#response-storage-fields).

L&#39;onglet **[!UICONTROL Avancé]** permet de définir des paramètres d&#39;affichage du champ (position des libellés, alignement, etc.). Voir [Définir la disposition des formulaires web](defining-web-forms-layout.md).

## Ajouter des listes déroulantes {#adding-drop-down-lists}

Vous pouvez insérer une liste déroulante dans une page de questionnaire. Elle permet à l’utilisateur ou à l’utilisatrice de sélectionner une valeur parmi celles proposées dans un menu déroulant.

![Liste déroulante rendue intitulée Titre offrant Monsieur, Madame et Mlle](assets/s_ncs_admin_survey_dropdown_sample.png)

Pour ajouter une liste déroulante dans une page de formulaire, cliquez sur le bouton **[!UICONTROL Contrôles de sélection > Liste déroulante...]** dans la barre d&#39;outils de l&#39;éditeur de page.

![Menu de la barre d&#39;outils de l&#39;éditeur de page Contrôles de sélection avec zone de liste déroulante, Case à cocher, Bouton radio, Choix multiples, Date, Grille](assets/s_ncs_admin_survey_create_dropdown.png)

Sélectionnez le mode de stockage des réponses et validez votre choix.

Définissez les libellés et les valeurs de la liste dans la section inférieure de l’onglet **[!UICONTROL Général]** . Si les informations sont stockées dans un champ existant de la base de données et s’il s’agit d’un champ d’énumération, vous pouvez renseigner automatiquement les valeurs en cliquant sur **[!UICONTROL Initialiser la liste des valeurs depuis la base de données]**, comme illustré ci-dessous :

![Onglet Général de la zone de liste déroulante avec le lien Initialiser la liste des valeurs à partir de la base de données et la liste remplie](assets/s_ncs_admin_survey_database_values.png)

>[!NOTE]
>
>Utilisez les flèches situées à droite de la liste des valeurs pour les ordonner.

Si les données sont stockées dans une table liée, vous pouvez sélectionner le champ où sont enregistrées les valeurs à proposer dans la liste. Par exemple, si vous sélectionnez le tableau des pays, cliquez sur **[!UICONTROL Initialiser la liste des valeurs depuis la base de données]** et sélectionnez le champ souhaité.

![Boîte de dialogue de l&#39;application Web pour sélectionner le champ Libellé dans la table Pays, avec la boîte de dialogue Sélectionner une expression](assets/s_ncs_admin_survey_preload_values.png)

Cliquez ensuite sur le lien **[!UICONTROL Charger]** pour récupérer les valeurs :

![Boîte de dialogue de l&#39;application Web après avoir cliqué sur Charger, avec une prévisualisation de la liste des libellés et valeurs de pays](assets/s_ncs_admin_survey_load_button.png)

>[!CAUTION]
>
>En cas de mise à jour des valeurs de la liste, vous devez renouveler cette opération pour actualiser les valeurs proposées.

## Ajouter des cases à cocher {#adding-checkboxes}

Pour que l&#39;utilisateur puisse sélectionner une option, utilisez une case à cocher.

![Case à cocher générée, cochée, avec le libellé Je souhaite recevoir votre newsletter](assets/s_ncs_admin_survey_check_box.png)

Pour ajouter une case à cocher dans une page de formulaire, cliquez sur l&#39;icône **[!UICONTROL Contrôles de sélection > Case à cocher...]** dans la barre d&#39;outils de l&#39;éditeur de page.

Sélectionnez le mode de stockage des réponses et validez votre choix.

Saisissez le libellé de la case dans le champ **[!UICONTROL Libellé]** de l&#39;onglet **[!UICONTROL Général]**.

![Onglet Général de la case à cocher avec les champs Libellé, Stockage, Sélectionné par défaut, Valeur et Valeur vide](assets/s_ncs_admin_survey_check_box_edit.png)

Une case à cocher permet d&#39;attribuer au champ (ou à la variable) de stockage une valeur ou une autre selon que la case est cochée ou non. La section **[!UICONTROL Valeurs]** permet de saisir la valeur à attribuer si la case est cochée (dans le champ **[!UICONTROL Valeur]**) et la valeur à attribuer si la case est décochée (dans le champ **[!UICONTROL Valeur vide]**). Ces valeurs dépendent du format de stockage des données.

Si le champ (ou la variable) de stockage est de type booléen, la valeur à attribuer si la case n’est pas cochée est déduite automatiquement. Dans ce cas, seul le champ **[!UICONTROL Valeur si coché]** est proposé, comme illustré ci-dessous :

![Onglet Général de la case à cocher pour un champ booléen, avec uniquement la liste déroulante Valeur si coché offrant Oui et Non](assets/s_ncs_admin_survey_check_box_enum.png)

## Exemple : attribuer une valeur à un champ si une case est cochée {#example--assign-a-value-to-a-field-if-a-box-is-checked}

Nous allons insérer une case à cocher dans un formulaire afin de transmettre une demande d&#39;intervention, comme ci-dessous :

![Page de formulaire générée avec une liste déroulante Produit, un champ Date d’expédition et une case à cocher Maintenance requise cochée](assets/s_ncs_admin_survey_check_box_ex.png)

Les informations seront chargées vers la base de données dans un champ existant (ici, le champ **[!UICONTROL Commentaire]**) :

![Liste des destinataires avec une colonne Commentaire indiquant Maintenance requise ou Maintenance non requise](assets/s_ncs_admin_survey_check_box_ex_list.png)

Si la case « Maintenance nécessaire » est cochée, la colonne **[!UICONTROL Commentaire]** contient le message « Maintenance nécessaire ». Si la case est décochée, elle contient le message « Maintenance non nécessaire ». Pour obtenir ce résultat, le paramétrage de la case à cocher doit être le suivant dans la page du formulaire :

![La case à cocher Maintenance requise est stockée dans le champ de commentaire, avec les textes Valeur et Valeur vide](assets/s_ncs_admin_survey_check_box_ex_edit.png)

## Ajouter des boutons radio {#adding-radio-buttons}

Les cases d’option permettent de proposer une série d’options à sélection exclusive. Il s’agit de valeurs différentes pour le même champ.

![Boutons radio rendus Monsieur, Madame et Mademoiselle, avec Madame sélectionnée](assets/s_ncs_admin_survey_radio_button.png)

Vous pouvez créer les boutons radio individuellement (boutons unitaires) ou via une liste à choix multiples. Toutefois, le principe du bouton radio étant de sélectionner une option ou une autre, il sera toujours nécessaire de créer au moins deux boutons radio, et jamais un bouton isolé.

>[!CAUTION]
>
>Si vous souhaitez rendre la sélection obligatoire, vous devez créer une liste à choix multiples.

### Ajouter des boutons uniques {#add-single-buttons}

Pour ajouter un bouton radio dans une page de formulaire, sélectionnez le menu **[!UICONTROL Contrôles de saisie > Bouton radio]** dans la barre d&#39;outils de l&#39;éditeur de page et choisissez le mode de stockage.

![Onglet Général d&#39;un champ Bouton radio avec l&#39;option Libellé 1, Stockage des variables, Sélectionné par défaut et Valeur](assets/s_ncs_admin_survey_radio_button_sample.png)

Les boutons radio sont configurés de la même manière que les cases à cocher (voir [Ajouter des cases à cocher](#adding-checkboxes)). Toutefois, aucune valeur n&#39;est affectée si l&#39;option n&#39;est pas sélectionnée. Pour que plusieurs boutons soient interdépendants, c&#39;est-à-dire que le fait de les sélectionner désélectionne automatiquement les autres, ils doivent être stockés dans le même champ. S&#39;ils ne sont pas stockés dans la base de données, la même variable locale doit être utilisée pour le stockage temporaire. Voir [Champs de stockage des réponses](web-forms-answers.md#response-storage-fields).

### Ajouter une liste de boutons {#add-a-list-of-buttons}

Pour ajouter des boutons radio via une liste, sélectionnez le menu **[!UICONTROL Contrôles de sélection > Choix multiples]** dans la barre d&#39;outils de l&#39;éditeur de page.

![Champ à choix multiples Onglet général répertoriant les options 1 à 3 avec les colonnes Valeur, Sélectionné et Score](assets/s_ncs_admin_survey_radio_button_sample2.png)

Ajoutez autant de cases d’option que de libellés. L&#39;avantage de cette fonctionnalité est que vous pouvez importer les valeurs d&#39;un champ existant (s&#39;il s&#39;agit d&#39;un champ énuméré) et permettre à l&#39;utilisateur de choisir une option. En revanche, la disposition des boutons est moins souple.

>[!NOTE]
>
>Vous ne pouvez pas activer la sélection multiple dans une application web.
>Il est toutefois possible d&#39;insérer un champ de type **[!UICONTROL Choix multiple]** dans une application web, mais cela ne permettra pas à l&#39;utilisateur de sélectionner plusieurs valeurs.

## Ajouter des matrices {#adding-grids}

Les grilles servent à concevoir des pages de vote dans les applications web. Vous pouvez ainsi proposer des listes de cases d’option afin de répondre à des formulaires web de type questionnaire ou évaluation, comme dans l’exemple ci-dessous :

![Grille de classement générée avec vidéo 1 à vidéo 3 lignes et boutons radio de 1 médiocre à 5 excellent](assets/s_ncs_admin_survey_vote_param.png)

Pour intégrer des éléments de ce type dans un formulaire, vous devez créer une matrice simple et ajouter une ligne pour chaque élément à évaluer.

![Éditeur de page avec une grille simple Notes et trois lignes de grille, vidéo 1 à vidéo 3, et valeurs d&#39;évaluation de 1 à 5](assets/s_ncs_admin_survey_vote_sample.png)

Le nombre de boutons radio de chaque ligne de matrice correspond au nombre de valeurs définies dans la matrice simple.

![Grille générée avec une simple ligne d&#39;en-tête de grille 1 à 5 et trois lignes de grille, un bouton radio choisi par ligne](assets/s_ncs_admin_survey_vote_ex.png)

Dans chaque ligne de matrice, une seule option peut être sélectionnée.

>[!NOTE]
>
>Dans notre exemple, le libellé de la grille est masqué. Pour ce faire, accédez à l&#39;onglet **[!UICONTROL Avancé]**. L&#39;affichage de la **[!UICONTROL Position du libellé]** est défini sur **[!UICONTROL Caché]**. Voir [Définir la position des libellés](defining-web-forms-layout.md#defining-the-position-of-labels).

## Ajouter des dates et des nombres {#adding-dates-and-numbers}

Le contenu des champs du formulaire peut être mis en forme afin de correspondre aux données stockées dans la base ou de répondre à un besoin spécifique. Vous pouvez créer des champs adaptés pour la saisie de nombres et de dates.

### Ajouter des dates {#adding-dates}

![Champ de date avec le sélecteur de calendrier ouvert en janvier 2017 et un jour sélectionné](assets/s_ncs_admin_survey_date_calendar.png)

Pour permettre à l&#39;utilisateur de saisir une date dans une page de formulaire, ajoutez un champ de saisie et sélectionnez le type **[!UICONTROL Date...]**.

Indiquez le libellé du champ et le mode de stockage des données.

![Onglet Général d’un champ Date de naissance de type Date, avec les listes déroulantes Format de la date et Format de l’heure](assets/s_ncs_admin_survey_date_edit.png)

La section inférieure de la fenêtre permet de sélectionner les formats de date et d&#39;heure pour les valeurs renseignées dans ce champ.

![Formats de liste déroulante du format des dates, tels que 12/31/12, 31 décembre 2012 et 31 décembre 2012](assets/s_ncs_admin_survey_date_edit_values.png)

Vous pouvez également choisir de ne pas afficher la date (ou l&#39;heure).

Les dates peuvent être sélectionnées via un calendrier ou des listes déroulantes. Vous pouvez aussi les saisir directement dans le champ. Toutefois, elles doivent respecter le format spécifié dans l’écran ci-dessus.

>[!NOTE]
>
>Par défaut, les dates utilisées dans les formulaires sont saisies via un calendrier. Dans le cadre de formulaires multilingues, nous vous invitons à vérifier que les calendriers sont disponibles pour toutes les langues utilisées. Voir [Traduire un formulaire web](translating-a-web-form.md).

Toutefois, il peut être plus adapté, par exemple pour indiquer une date de naissance, d&#39;utiliser des listes déroulantes.

![Champ de date de naissance généré à l&#39;aide de trois listes déroulantes pour le jour, le mois et l&#39;année](assets/s_ncs_admin_survey_date_list_select.png)

Pour cela, cliquez sur l&#39;onglet **[!UICONTROL Avancé]** et choisissez un mode de saisie par **[!UICONTROL Listes déroulantes]**.

![Onglet Avancé avec le menu déroulant Mode de saisie configuré pour choisir la saisie de date à l&#39;aide d&#39;un calendrier ou de listes déroulantes](assets/s_ncs_admin_survey_date_selection.png)

Vous pouvez alors borner les valeurs proposées dans la liste.

![Onglet Général du champ de date avec les cases Première année et Dernière année limitant les années proposées dans les listes](assets/s_ncs_admin_survey_date_first_last_y.png)

### Ajouter des nombres {#adding-numbers}

Vous pouvez créer des champs adaptés pour la saisie de nombres.

![Champ numérique rendu intitulé Points contenant la valeur 2 500](assets/s_ncs_admin_survey_number.png)

Dans un champ numérique, l’utilisateur ou l’utilisatrice ne peut saisir que des chiffres. Un contrôle de saisie est automatiquement appliqué lors de l’approbation de la page.

En fonction du champ de stockage des données dans la base, une mise en forme spécifique ou certaines restrictions peuvent être appliquées. Vous pouvez également définir des valeurs minimales et maximales. Le paramétrage de ce type de champ est le suivant :

![Onglet Général du champ Nombre avec les options Valeur par défaut, Valeur minimale et Valeur maximale d&#39;approbation](assets/s_ncs_admin_survey_number_edit.png)

La valeur par défaut est la valeur affichée dans le champ lors de la publication du formulaire. Elle peut être corrigée par l’utilisateur ou l’utilisatrice.

Vous pouvez ajouter un préfixe et/ou un suffixe au champ numérique, à partir de l&#39;onglet **[!UICONTROL Avancé]**, comme dans l&#39;exemple suivant :

![Onglet Avancé d&#39;un champ numérique avec Préfixe défini sur Vous avez et Suffixe défini sur points](assets/s_ncs_admin_survey_number_ex_conf.png)

Dans le formulaire, le rendu sera :

![Champ numérique rendu indiquant le préfixe que vous avez, la valeur 10 et le suffixe points](assets/s_ncs_admin_survey_number_ex.png)

## Cases à cocher d&#39;abonnement {#subscription-checkboxes}

Vous pouvez ajouter des contrôles pour permettre aux utilisateurs et utilisatrices de s’abonner à un ou plusieurs services d’information (newsletters, alertes, notifications en temps réel, etc.) ou de se désabonner. Pour s’abonner, la personne coche le service correspondant.

Pour créer une case à cocher d&#39;abonnement, cliquez sur **[!UICONTROL Contrôles avancés > Abonnement]**.

![Onglet Général du champ Abonnement avec la liste déroulante Service répertoriant les services d&#39;informations à sélectionner](assets/s_ncs_admin_survey_subscription_edit.png)

Indiquez le libellé de la case à cocher et sélectionnez le service d&#39;information concerné dans la liste déroulante **[!UICONTROL Service]**.

>[!NOTE]
>
>Les services d&#39;informations sont présentés dans cette [page](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions){target="_blank"}.

L&#39;utilisateur sera abonné au service spécifié s&#39;il coche l&#39;option correspondante.

![Formulaire de confirmation de profil rendu et de sélection de newsletters avec cases à cocher de newsletter et bouton Valider](assets/s_ncs_admin_survey_subscribe.png)

>[!CAUTION]
>
>Si l&#39;utilisateur est déjà abonné à un service d&#39;information et que la case correspondant à ce service est décochée lorsqu&#39;il valide le formulaire, il sera alors désabonné.

## Insérer un captcha {#inserting-a-captcha}

Les **captcha** permettent de prévenir l&#39;utilisation frauduleuse de vos formulaires Web.

>[!CAUTION]
>
>Si votre formulaire est composé de plusieurs pages, le Captcha doit toujours être positionné dans la dernière page, immédiatement avant la boîte d&#39;enregistrement, afin de prévenir tout contournement de la sécurité.

Pour insérer un Captcha dans un formulaire, cliquez sur le premier bouton de la barre d&#39;outils et sélectionnez **[!UICONTROL Contrôles avancés>Captcha]**.

![Menu de la barre d&#39;outils Contrôles avancés répertoriant Fichier, Abonnement, Constant et Captcha, avec Captcha en surbrillance](assets/s_ncs_admin_survey_add_captcha.png)

Saisissez le libellé du champ. Ce libellé sera affiché devant la zone d’affichage du captcha. Vous pouvez modifier le positionnement de ce libellé à partir de l&#39;onglet **[!UICONTROL Avancé]**.

![Onglet Avancé Captcha avec la liste déroulante Position du libellé offrant Hérité, Gauche, Droite, Au-dessus, En dessous, Masqué](assets/s_ncs_admin_survey_captcha_adv.png)

>[!NOTE]
>
>Pour les contrôles de type **[!UICONTROL captcha]**, il n&#39;est pas nécessaire d&#39;indiquer de champ ou variable de stockage.

Le captcha est inséré dans la page avec un champ de saisie placé sous le visuel. Ces deux éléments sont indissociables : pour la mise en page, ils sont considérés comme un seul élément (ils n’occupent qu’une seule cellule).

![Page de formulaire générée avec une image captcha de caractères déformés et un champ de saisie en dessous](assets/s_ncs_admin_survey_captcha_sample.png)

Lors de la validation de la page, le champ de saisie est affiché en rouge si le contenu du Captcha n&#39;a pas été saisi correctement.

![Page de formulaire affichant un message d&#39;erreur rouge indiquant que les caractères saisis doivent correspondre à l&#39;image captcha](assets/s_ncs_admin_survey_captcha_error.png)

Vous pouvez créer un message d’erreur à afficher. Pour cela, utilisez le lien **[!UICONTROL Personnaliser le message]** dans l’onglet **[!UICONTROL Général]**.

![Onglet Général de Captcha avec le lien Personnaliser le message ouvrant la boîte de dialogue Personnalisation du message](assets/s_ncs_admin_survey_captcha_error_msg.png)

>[!NOTE]
>
>Les captchas font toujours 8 caractères. Vous ne pouvez pas modifier cette valeur.

## Télécharger un fichier {#uploading-a-file}

Vous pouvez ajouter un champ de chargement à une page. Cette fonctionnalité peut être utile, par exemple dans le contexte d’un intranet, afin de partager des fichiers.

![Champ de chargement généré intitulé Charger votre image avec un bouton Parcourir](assets/s_ncs_admin_survey_download_file.png)

Pour ajouter un champ de téléchargement dans une page de formulaire, sélectionnez le menu **[!UICONTROL Contrôles avancés > Fichier...]** dans la barre d&#39;outils de l&#39;éditeur de page.

Par défaut, les fichiers chargés sont stockés dans des fichiers de ressources accessibles via le menu **[!UICONTROL Ressources > En ligne > Ressources publiques]**. Vous pouvez utiliser un script pour modifier ce comportement. Ce script peut utiliser les fonctions définies dans la [documentation JSAPI Campaign](https://experienceleague.adobe.com/fr/tools/campaign-api) notamment celles relatives à la manipulation des fichiers.

Vous pouvez stocker le lien vers ces fichiers dans une variable locale ou dans un champ de base de données. Vous pouvez, par exemple, étendre le schéma des destinataires afin d’ajouter un lien vers les ressources fichiers.

>[!CAUTION]
>
>* Ce type de champ doit être réservé aux formulaires dont l&#39;accès est sécurisé (à l’aide d’informations d’identification).
>* Adobe Campaign n&#39;applique aucun contrôle sur la taille ou le type de ressource téléchargée : il est donc vivement recommandé de n&#39;utiliser les champs de téléchargement que pour les sites de type intranet sécurisé.
>* Lorsque plusieurs serveurs sont associés à l&#39;instance (architecture « load balancing »), vous devez vous assurer que les appels au formulaire web arrivent sur le même serveur.
>* Ce type d&#39;implémentation peut nécessiter l&#39;intervention de l&#39;équipe Consulting d&#39;Adobe Campaign.
>

## Insérer une constante masquée {#inserting-a-hidden-constant}

Lorsque l’utilisateur valide l’une des pages du formulaire, vous pouvez définir une valeur spécifique pour un champ de son profil ou une variable.

Ce champ n‘est pas visible par l‘utilisateur mais permet d‘enrichir les données de son profil.

Pour ce faire, placez une **constante** dans la page et indiquez la valeur et l&#39;emplacement de stockage.

Dans l&#39;exemple suivant, le champ **origine** du profil du destinataire est renseigné automatiquement chaque fois qu&#39;un utilisateur valide cette page. La constante n&#39;est pas affichée sur la page.

![Champ constant nommé Origin, stocké dans le champ de base de données d&#39;origine, avec la valeur Externe](assets/s_ncs_admin_survey_constante.png)
