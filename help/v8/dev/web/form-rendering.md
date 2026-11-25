---
product: campaign
title: Rendu du formulaire
description: Rendu du formulaire
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 723a6c47-5323-4914-a014-58be493852cc
TQID: 'https://experienceleague.adobe.com/zLf1lFV9vVIHcEbfO5UrFo92epuVlfMUWrl64SqNfCQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
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
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 77%
---
# Rendu du formulaire{#form-rendering}



## Choisir le modèle de rendu du formulaire {#selecting-the-form-rendering-template}

Les paramètres du formulaire permettent de sélectionner le modèle utilisé pour générer les pages. Pour y accéder, cliquez sur le bouton **[!UICONTROL Propriétés]** dans la barre d’outils des détails du formulaire, puis sélectionnez l’onglet **[!UICONTROL Rendu]**. Plusieurs modèles (feuilles de style) sont disponibles par défaut.

![Onglet de rendu des propriétés du formulaire avec la liste Modèle ouverte, affichant le formulaire standard et le thème 1 au thème 7.](assets/s_ncs_admin_survey_rendering_select.png)

La section inférieure de l&#39;éditeur permet de visualiser un exemple de rendu du modèle sélectionné.

La loupe permet d&#39;éditer le modèle sélectionné.

![Boîte de dialogue du thème 5 du modèle de génération de formulaire avec le lien de mise en page et les paramètres CSS.](assets/s_ncs_admin_survey_render_edit.png)

Vous pouvez modifier ou remplacer ces modèles. Pour cela, cliquez sur le lien **[!UICONTROL Mise en page]** et personnalisez les informations.

![Boîte de dialogue Disposition de page, onglet Propriétés, avec image du logo, largeur et hauteur, et chemin d&#39;accès à l&#39;image d&#39;aperçu.](assets/s_ncs_admin_survey_render_edit_param.png)

Vous pouvez ainsi :

* Modifier l&#39;image utilisée comme logo et adapter sa taille,
* Indiquer également le chemin d&#39;accès à l&#39;image d&#39;aperçu proposée aux utilisateurs lorsqu&#39;ils sélectionnent ce modèle de rendu.

L&#39;onglet **[!UICONTROL En-têtes/Pieds]** permet de modifier les informations affichées en en-tête et pied de page de chacune des pages des formulaires utilisant ce modèle.

![Boîte de dialogue Disposition de page, onglet En-têtes/pieds de page, avec des lignes d&#39;en-têtes de page et de pieds de page et des champs Position.](assets/s_ncs_admin_survey_render_edit_header.png)

Chaque ligne des sections **[!UICONTROL En-têtes de page]** et **[!UICONTROL Pieds de page]** correspond à une ligne dans la page HTML. Cliquez sur **[!UICONTROL Ajouter]** pour créer une nouvelle ligne.

Sélectionnez une ligne existante et cliquez sur le bouton **[!UICONTROL Détail]** pour la personnaliser.

![Boîte de dialogue détaillée des en-têtes de page avec les onglets Mise en page, Bordures et Police et contenu des zones gauche et droite.](assets/s_ncs_admin_survey_render_edit_header_detail.png)

Vous pouvez modifier le contenu de la ligne, ajouter des bordures et changer les attributs de la police de caractères utilisée à partir des onglets correspondants. Cliquez sur **[!UICONTROL OK]** pour valider ces modifications.

Les champs **[!UICONTROL Position]** permettent de définir la position des éléments dans l&#39;en-tête et dans le pied de page.

![Onglet En-têtes/pieds de page avec les listes Position des en-têtes et pieds de page, offrant Masqué, En dehors de la page, Dans la page.](assets/s_ncs_admin_survey_render_edit_header_position.png)

>[!NOTE]
>
>Les modèles de rendus sont stockés dans le nœud **[!UICONTROL Administration > Paramétrage > Rendus des formulaires]**.\
>Pour plus d&#39;informations, voir la section [Personnaliser le rendu du formulaire](#customizing-form-rendering).

## Personnaliser le rendu du formulaire {#customizing-form-rendering}

### Adapter la disposition des éléments {#changing-the-layout-of-elements}

Vous pouvez surcharger la feuille de style au niveau de chaque élément du formulaire (champs de saisie, images, boutons radio, etc.).

Pour cela, utilisez l&#39;onglet **[!UICONTROL Avancé]**.

![Onglet avancé d’un élément de formulaire avec des paramètres d’affichage tels que le nombre de cellules et l’alignement vertical.](assets/s_ncs_admin_survey_advanced_tab.png)

Il permet de définir les propriétés suivantes :

* **[!UICONTROL Position du libellé]** : voir [Définir la position des libellés](defining-web-forms-layout.md#defining-the-position-of-labels),
* **[!UICONTROL Format du libellé]** : Retour à la ligne ou Pas de retour à la ligne,
* **[!UICONTROL Nombre de cellules]** : voir la section [Placer les champs de la page](defining-web-forms-layout.md#positioning-the-fields-on-the-page),
* **[!UICONTROL Alignement horizontal]** (Gauche, Droite, Centré) et **[!UICONTROL vertical]** (Haut, Bas, Milieu),
* **[!UICONTROL Largeur]** de la zone : elle peut être exprimée en pourcentage, en em, en points ou en pixels (valeur par défaut),
* **[!UICONTROL Longueur]** maximale : nombre de caractères maximum autorisé (pour un contrôle de type Texte, Nombre, Mot de passe),
* **[!UICONTROL Lignes]** : nombre de lignes pour une zone de type **[!UICONTROL Texte Multi-lignes]**,
* **[!UICONTROL Style intégré]** : permet de surcharger la feuille de style CSS avec des paramètres supplémentaires. Ces derniers sont séparés à l’aide des caractères **;** comme illustré dans l’exemple ci-dessous :

  ![Onglet avancé avec la valeur Style intégrée définie sur font-size:16pt ; arrière-plan : bleu.](assets/s_ncs_admin_survey_advanced_tab_inline.png)

### Définir les en-têtes et pieds de page {#defining-headers-and-footers}

Les champs sont enchaînés dans une arborescence dont la racine porte le nom de la page. Sélectionnez-la pour modifier ce nom.

Le titre de la fenêtre doit être saisi dans l’onglet **[!UICONTROL Page]** de la fenêtre des propriétés du formulaire. Vous pouvez également ajouter un contenu défini à l’en-tête et au pied-de-page (ces informations s’affichent sur chaque page). Ce contenu doit être saisi dans les sections correspondantes de l&#39;onglet **[!UICONTROL Textes]**, comme dans l&#39;exemple ci-dessous :

![Onglet Page des propriétés du formulaire avec le titre de la fenêtre, l&#39;en-tête et le pied de page.](assets/s_ncs_admin_survey_titles_config.png)

### Ajouter des éléments dans l&#39;en-tête HTML {#adding-elements-to-html-header}

Vous pouvez saisir des élément additionnels à insérer dans l&#39;en-tête HTML d&#39;une page de formulaire. Pour cela, saisissez ces éléments dans l&#39;onglet **[!UICONTROL En-tête]** de la page visée.

Ainsi, par exemple, vous pouvez y référencer une icône qui sera affichée dans la barre de titre de la page.

![Onglet En-tête de page avec un élément de lien pour une icône de raccourci ajoutée à l’en-tête HTML.](assets/webform_header_page_tab.png)

## Définir les paramètres de contrôle {#defining-control-settings}

Lorsque l&#39;utilisateur renseigne le formulaire, une vérification de certains champs est automatiquement effectuée selon leur format ou leur configuration. Vous pouvez ainsi rendre certains champs obligatoires (voir la section [Définir les champs obligatoires](#defining-mandatory-fields)) ou vérifier le format des données saisies (voir la section [Contrôler le format des données](#checking-data-format)). Les vérifications sont effectuées lors de la validation de la page (en cliquant sur un lien ou un bouton qui active une transition de sortie).

### Définir les champs obligatoires {#defining-mandatory-fields}

Pour rendre obligatoire le renseignement d&#39;un champ, vous devez cocher l&#39;option correspondante lors de la création du champ.

![Onglet Général du champ avec l&#39;option Obligatoire activée pour le champ Nom.](assets/s_ncs_admin_survey_required_field.png)

Lorsque l’utilisateur ou l’utilisatrice valide la page, si le champ n’est pas renseigné, le message d’erreur sera le suivant :

![Page de formulaire affichant le message d&#39;erreur par défaut Le champ &#39;Nom&#39; est obligatoire, avec le champ vide en surbrillance.](assets/s_ncs_admin_survey_required_default_msg.png)

Vous pouvez personnaliser ce message en cliquant sur le lien **[!UICONTROL Personnaliser ce message]**.

![La boîte de dialogue de personnalisation des messages s’est ouverte à partir de Personnaliser le message avec du texte personnalisé pour un champ obligatoire vide.](assets/s_ncs_admin_survey_required_custom_msg.png)

Lorsque l’utilisateur ou l’utilisatrice valide la page, si le champ n’est pas renseigné, le message d’erreur sera le suivant :

![Page de formulaire affichant le message CHAMP OBLIGATOIRE personnalisé au-dessus du champ vide mis en surbrillance.](assets/s_ncs_admin_survey_required_custom_msg2.png)

### Contrôler le format des données {#checking-data-format}

Pour les contrôles du formulaire dont les valeurs seront stockées dans un champ existant de la base de données, les règles du champ de stockage sont appliquées.

Pour les contrôles du formulaire dont les valeurs seront stockées dans une variable, les règles de validation dépendent du format de la variable.

Par exemple, si vous créez un contrôle de type **[!UICONTROL Nombre]** pour stocker le numéro du client, comme dans l&#39;exemple suivant :

![Champ de type Nombre stockant sa valeur dans une variable client, avec boîtes de dialogue Stockage et Modifier les branches affichant le type Entier.](assets/s_ncs_admin_survey_choose_format.png)

L&#39;utilisateur devra saisir un nombre entier dans le champ correspondant du formulaire.

## Définir l&#39;affichage conditionnel des champs {#defining-fields-conditional-display}

Vous pouvez configurer l’affichage des champs de la page en fonction des valeurs choisies par l’utilisateur ou l’utilisatrice. Cela peut s’appliquer à un champ ou à un groupe de champs (lorsqu’ils sont regroupés dans un conteneur).

Pour chaque élément de la page, la section **[!UICONTROL Visibilité]** permet de définir la ou les conditions d&#39;affichage.

![Onglet Général du conteneur avec le lien Modification de la visibilité ouvrant la boîte de dialogue Condition de visibilité.](assets/s_ncs_admin_survey_condition_edit.png)

Les conditions peuvent porter sur la valeur de champs de la base ou de variables.

Dans la fenêtre de sélection d&#39;un champ, vous pouvez sélectionner parmi les données disponibles :

![Sélectionnez une boîte de dialogue de champ affichant l&#39;arborescence contextuelle avec l&#39;identifiant, la langue, l&#39;origine, les destinataires et les variables.](assets/s_ncs_admin_survey_condition_select.png)

* L’arborescence principale contient les paramètres du contexte du formulaire. Les paramètres par défaut sont Identifiant (qui correspond à l’identifiant chiffré de la personne destinataire), Langue et Origine.

  Voir à ce propos [cette page](defining-web-forms-properties.md#form-url-parameters).

* La sous-arborescence **[!UICONTROL Destinataires]** contient les champs de saisie insérés dans le formulaire et stockés dans la base de données.

  Pour plus d&#39;informations, voir la section [Stockage des données dans la base de données](web-forms-answers.md#storing-data-in-the-database).

* La sous-arborescence **[!UICONTROL Variables]** contient les variables disponibles pour ce formulaire. Pour plus d&#39;informations, voir la section [Stocker les données dans une variable locale](web-forms-answers.md#storing-data-in-a-local-variable).

Pour plus d&#39;informations, reportez-vous au cas d&#39;utilisation disponible ici : [Afficher différentes options en fonction de la valeur sélectionnée](use-cases-web-forms.md#displaying-different-options-depending-on-the-selected-values).

Vous pouvez aussi conditionner l&#39;affichage des pages du formulaire via l&#39;objet **[!UICONTROL Test]**. Pour en savoir plus à ce sujet, consultez cette [page](defining-web-forms-page-sequencing.md#conditional-page-display).

## Importer des éléments depuis un formulaire existant {#importing-elements-from-an-existing-form}

Il est possible d’importer des champs ou des conteneurs à partir d’autres formulaires web. Ainsi, vous pouvez créer une bibliothèque de blocs réutilisables qui seront insérés dans les formulaires, par exemple le bloc adresse, la zone d’inscription aux newsletters, etc.

Pour importer un élément dans un formulaire, les étapes sont les suivantes :

1. Editez la page dans laquelle vous souhaitez inclure un ou plusieurs éléments et cliquez sur le bouton **[!UICONTROL Importer un bloc existant]** de la barre d&#39;outils.

   ![Barre d&#39;outils de l&#39;éditeur de page avec le bouton Importer un bloc existant en surbrillance.](assets/s_ncs_admin_survey_import_block.png)

1. Sélectionnez le formulaire Web contenant les champs à importer et choisissez les conteneurs et les champs à importer.

   ![Importez une boîte de dialogue de bloc existante avec une application Web source et les blocs à importer sont vérifiés.](assets/s_ncs_admin_survey_import_block_selection.png)

   >[!NOTE]
   >
   >L&#39;icône **[!UICONTROL Editer le lien]** située à droite du nom du formulaire source permet de visualiser le formulaire Web sélectionné.

1. Cliquez sur **[!UICONTROL Ok]** pour valider l&#39;insertion des éléments.

   ![Arborescence de pages après l&#39;importation, contenant désormais les champs Nom, Pays, N° de compte et E-mail.](assets/s_ncs_admin_survey_import_block_rendering.png)
