---
title: Prise en main des profils
description: Prise en main des profils
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
version: Campaign v8, Campaign Classic v7
TQID: 'https://experienceleague.adobe.com/lOHi9m2uufIl3Qk5z-vJUVMkBJE3hHOmGjiebKKiZqo'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 8ab3ced33b95f977032d9f0ffccd1dc50c7a59e8
workflow-type: tm+mt
source-wordcount: '4821'
ht-degree: 84%
---
# Import de données dans Campaign {#ootb-profiles}

Campaign vous aide à ajouter des contacts à la base de données. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour des contacts, collecter des données sur le Web ou saisir des informations de profil directement dans la table des destinataires.

Les imports de profils sont configurés dans des modèles dédiés, exécutés par le biais de workflows via l&#39;activité **Import**. Ils peuvent être répétés automatiquement selon un planning, par exemple pour automatiser l&#39;échange de données entre plusieurs systèmes d&#39;informations. Pour en savoir plus, consultez la section [Configurer un import récurrent](../../automation/workflow/recurring-import-workflow.md).

![Workflow de mise à jour des profils : contacts mis à jour et flux de lecture Exclusion, puis Déduplication, puis Mise à jour des données.](assets/import-wf.png)

## Exécution d’un import

Adobe Campaign vous permet d&#39;importer des données dans la base de données à partir d&#39;un ou de plusieurs fichiers au format texte, CSV, TAB ou XML. Ces fichiers sont associés à une table (principale ou liée) et chaque champ du ou des fichier(s) source est associé à un champ de la base de données.

>[!NOTE]
>
>Vous pouvez importer des données sans les mapper aux données de la base en utilisant la fonction **[!UICONTROL Importer une liste]**. Les données seront alors utilisables exclusivement dans les workflows via l&#39;objet **[!UICONTROL Lecture de liste]**. Pour plus d&#39;informations, consultez la section [Lecture de liste](../../automation/workflow/read-list.md).


## Utilisation de l’assistant d’importation

L’assistant d’import vous permet de configurer un import, de définir ses options (comme la transformation de données) et de lancer son exécution. Il s’agit d’une série d’écrans dont le contenu dépend du type d’import (simple ou multiple) et des droits de l’opérateur ou de l’opératrice.

L’assistant d’import s’affiche après la création d’un traitement d’import.

![Liste des tâches avec le menu Créer affichant Nouvelle importation et Nouvelle exportation, et la boîte de dialogue Fichier à importer de l&#39;assistant d&#39;importation.](assets/new-import.png)

Dans le fichier source, chaque ligne correspond à un enregistrement. Les données des enregistrements sont séparées les unes des autres par un délimiteur (espace, tabulation, caractère, etc.). Les données sont ainsi récupérées sous forme de colonnes et chaque colonne est associée à un champ de la base de données.

### Etape 1 - Choix du modèle d’import {#step-1---choosing-the-import-template}

Lorsque vous lancez l’assistant d’import, vous devez d’abord sélectionner un modèle. Par exemple, pour configurer l’import des destinataires ayant reçu une newsletter, procédez comme suit :

1. Sélectionnez le dossier **[!UICONTROL Profils et Cibles > Traitement > Imports et exports génériques]**.
1. Cliquez sur **Nouveau** puis sur **Import** pour créer le modèle d&#39;import.

   ![Écran de sélection des modèles : nouveau modèle d&#39;importation de texte, libellé, description, type d&#39;importation simple et dossier de destination.](assets/s_ncs_user_import_wizard01_1.png)

1. Cliquez sur la flèche située à droite du champ **[!UICONTROL Modèle d&#39;import]** pour sélectionner votre modèle, ou cliquez sur l&#39;icône **[!UICONTROL Choisir le lien]** pour parcourir l&#39;arborescence.

   Le modèle natif est **[!UICONTROL Nouvel import texte]**. Ce modèle ne doit pas être modifié, mais vous pouvez le dupliquer pour en configurer un nouveau selon vos besoins. Par défaut, les modèles d&#39;import sont enregistrés dans le nœud **[!UICONTROL Profils et cibles > Modèles > Modèles de traitement]**.

1. Saisissez un nom pour cet import dans le champ **[!UICONTROL Libellé]**. Vous pouvez ajouter une description.
1. Sélectionnez le type d&#39;import dans le champ correspondant. Deux types d&#39;imports sont possibles : **[!UICONTROL Import simple]** pour n&#39;importer qu&#39;un seul fichier et **[!UICONTROL Import multiple]** pour importer plusieurs fichiers en une seule exécution.

   Dans le cas d’un import multiple, sélectionnez **[!UICONTROL Import multiple]** dans la liste déroulante **[!UICONTROL Type d’import]** du premier écran de l’assistant d’import.

   ![Écran de sélection des modèles avec la liste déroulante Type d’import énumérant Import simple et Import multiple.](assets/s_ncs_user_import_wizard01_2.png)

1. Indiquez ensuite les différents fichiers que vous souhaitez importer en cliquant sur **[!UICONTROL Ajouter]**.

   ![Liste des étapes d&#39;un import multiple avec deux fichiers sources et le bouton Ajouter pour ajouter un autre fichier.](assets/s_ncs_user_import_wizard01_3.png)

   Chaque fois qu’un fichier est ajouté, l’écran de l’assistant **[!UICONTROL Fichier à importer]** s’affiche. Consultez la section [Étape 2 - Sélection du fichier source](#step-2---source-file-selection) et suivez les étapes de l’assistant pour définir les options d’import comme pour un import simple.

   >[!NOTE]
   >
   >Les imports multiples ne doivent répondre qu’à des besoins spécifiques et ne sont pas recommandés.

#### Etape 2 - Choix du fichier source {#step-2---source-file-selection}

Le fichier source peut être au format texte (txt, csv, tab, colonnes fixes) ou xml.

Par défaut, l&#39;option **[!UICONTROL Télécharger le fichier sur le serveur]** est cochée. Cliquez sur le dossier situé à droite du champ **[!UICONTROL Fichier local]** pour parcourir le disque local et sélectionner le fichier à importer. Vous pouvez décocher cette option pour saisir le chemin d&#39;accès et le nom du fichier à importer s&#39;il se trouve sur le serveur.

![Écran Fichier à importer avec un champ Fichier local vide et l&#39;option Télécharger le fichier sur le serveur sélectionnée.](assets/s_ncs_user_import_wizard02_1.png)

Une fois le fichier spécifié, vous pouvez en visualiser les données dans la section inférieure de la fenêtre en cliquant sur le lien **[!UICONTROL Auto-détection du format]**. Cet aperçu affiche les 200 premières lignes du fichier source.

![Fichier à importer avec un fichier source sélectionné et ses premières lignes prévisualisées après avoir cliqué sur Détection automatique du format.](assets/s_ncs_user_import_wizard02_2.png)

Utilisez les options proposées au-dessus de cette vue pour configurer l’importation. Les paramètres définis via ces options sont transférés dans l’aperçu. Les options disponibles sont les suivantes :

* **[!UICONTROL Cliquez ici pour changer le format du fichier...]** permet de vérifier le format du fichier et d&#39;affiner le paramétrage.
* **[!UICONTROL Mettre à jour sur le serveur]** permet de transférer le fichier local sur le serveur. Cette option est disponible uniquement si la case **[!UICONTROL Télécharger le fichier sur le serveur]** est cochée.
* **[!UICONTROL Rapatrier en local]** n&#39;est disponible que si le fichier a été téléchargé sur le serveur.
* **[!UICONTROL Auto-détection du format]** permet de réinitialiser le format de la source de données. Cette option permet de réappliquer les formats originaux aux données qui ont été formatées via l&#39;option **[!UICONTROL Cliquez ici pour changer le format du fichier...]**.
* Le lien **[!UICONTROL Paramètres avancés]** permet de filtrer les données sources et d’accéder aux options avancées. Sur cet écran, vous pouvez choisir de n’importer qu’une partie du fichier. Vous pouvez également définir un filtre pour n’importer par exemple que les utilisateurs et utilisatrices de type « Prospect » ou « Client », en fonction de la valeur de la ligne correspondante. Ces options ne doivent être utilisées que par des utilisateurs et utilisatrices experts de JavaScript.

### Modifier le format du fichier {#changing-the-file-format}

L’option **[!UICONTROL Cliquer ici pour changer le format du fichier…]** permet de formater les données du fichier source, et notamment de préciser le séparateur de colonnes et le type de données pour chaque champ. Cette configuration est effectuée dans la fenêtre suivante :

![Boîte de dialogue Format de fichier : type de fichier, codage, séparateurs de colonne, libellé par colonne et type de données, et aperçu.](assets/s_ncs_user_import_wizard02_3.png)

Cette étape permet de décrire la façon dont les valeurs des champs du fichier doivent être lues. Par exemple, dans le cas d’une date, les données Date ou Date + Heure peuvent être associées à un format (jj/mm/aaaa, mm/jj/aa, etc.). Si les données d’entrée ne correspondent pas au format attendu, des rejets se produisent lors de l’importation.

Vous pouvez visualiser le résultat du paramétrage dans la zone d&#39;aperçu située dans la section inférieure de la fenêtre.

Cliquez sur **[!UICONTROL OK]** pour enregistrer ce formatage puis sur **[!UICONTROL Suivant]** pour afficher l&#39;étape suivante.

### Étape 3 - Mapping des champs {#step-3---field-mapping}

Vous devez ensuite choisir le schéma de destination et associer les données de chaque colonne à des champs de la base de données.

![Écran de mappage des champs avec le schéma de destination du destinataire et les colonnes source mappées aux champs de destination.](assets/s_ncs_user_import_wizard03_1.png)

* Le champ **[!UICONTROL Schéma de destination]** permet de sélectionner le schéma dans lequel seront importées les données. Cette information est obligatoire. Cliquez sur l&#39;icône **[!UICONTROL Choisir le lien]** pour sélectionner un des schéma existants. Cliquez sur **[!UICONTROL Éditer le lien]** pour afficher le contenu de la table sélectionnée.
* Le tableau central présente tous les champs définis dans le fichier source. Sélectionnez les champs à importer afin de leur associer un fichier de destination. Ces champs peuvent être mappés manuellement ou automatiquement.

  Pour associer un champ manuellement, cliquez sur la case à cocher pour sélectionner le champ source et cliquez dans la seconde colonne pour activer la cellule correspondant au champ sélectionné. Cliquez ensuite sur l&#39;icône **[!UICONTROL Editer l&#39;expression]** pour afficher tous les champs de la table courante. Sélectionnez le champ de destination et cliquez sur **[!UICONTROL OK]** pour valider le mapping.

  Pour associer automatiquement les champs sources et les champs de destination, cliquez sur l’icône **[!UICONTROL Deviner les champs destination]** située à droite de la liste des champs. Les champs proposés peuvent être modifiés si nécessaire.

  >[!IMPORTANT]
  >
  >Le résultat de cette opération doit toujours être validé avant de passer à l&#39;étape suivante.

* Vous pouvez appliquer une transformation aux champs importés. Pour cela, cliquez dans la cellule de la colonne **[!UICONTROL Transformation]** relative au champ visé et sélectionnez la transformation à appliquer.

  ![Écran de mappage des champs avec le menu déroulant Transformation : aucune, minuscules, majuscules, première lettre en majuscule.](assets/s_ncs_user_import_wizard03_2.png)

  >[!IMPORTANT]
  >
  >La transformation est appliquée au moment de l’import. Toutefois, si des contraintes ont été définies sur le champ de destination (dans l’exemple ci-dessus, sur le champ @lastname), ces contraintes sont prioritaires.

* Vous pouvez ajouter des champs calculés à l’aide de l’icône correspondante située à droite de la table centrale. Les champs calculés vous permettent d’effectuer des transformations complexes, d’ajouter des colonnes virtuelles ou de fusionner les données de plusieurs colonnes. Reportez-vous aux sections suivantes qui détaillent les différentes possibilités.

#### Les champs calculés {#calculated-fields}

Les champs calculés sont de nouvelles colonnes ajoutées au fichier source et calculées à partir d’autres colonnes. Les champs calculés peuvent ensuite être associés à des champs de la base de données Adobe Campaign. Les opérations de réconciliation ne sont toutefois pas possibles sur les champs calculés.

Quatre types de champ calculé sont proposés :

* **[!UICONTROL Chaîne fixe]** : la valeur du champ calculé est la même pour toutes les lignes du fichier source. Cela vous permet de définir la valeur d’un champ des enregistrements insérés ou mis à jour. Par exemple, vous pouvez définir un marqueur sur « oui » pour tous les enregistrements importés.
* **[!UICONTROL Chaîne avec fusion JavaScript]** : la valeur du champ calculé est une chaîne de caractères contenant des directives JavaScript.
* **[!UICONTROL Expression JavaScript]** : la valeur du champ calculé est le résultat de l’évaluation d’une fonction JavaScript. La valeur renvoyée peut être un nombre, une date, etc.
* **[!UICONTROL Énumération]** : la valeur du champ est attribuée en fonction d’une valeur contenue dans le fichier source. L’éditeur vous permet de spécifier la colonne source et de saisir la liste des valeurs d’énumération, comme dans l’exemple suivant :

  ![Importer la définition du champ calculé de type Énumérations mappant les valeurs sources 0 et 1 à non enregistrées et enregistrées.](assets/s_ncs_user_import_wizard03_3.png)

  L&#39;onglet **[!UICONTROL Aperçu]** permet de visualiser le résultat du paramétrage défini. Ici, la colonne **[!UICONTROL Abonnement]** a été ajoutée. La valeur est calculée à partir du champ **Statut**.

  ![Onglet Aperçu de la définition du champ calculé affichant la nouvelle colonne Service calculée à partir des données source.](assets/s_ncs_user_import_wizard03_4.png)

### Étape 4 - Réconciliation {#step-4---reconciliation}

L’étape de réconciliation de l’assistant d’import permet de définir le mode de rapprochement des données issues du fichier avec les informations existantes dans la base de données, ainsi que de fixer les règles de priorité entre les données du fichier et celles de la base de données. La fenêtre de configuration se présente comme suit :

![Écran de réconciliation avec l&#39;arborescence des champs, où Prénom est défini dans le cadre de la clé de réconciliation 1.](assets/s_ncs_user_import_wizard04_1.png)

La section centrale de l’écran présente de manière arborescente les champs et les tableaux de la base de données Adobe Campaign vers lesquels des données seront importées.

Des options spéciales sont disponibles pour chaque nœud (table ou champ). Lorsque vous cliquez sur le nœud concerné dans la liste, ses paramètres et une brève description apparaissent en dessous. Le comportement défini pour chaque élément est affiché dans la colonne **[!UICONTROL Comportement]** correspondante.

![Écran de réconciliation avec le paramètre Opération et le menu déroulant Gestion des doublons : Mettre à jour, Rejeter l&#39;entité, Ignorer.](assets/s_ncs_user_import_wizard04_2.png)

#### Types d&#39;opérations {#types-of-operation}

Pour chaque table concernée par l’import, vous devez définir le type d’opération. Les opérations disponibles pour l’élément principal de la base de données sont les suivantes :

* **[!UICONTROL Mise à jour ou insertion]** : met à jour l&#39;enregistrement s&#39;il existe dans la base de données et le crée dans le cas contraire.
* **[!UICONTROL Insertion]** : insère les enregistrements dans la base.
* **[!UICONTROL Mise à jour]** : effectue uniquement une mise à jour des enregistrements existants (ignore les autres enregistrements).
* **[!UICONTROL Réconciliation seule]** : recherche l’enregistrement dans la base de données mais n’effectue aucune mise à jour. Cela vous permet, par exemple, d’associer le dossier de personnes destinataires à importer en fonction d’une colonne du fichier sans mettre à jour les données dans les dossiers.
* **[!UICONTROL Suppression]** : permet de détruire des enregistrements de la base de données.

Les options disponibles pour chaque champ de la table concernée par l&#39;import sont les suivantes :

* **[!UICONTROL Mettre à jour (vider) si la valeur source est vide]** : en cas de mise à jour, la valeur du champ remplacera la valeur de la base de données si le champ est vide dans le fichier source. Sinon, le champ de la base de données est conservé.
* **[!UICONTROL Mettre à jour uniquement si la destination est vide]** : la valeur dans le fichier source ne remplace par la valeur dans le champ de la base de données, sauf si le champ de la base de données est vide. Dans ce cas, il prend la valeur du fichier source.
* **[!UICONTROL Mettre à jour uniquement à l&#39;insertion de l&#39;enregistrement]** : lors d&#39;une opération de mise à jour ou insertion, ne sont importés que les enregistrement du fichier source qui sont nouveaux.

>[!NOTE]
>
>Dans tous les cas, la définition d&#39;une clé de réconciliation est **obligatoire**, sauf en cas d&#39;insertion sans dédoublonnage.

#### Les clés de réconciliation {#reconciliation-keys}

Il est nécessaire de renseigner au moins une clé de réconciliation pour gérer le dédoublonnage.

Une clé de réconciliation est un ensemble de champs utilisés pour identifier un enregistrement. Par exemple, pour un import de destinataires, la clé de réconciliation peut être le numéro de compte, le champ « E-mail » ou encore les champs « Nom, Prénom, Société », etc.

Dans ce cas, pour savoir si une ligne du fichier correspond à une personne destinataire existante dans la base de données, le moteur d’import compare les valeurs du fichier à celles de la base de données pour tous les champs de la clé. Plus les champs sont spécifiques à un enregistrement, plus la comparaison entre les données de source et de destination pourra être fine et garantir l’intégrité des données après l’import. Il est possible de renseigner une seconde clé de réconciliation pour une même table : elle sera utilisée pour les lignes dont la première clé est vide.

Il convient aussi de ne pas choisir un champ qui risque d&#39;être modifié lors de l&#39;import, auquel cas, le moteur risque de créer des enregistrements supplémentaires.

![Écran de réconciliation avec le champ E-mail sélectionné et défini dans le cadre de la clé de réconciliation 2.](assets/s_ncs_user_import_wizard04_3.png)

>[!NOTE]
>
>Pour un import de destinataires, l&#39;identifiant du dossier sélectionné est implicitement ajouté à la clé.
>
>La réconciliation n&#39;est donc effectuée que sur ce dossier (sauf si aucun dossier n&#39;est sélectionné).

#### Déduplication {#deduplication}

>[!NOTE]
>
>Un doublon est un élément qui est présent au moins deux fois dans le fichier à importer.
>
>Un doublon est un élément qui est présent à la fois dans le fichier à importer et dans la base de données.

Le champ **[!UICONTROL Gestion des doublons]** permet de configurer le déduplication des données. Le déduplication concerne les enregistrements qui apparaissent plusieurs fois **dans le fichier source** (ou les fichiers sources dans le cas d&#39;un import multi-fichiers), c&#39;est-à-dire des lignes pour lesquelles les champs de la clé de réconciliation sont identiques.

* La gestion des doublons en mode **[!UICONTROL Mise à jour]** (mode par défaut) n’effectue pas de déduplication. Le dernier enregistrement est donc prioritaire (car il met à jour les données des enregistrements précédents). Le comptage des doublons n’est pas effectué dans ce mode.
* La gestion des doublons en mode **[!UICONTROL Ignorer]** ou **[!UICONTROL Rejeter l’entité]** exclut les doublons de l’import. Dans ce cas, aucun enregistrement n’est importé.
* En mode **[!UICONTROL Rejeter l&#39;entité]**, l&#39;élément n&#39;est pas importé et une erreur est générée dans les logs de l&#39;importation.
* En mode **[!UICONTROL Ignorer]**, l’élément n’est pas importé mais aucune trace de l’erreur n’est conservée. Ce mode permet d’optimiser les performances.

>[!IMPORTANT]
>
>La déduplication est effectuée en mémoire uniquement. La taille d’un import avec déduplication est donc limitée. La limite dépend de plusieurs paramètres (capacité du serveur applicatif, activité, nombre de champs dans la clé, etc.). La taille maximale d’une déduplication est de l’ordre d’1 000 000 de lignes.

La déduplication concerne un enregistrement présent à la fois dans le fichier source et dans la base de données. Cela concerne les opérations avec mise à jour uniquement (c’est-à-dire **[!UICONTROL Mise à jour et insertion]** ou **[!UICONTROL Mettre à jour]**). L&#39;option **[!UICONTROL Gestion des doublons]** permet de mettre à jour ou d&#39;ignorer l&#39;enregistrement s&#39;il se trouve à la fois dans le fichier source et dans la base de données. L&#39;option **[!UICONTROL Mise à jour ou insertion en fonction de l&#39;origine]** fait partie d&#39;un module en option : elle n&#39;est pas utilisable dans un contexte standard.

Les options **[!UICONTROL Rejeter]** et **[!UICONTROL Ignorer]** fonctionnent comme présentés ci-dessus.

### En cas d’erreur {#behavior-in-the-event-of-an-error}

La plupart des opérations de transfert de données génèrent différents types d’erreurs (format de ligne incohérent, adresse e-mail non valide, etc.). Toutes les erreurs et tous les avertissements générés par le moteur d’import sont stockés et liés à l’instance d’import.

![Onglet Général de la tâche d&#39;importation avec des compteurs pour les erreurs, avertissements, rejets, doublons et doublons mis en surbrillance.](assets/s_ncs_user_import_general_tab.png)

Le détail de ces rejets est visible depuis l&#39;onglet **[!UICONTROL Rejets]**.

![Onglet Rejets d&#39;une tâche d&#39;importation répertoriant les enregistrements rejetés par le connecteur et le message de rejet pour l&#39;enregistrement sélectionné.](assets/s_ncs_user_import_rejets_tab.png)

Les rejets peuvent être de deux types (le type est affiché dans la colonne **[!UICONTROL Connecteur]**) :

* Les rejets du connecteur de texte concernent les erreurs lors du traitement de la ligne du fichier (champ calculé, analyse de données, etc.). Dans ce cas, en cas d’erreur, la ligne entière est toujours rejetée.
* Les rejets du connecteur de base de données concernent les erreurs survenant lors de la réconciliation des données ou lors de l’écriture dans la base de données. Dans le cas d’un import sur plusieurs tables, le rejet peut ne concerner qu’une portion de l’enregistrement (par exemple, pour un import de destinataires et d’événements associés, une erreur peut empêcher la mise à jour d’un événement sans pour autant rejeter la personne destinataire).

Dans la page de réconciliation des données, il est possible de définir champ par champ, et table par table, le type de gestion d&#39;erreur souhaité.

* **[!UICONTROL Ignorer mais générer un avertissement]** : tous les champs sont importés dans la base de données, sauf celui qui a généré une erreur.
* **[!UICONTROL Rejeter l&#39;élément parent]** : toute la ligne de l&#39;enregistrement est rejetée et pas uniquement le champ qui a provoqué une erreur.
* **[!UICONTROL Rejeter tous les éléments]** : l&#39;import s&#39;arrête et tous les éléments de l&#39;enregistrement sont rejetés.

  ![Réconciliation En cas d&#39;erreur, liste déroulante : Ignorer et consigner un avertissement, Rejeter l&#39;élément parent, Rejeter tous les éléments.](assets/s_ncs_user_import_wizard04_4.png)

L&#39;arborescence dans l&#39;écran des rejets d&#39;une instance d&#39;import indique quels champs ont été rejetés et où les erreurs se sont produites.

Vous pouvez générer un fichier comportant ces enregistrements via l&#39;icône **[!UICONTROL Exporter les rejets]**:

![Liste générique d&#39;imports et d&#39;exports terminée par des erreurs et l&#39;icône Exporter les rejets.](assets/s_ncs_user_import_errors_export.png)

### Etape 5 - Etape supplémentaire lors de l&#39;import de destinataires {#step-5---additional-step-when-importing-recipients}

L’étape suivante de l’assistant d’import permet de choisir ou créer le dossier dans lequel les données seront importées, d’associer automatiquement les personnes destinataires importées à une liste (existante ou nouvelle) et de les abonner à un service.

![Importez l&#39;écran des destinataires avec des liens Modifier pour le dossier, la liste et le service, ainsi que le champ Origine.](assets/s_ncs_user_import_wizard05_1.png)

>[!NOTE]
>
>Cette étape n’apparaît que lorsque vous importez des personnes destinataires et que vous utilisez la table de personnes destinataires Adobe Campaign par défaut (**nms:recipient**).

* Cliquez sur les liens **[!UICONTROL Editer]** pour choisir le dossier, la liste ou le service auxquels vous souhaitez associer ou abonner les destinataires.

  1. Importer dans un dossier

     Le lien **[!UICONTROL Éditer…]** de la section **[!UICONTROL Réaliser l’import dans un dossier]** permet de sélectionner ou de créer le dossier dans lequel seront importées les personnes destinataires. Par défaut, si aucun dossier n’est défini, les données sont importées dans le dossier par défaut de l’opérateur ou de l’opératrice.

     >[!NOTE]
     >
     >Le dossier par défaut de l&#39;opérateur correspond au premier dossier dans lequel l&#39;opérateur a le droit d&#39;écrire. En savoir plus dans la section [Gérer les dossiers et vues](../audiences/folders-and-views.md).

     Pour choisir le dossier d&#39;import, cliquez sur la flèche située à droite du champ **[!UICONTROL Dossier]** et sélectionnez le dossier visé. Vous pouvez également utiliser l&#39;icône **[!UICONTROL Choisir le lien]** pour afficher l&#39;arborescence dans une nouvelle fenêtre ou créer un nouveau dossier.

     ![Effectuez une importation dans une boîte de dialogue de dossier à l&#39;aide de l&#39;option Ajouter à un dossier existant et d&#39;un champ Dossier.](assets/s_ncs_user_import_wizard05_2.png)

     Pour créer un nouveau dossier, sélectionnez le noeud à partir duquel vous souhaitez ajouter un dossier et cliquez sur le bouton droit de la souris. Choisissez **[!UICONTROL Ajouter un dossier Destinataires]**.

     ![Arborescence de dossiers avec le menu contextuel affichant Créer un dossier Destinataires.](assets/s_ncs_user_import_wizard05_3.png)

     Le dossier est ajouté en sous-arborescence du noeud courant. Saisissez le nom de ce nouveau dossier, appuyez sur la touche Entrée pour valider et cliquez ensuite sur **[!UICONTROL OK]**.

     ![Arborescence de dossiers avec un nouveau dossier Newsletter ajouté sous le nœud sélectionné, prêt à être confirmé avec OK.](assets/s_ncs_user_import_wizard05_4.png)

  1. Associer à une liste

     Le lien **[!UICONTROL Editer...]** de la section **[!UICONTROL Ajouter les destinataires dans une liste]** permet de sélectionner ou créer une liste dans laquelle seront ajoutés les destinataires importés.

     ![Ajoutez des destinataires à une boîte de dialogue de liste à l&#39;aide de l&#39;option Ajouter à une liste existante et d&#39;une liste déroulante de liste.](assets/s_ncs_user_import_wizard05_5.png)

     Vous pouvez créer une liste pour ces destinataires en cliquant sur **[!UICONTROL Choisir le lien]**, puis sur **[!UICONTROL Créer]**.

     ![Boîte de dialogue de sélection de liste avec l’icône Créer utilisée pour ajouter une nouvelle liste de destinataires.](assets/s_ncs_user_import_wizard05_6.png)

     Vous pouvez choisir d’ajouter les personnes destinataires à celles déjà présentse dans une liste existante ou de recréer la liste avec les nouvelles personnes destinataires. Dans ce cas, si la liste contenait déjà des personnes destinataires, elles seront supprimées et remplacées par les personnes destinataires importées.

  1. Abonner à un service

     Pour abonner tous les destinataires importés à un service d&#39;information, cliquez sur le lien **[!UICONTROL Editer...]** **&#x200B;**&#x200B;Vous pouvez sélectionner l&#39;option **[!UICONTROL Envoyer un message de confirmation]** : le contenu de ce message est défini dans le modèle de diffusion associé au service d&#39;abonnement.

     ![Abonner les destinataires à une boîte de dialogue de service avec un service existant sélectionné et Envoyer un message de confirmation coché.](assets/s_ncs_user_import_wizard05_7.png)

     Vous pouvez créer un nouveau service pour ces destinataires en cliquant sur le bouton **[!UICONTROL Choisir le lien]**, puis sur l&#39;icône **[!UICONTROL Créer]**. La gestion des services d&#39;information est présentée dans la section [Gérer les abonnements et les désabonnements dans Campaign](../start/subscriptions.md).

* Utilisez le champ **[!UICONTROL Origine]** pour ajouter des informations sur l’origine des destinataires dans leur profil. Ces informations sont particulièrement utiles dans le cadre d’une importation multiple.

Cliquez sur **[!UICONTROL Suivant]** pour valider cette étape et afficher l&#39;étape suivante.

### Étape 6 - Lancement de l’import {#step-6---launching-the-import}

La dernière étape de l’assistant permet de lancer l’import des données. Pour cela, cliquez sur le bouton **[!UICONTROL Démarrer]**.

![Écran d&#39;exécution de l&#39;import de données avec le bouton Démarrer, les logs d&#39;exécution, le nombre traité et une barre de progression de 100 %.](assets/s_ncs_user_import_wizard06_1.png)

Vous pouvez ensuite surveiller l’exécution du traitement d’import (consultez [Surveillance de l’exécution des workflows](../../automation/workflow/monitor-workflow-execution.md)).

## Exporter des données

Les traitements d’export vous permettent d’accéder à la base de données et d’en extraire les données : contacts, clientes et clients, listes, segments, etc.

Par exemple, il peut être utile d’utiliser les données de tracking d’une campagne (historique de tracking, etc.) dans une feuille de calcul. Les données de sortie peuvent être au format txt, CSV, TAB ou XML.

L’assistant d’export vous permet de configurer un export, de définir ses options et de lancer son exécution. Il s’agit d’une série d’écrans dont le contenu dépend du type d’export (simple ou multiple) et des droits de l’opérateur ou de l’opératrice.

L’assistant d’export s’affiche après la création d’un traitement d’export.

### Etape 1 - Choix du modèle d’export {#step-1---choosing-the-export-template}

Lorsque vous lancez l’assistant d’export, vous devez d’abord sélectionner un modèle. Par exemple, pour configurer l’export des personnes destinataires récemment enregistrées, procédez comme suit :

1. Sélectionnez le dossier **[!UICONTROL Profils et Cibles > Traitement > Imports et exports génériques]**.
1. Cliquez sur **Nouveau** puis sur **Export** pour créer le modèle d&#39;export.

   ![Écran de sélection du modèle d&#39;exportation avec Nouveau modèle d&#39;exportation de texte, libellé, description, Type d&#39;exportation simple et dossier.](assets/s_ncs_user_export_wizard01.png)

1. Cliquez sur la flèche située à droite du champ **[!UICONTROL Modèle d&#39;export]** pour sélectionner votre modèle, ou cliquez sur l&#39;icône **[!UICONTROL Choisir le lien]** pour parcourir l&#39;arborescence.

   Le modèle natif est **[!UICONTROL Nouvel export texte]**. Ce modèle ne doit pas être modifié, mais vous pouvez le dupliquer pour en configurer un nouveau. Par défaut, les modèles d&#39;export sont enregistrés dans le nœud **[!UICONTROL Ressources > Modèles > Modèles de traitement]**.

1. Saisissez un nom pour l’export dans le champ **[!UICONTROL Libellé]**. Vous pouvez ajouter une description.
1. Sélectionnez le type d&#39;export. Deux types d&#39;export sont possibles : **[!UICONTROL Export simple]** pour n&#39;exporter qu&#39;un seul fichier et **[!UICONTROL Export multiple]** pour exporter plusieurs fichiers en une seule exécution, depuis un ou plusieurs types de documents sources.

### Etape 2 - Type de fichier à exporter {#step-2---type-of-file-to-export}

Sélectionnez le type de document à exporter, c&#39;est-à-dire le schéma des données à exporter.

Par défaut, lorsque l&#39;export est lancé depuis le nœud **[!UICONTROL Traitements]**, il s&#39;agit des données de la table des destinataires. Si l&#39;export est lancé à partir d&#39;une liste de données (à partir du **[!UICONTROL menu contextuel > Exporter]**), la table à laquelle appartiennent les données est automatiquement renseignée dans le champ **[!UICONTROL Type de document]**.

![Écran Fichier à exporter avec le type de document du destinataire, l&#39;option de téléchargement, le chemin d&#39;accès au fichier local et le nom.](assets/s_ncs_user_export_wizard02.png)

* Par défaut, la case **[!UICONTROL Rapatrier en local le fichier généré après l&#39;export]** est cochée. Dans le champ **[!UICONTROL Fichier local]**, renseignez le nom et le chemin du fichier à créer, ou parcourez votre disque local en cliquant sur le dossier situé à droite du champ. Vous pouvez désélectionner cette option pour saisir le chemin d&#39;accès et le nom du fichier de sortie sur le serveur.

  >[!NOTE]
  >
  >Les traitements automatiques d&#39;import et d&#39;export sont toujours effectués sur le serveur.
  >
  >Si vous souhaitez n&#39;exporter qu&#39;une partie des données, cliquez sur le lien **[!UICONTROL Paramètres avancés...]** et indiquez le nombre de lignes à exporter dans le champ correspondant.

* Vous pouvez créer un export différentiel afin de n&#39;exporter que les enregistrements modifiés depuis la dernière exécution. Pour cela, cliquez sur le lien **[!UICONTROL Paramètres avancés]**, cliquez sur l&#39;onglet **[!UICONTROL Export différentiel]**, puis cochez la case **[!UICONTROL Activer l&#39;export différentiel]**.

  ![Paramètres avancés, onglet Exportation différentielle : l&#39;option Activer l&#39;exportation différentielle est cochée et un champ Date de modification est ajouté.](assets/s_ncs_user_export_wizard02_b.png)

  Vous devez saisir la date de la dernière modification. Elle peut être récupérée à partir d’un champ ou être calculée.

### Etape 3 - Définition du format de sortie {#step-3---defining-the-output-format}

Sélectionnez un format de sortie pour le fichier d’export. Les formats possibles sont les suivants : Texte, Texte à colonnes fixes, CSV et XML.

![Écran de format de destination avec format de sortie texte, séparateur de colonne, délimiteur de chaîne, codage et formats.](assets/s_ncs_user_export_wizard03.png)

* Pour le format **[!UICONTROL Texte]**, choisissez les délimiteurs à utiliser pour séparer les colonnes (tabulations, virgules, points-virgules, ou personnalisé) et les chaînes (guillemets simples ou doubles, ou aucun).
* Pour les format **[!UICONTROL Texte]** et **[!UICONTROL CSV]**, vous pouvez cocher l&#39;option **[!UICONTROL Utiliser la première ligne comme titre des colonnes]**.
* Indiquez le format de date et le format des nombres. Pour cela, cliquez sur le bouton **[!UICONTROL Editer]** correspondant au champ et utilisez l&#39;éditeur.
* Pour les champs contenant des valeurs énumérées, vous pouvez sélectionner **[!UICONTROL Exporter les libellés plutôt que les valeurs internes des énumérations]**. Par exemple, le titre peut être stocké sous la forme **1=M.**, **2=Mlle**, **3=Mme**. Si cette option est sélectionnée, **M.**, **Mlle** et **Mme** seront exportés.

### Etape 4 - Sélection des données {#step-4---data-selection}

Sélectionnez les champs à exporter. Pour ce faire :

1. Double-cliquez sur les champs de votre choix dans la liste **[!UICONTROL Champs disponibles]** afin de les ajouter à la section **[!UICONTROL Colonnes de sortie]**.
1. Utilisez les flèches à droite de la liste pour définir l&#39;ordre des champs dans le fichier de sortie.

   ![Écran Données à extraire avec la liste Champs disponibles et les colonnes de sortie sélectionnées.](assets/s_ncs_user_export_wizard04.png)

1. Cliquez sur le bouton **[!UICONTROL Ajouter]** pour faire appel à des fonctions.

### Etape 5 - Tri des colonnes {#step-5---sorting-columns}

Sélectionnez l&#39;ordre de tri des colonnes.

![Écran de tri répertoriant les colonnes de sortie avec les options de tri Trier et Descendant.](assets/s_ncs_user_export_wizard05.png)

### Etape 6 - Conditions de filtrage {#step-6---filter-conditions-}

Vous pouvez ajouter des conditions de filtrage afin de ne pas exporter toutes les données. La configuration de ce filtrage correspond à celle du ciblage des destinataires dans l’assistant de diffusion.

![Liste de filtrage des données des filtres de restriction, avec la boîte de dialogue Abonnés d&#39;un élément cible de service d&#39;information ouverte.](assets/s_ncs_user_export_wizard05_b.png)

### Etape 7 - Formatage des données {#step-7---data-formatting}

Vous pouvez modifier l&#39;ordre et le libellé des champs pour le fichier de sortie. Vous pouvez également appliquer des transformations aux données sources.

* Pour changer l&#39;ordre des colonnes à exporter, sélectionnez la colonne concernée et utilisez les flèches bleues situées à droite du tableau.
* Pour modifier le libellé d’un champ, cliquez dans la cellule de la colonne **[!UICONTROL Libellé]** correspondant au champ à modifier et saisissez le nouveau libellé. Appuyez sur la touche Entrée du clavier pour confirmer.
* Pour appliquer une transformation de casse au contenu d’un champ, sélectionnez-la dans la colonne **[!UICONTROL Transformation]**. Vous pouvez sélectionner les éléments suivants :

  * Passer en majuscules
  * Passer en minuscules
  * Première lettre en majuscule

  ![Écran Formatage des données avec le menu déroulant Transformation pour la colonne Société : aucune, inférieure, supérieure, première lettre.](assets/s_ncs_user_export_wizard06.png)

* Cliquez sur l&#39;icône **[!UICONTROL Ajouter un champ calculé]** si vous voulez créer un champ calculé (par exemple, une colonne contenant le nom+le prénom). Pour plus d’informations, consultez la section Importer des données.

Si vous exportez une collection d’éléments (par exemple les abonnements des personnes destinataires, les listes auxquelles elles appartiennent, etc.), vous devez indiquer le nombre d’éléments de la collection que vous voulez exporter.

![Les boîtes de dialogue de personnalisation de la collection limitent les lignes permettant de récupérer et de filtrer les éléments de la collection Abonnements.](assets/s_ncs_user_export_wizard06_c.png)

### Etape 8 - Prévisualisation des données {#step-8---data-preview}

Cliquez sur **[!UICONTROL Lancer la prévisualisation des données]** pour obtenir une prévisualisation du résultat de l’export.

![Écran de prévisualisation des données avec Commencer la prévisualisation des données, Champs de lignes à afficher et colonnes de résultats de prévisualisation.](assets/s_ncs_user_export_wizard07.png)

>[!NOTE]
>
>Comme pour toutes les listes disponibles dans la console, seules les 200 premières lignes sont affichées par défaut dans la fenêtre **[!UICONTROL Aperçu des données]**. Pour modifier ce paramètre, saisissez un nombre dans la zone **[!UICONTROL Lignes à afficher]** et cliquez sur **[!UICONTROL Démarrer l&#39;aperçu des données]**. [En savoir plus](../config/ui-settings.md#customize-lists)

Cliquez sur les onglets en bas de l’assistant pour basculer de la prévisualisation des résultats en colonnes aux résultats en XML. Vous pouvez également visualiser les requêtes SQL générées.

### Etape 9 - Lancement de l’export {#step-9---launching-the-export}

Cliquez sur **[!UICONTROL Démarrer]** pour lancer l’export des données.

![Écran d&#39;exécution de l&#39;export des données avec le bouton Démarrer, les logs d&#39;exécution et une barre de progression de 100 %.](assets/s_ncs_user_export_wizard08.png)

Vous pouvez ensuite surveiller l’exécution du traitement d’exportation.


## Collecte de profils via des applications web

Utilisez Campaign pour créer des formulaires web, et collecter et gérer facilement et efficacement les informations de profil. Vous pouvez partager ces formulaires sur votre site web, ce qui permet à vos contacts de fournir facilement leurs informations. Leurs informations sont envoyées à Campaign pour créer leur profil ou mettre à jour leurs informations si elles sont déjà présentes dans la base de données.

![Workflow d&#39;application web avec début, préchargement, page, stockage et fin, et éditeur de page avec formulaire d&#39;inscription par e-mail.](assets/web-form-page.png)

Découvrez comment créer des formulaires web dans [Prise en main des formulaires web](../dev/web/about-web-forms.md).

**Rubriques connexes :**

* [Création d’audiences](audiences.md)
* [Dédupliquer les profils](../../automation/workflow/deduplication-merge.md)
* [Enrichir les données de profil](../../automation/workflow/enrich-data.md)
* Comprendre le [modèle de données](../dev/datamodel.md) de Campaign