---
product: campaign
title: Gestion des réponses
description: Découvrez comment gérer les réponses aux questionnaires
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 0b5dc602-e16f-4bf1-bd8f-352e0bc78996
TQID: 'https://experienceleague.adobe.com/-xjK3nxUc4Lz-mWyVoUbbIJ8HQvyLRInYk-w8zYLYE4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 74%
---
# Gestion des réponses{#managing-answers}

>[!AVAILABILITY]
>
>Les questionnaires ne sont pas disponibles pour les [déploiements de Campaign FFDA](../../architecture/enterprise-deployment.md).



## Stocker les réponses collectées {#storing-collected-answers}

En complément des modes de stockage standard communs à tous les formulaires Web sous Adobe Campaign (champ de la base et variable locale), les questionnaires permettent l&#39;extension dynamique du modèle de données au travers de champs archivés.

>[!CAUTION]
>
>Cette option n’est disponible que pour les formulaires web de type **Questionnaire**. Elle n’est pas proposée pour d’autres types de formulaires web.

### Stocker les réponses dans un champ archivé {#storing-in-an-archived-field}

Il est facile d&#39;étendre le modèle de données en ajoutant de nouveaux espaces de stockage pour enregistrer les réponses fournies dans les questionnaires. Pour cela, sélectionnez l&#39;option **[!UICONTROL Stocker les réponses à une question]** lors de la création du champ de saisie. Cliquez sur le bouton **[!UICONTROL Nouveau champ]** et indiquez ses propriétés :

![Boîte de dialogue de stockage avec Stocker les réponses à une question sélectionnée et la boîte de dialogue Créer un champ archivé pour un champ Contrat.](assets/s_ncs_admin_survey_new_space.png)

Saisissez le libellé et le nom du champ, puis sélectionnez le type de champ : Texte, Booléen, Nombre entier ou à virgule, Date, etc.

Le type de champ sélectionné implique un contrôle des données lors de la saisie des réponses par les utilisateurs. Pour les champs de **texte**, vous pouvez ajouter une contrainte (casse, format) ou un lien vers une énumération existante pour forcer la sélection.

Pour ajouter une contrainte, sélectionnez-la dans la liste déroulante. Deux types de contraintes existent :

1. Sur la casse des caractères

   Les informations saisies peuvent être stockées dans le champ dans les formats suivants : tout en majuscule, tout en minuscule ou avec la première lettre en majuscule. Cette contrainte n’oblige pas l’utilisateur ou l’utilisatrice à saisir les informations dans le format sélectionné, mais le contenu saisi dans le champ sera transformé lors de l’enregistrement.

1. Sur le format des données saisies

Si ce champ est utilisé dans une liste, les valeurs de l’énumération pourront être récupérées automatiquement dans le tableau des valeurs à partir du lien **[!UICONTROL Initialiser la liste des valeurs depuis la base de données]** situé au-dessus de la liste des valeurs.

Vous pouvez par exemple créer une liste déroulante dans laquelle l’utilisateur pourra sélectionner sa langue maternelle. Le champ archivé correspondant peut être associé à l’énumération **langue** contenant une liste de langues :

![Créez une boîte de dialogue de champ archivée avec l&#39;énumération de langue sélectionnée et l&#39;icône Modifier le lien mise en surbrillance.](assets/s_ncs_admin_survey_database_values_2b.png)

L&#39;icône **[!UICONTROL Editer le lien]** située à droite du champ permet d&#39;éditer le contenu de cette énumération :

![Éditeur de langue d&#39;énumération (langue) répertoriant les valeurs Anglais, Français et Allemand.](assets/s_ncs_admin_survey_database_values_2c.png)

Dans l&#39;onglet **[!UICONTROL Général]** du champ, le lien **[!UICONTROL Initialiser la liste des valeurs depuis la base de données]** permet de renseigner automatiquement la liste des libellés proposés.

![Onglet Général du champ déroulant, Initialiser la liste des valeurs à partir du lien de base de données remplissant les libellés de langue.](assets/s_ncs_admin_survey_database_values_2.png)

**Exemple** : stocker tous les contrats d&#39;un destinataire dans un même champ

Pour stocker les types de contrats d&#39;un utilisateur dans un même champ, créez un champ de saisie de type **[!UICONTROL Texte]** et sélectionnez l&#39;option **[!UICONTROL Stocker les réponses à une question]**.

Cliquez sur le lien **[!UICONTROL Nouveau champ]** et saisissez les propriétés du champ. Sélectionnez l&#39;option **[!UICONTROL Valeurs multiples]** afin de permettre le stockage de plusieurs valeurs.

![Boîte de dialogue Créer un champ archivé pour les contrats avec l&#39;option Valeurs multiples sélectionnée.](assets/s_ncs_admin_survey_storage_multi_ex1.png)

Créez les champs de saisie des autres contrats, et stockez les informations dans le même champ archivé.

![Boîte de dialogue de stockage et sélecteur de champ liant un champ de saisie au champ archivé Contrats.](assets/s_ncs_admin_survey_storage_multi_ex2.png)

Lorsque l&#39;utilisateur valide le questionnaire, ses réponses sont stockées dans le champ **[!UICONTROL Contrats]**.

Dans notre exemple, pour les réponses suivantes :

![Page d&#39;enquête sur les contrats avec quatre champs de contrat remplis avec les valeurs M, L, T et V.](assets/s_ncs_admin_survey_storage_multi_ex3.png)

Le profil du répondant contiendra les quatre contrats renseignés.

Vous pouvez les visualiser dans l&#39;onglet **[!UICONTROL Réponses]** du questionnaire, en affichant les colonnes correspondantes.

![Onglet Réponses répertoriant les réponses avec les colonnes Contrat_1 à Contrat_4 affichant les valeurs des réponses à plusieurs valeurs.](assets/s_ncs_admin_survey_storage_multi_ex4.png)

Vous pouvez également filtrer les destinataires en fonction des réponses fournies pour n&#39;afficher que les utilisateurs recherchés. Pour cela, créez un workflow de ciblage et utilisez la boîte **[!UICONTROL Réponses à un questionnaire]**.

![Workflow de ciblage avec l&#39;activité Réponses à un questionnaire glissée de la palette Ciblage vers le diagramme.](assets/s_ncs_admin_survey_read_responses_wf.png)

Créez votre requête en fonction des profils que vous souhaitez récupérer. Dans l’exemple ci-dessous, la requête vous permet de sélectionner les profils ayant au moins deux contrats dont un contrat de type A.

![L&#39;activité Réponses à un questionnaire et sa boîte de dialogue de requête filtrent sur Contract_1 égal à E et Contract_2 égal à R.](assets/s_ncs_admin_survey_read_responses_edit.png)

Pour chaque formulaire, les réponses fournies peuvent être réutilisées dans les champs ou les libellés. Utilisez la syntaxe suivante pour le contenu stocké dans un champ archivé :

```html
<%= ctx.webAppLogRcpData.name of the archived field %
```

>[!NOTE]
>
>Pour les autres types de champs, la syntaxe à utiliser est présentée dans [cette section](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/data/query/query-editor){target="_blank"} (documentation de Campaign v8).

### Paramètres de stockage {#storage-settings}

Vous pouvez archiver les réponses aux questionnaires au format XML. Vous pouvez ainsi conserver une copie brute des réponses collectées, ce qui peut s&#39;avérer utile en cas de normalisation excessive des données dans une liste détaillée d&#39;informations. [En savoir plus](publish-track-and-use-collected-data.md#standardizing-data)

>[!CAUTION]
>
>L&#39;archivage des réponses brutes affecte l&#39;espace de stockage requis. Utilisez cette option avec précaution.

Pour cela :

* Editez les propriétés du questionnaire à partir du bouton **[!UICONTROL Propriétés]** de l&#39;onglet **[!UICONTROL Edition]**.
* Cliquez sur le lien **[!UICONTROL Paramètres avancés]** et cochez l&#39;option **[!UICONTROL Conserver une copie des réponses brutes]**.

![Boîte de dialogue Paramètres avancés de l&#39;application Web avec l&#39;option Enregistrer une copie des réponses brutes sélectionnée.](assets/s_ncs_admin_survey_xml_archive_option.png)

Vous pouvez l&#39;activer par défaut pour tous les questionnaires (cette option est appliquée à la publication du questionnaire). Pour ce faire, créez l’option **[!UICONTROL NmsWebApp_XmlBackup]** et affectez-lui la valeur **[!UICONTROL 1]**, comme illustré ci-dessous :

![Nœud Options dans Administration, Plateforme avec l&#39;option NmsWebApp_XmlBackup créée avec la valeur 1.](assets/s_ncs_admin_survey_xml_global_option.png)

## Gestion des scores {#score-management}

Vous pouvez attribuer un score aux options proposées dans les pages du formulaire. Les scores ne peuvent être associés qu’à des questions fermées : case à cocher, valeur d’une liste déroulante, abonnement, etc.

![Onglet Général du champ de zone de liste déroulante répertoriant les valeurs des cartes de fidélité de standard à VIP avec une colonne Score comprise entre 2.00 et 10.00.](assets/s_ncs_admin_survey_score_create.png)

Les scores sont cumulés et sauvegardés côté serveur, au moment de la validation de la page, c&#39;est-à-dire lorsque l&#39;utilisateur clique sur un bouton **[!UICONTROL Suivant]** ou **[!UICONTROL Terminer]**.

>[!NOTE]
>
>Vous pouvez utiliser des valeurs positives ou négatives, entières ou non.

Les scores peuvent être utilisés dans des tests et dans des scripts.

>[!CAUTION]
>
>Les scores ne peuvent pas être utilisés dans les conditions de visibilité pour les champs d’une même page. Ils peuvent toutefois être utilisés dans les pages suivantes.

* Pour utiliser les scores dans des tests, vous devez utiliser le champ **[!UICONTROL Score]** dans la formule de calcul du test, comme dans l&#39;exemple ci-dessous :

  ![Activité de test avec une condition sur le score supérieur à 6, en sélectionnant le champ Score dans le document contextuel.](assets/s_ncs_admin_survey_score_in_a_test.png)

* Vous pouvez utiliser le score dans un script.

**Exemple** : calculer un score et conditionner l&#39;affichage de la page suivante :

* Dans un questionnaire, la page suivante permet d&#39;attribuer un score différent à l&#39;utilisateur en fonction de la valeur sélectionnée dans la liste déroulante :

  ![Champ déroulant des niveaux de classe, de l&#39;école maternelle à l&#39;université, avec des scores de 2.00 à 7.00.](assets/s_ncs_admin_survey_score_exa.png)

* Vous pouvez cumuler ce score avec une seconde valeur, en fonction de l&#39;option sélectionnée :

  ![Champ à choix multiples Vous êtes... avec un parent ayant obtenu une note de 7,00 et un élève ayant obtenu une note de 2,00.](assets/s_ncs_admin_survey_score_exb.png)

* Lorsque l&#39;utilisateur clique sur le bouton **[!UICONTROL Suivant]**, les deux valeurs sont additionnées.

  ![Page d&#39;accueil avec le niveau Junior élevé sélectionné dans la liste Niveau et l&#39;option Parent sélectionnée sous Statut.](assets/s_ncs_admin_survey_score_exe.png)

* Des conditions peuvent être appliquées pour la page à afficher en fonction du score. Elle est configurée comme suit :

  ![Activité de test avec une condition de branche Modifier : score supérieur à 7.00.](assets/s_ncs_admin_survey_score_exd.png)

  ![L’activité de test atteint le niveau 1 lorsque le score est inférieur à 7, le niveau 2 lorsqu’il est égal à 7 et le niveau 3 lorsqu’il est supérieur à 7.](assets/s_ncs_admin_survey_score_exg.png)
