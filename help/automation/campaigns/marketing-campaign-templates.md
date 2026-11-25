---
product: campaign
title: Modèles de campagne marketing
description: Modèles de campagne marketing
feature: Campaigns, Templates
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 1bd8d3e7-aaa9-4e00-96bb-0d30614ab380
TQID: 'https://experienceleague.adobe.com/qmz-Sd1EJmACFfgozVirCHCaeiQN-lGKuxd9-VAPMHs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: baf8e746-117b-5e73-b179-0a83edc0295f
    internal-label: Templates
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 68%
---
# Création et configuration de modèles d’opération {#campaign-templates}

Toutes les campagnes marketing sont basées sur un modèle qui stocke les principales caractéristiques et fonctionnalités. Campaign est fourni avec un modèle intégré qui permet de créer des campagnes. Toutes les fonctionnalités de ce modèle sont activées : documents, adresses de contrôle, validations, compositions de diffusion, etc.

Les fonctionnalités disponibles dépendent de vos autorisations, modules complémentaires et de la configuration de votre plateforme Adobe Campaign.


>[!NOTE]
>
>Vous pouvez afficher l’arborescence en cliquant sur l’icône de l’**[!UICONTROL Explorateur]** sur la page d’accueil.

Un modèle natif est fourni pour créer une opération pour laquelle aucune configuration spécifique n’a été définie. Vous pouvez créer et configurer des modèles d’opération, puis créer des opérations à partir de ces modèles.

## Création d’un modèle d’opération {#create-a-campaign-template}

Pour créer un modèle de campagne, procédez comme suit :

1. Ouvrez l&#39;**Explorateur** Campaign et accédez à **Ressources > Modèles > Modèles de campagne**.
1. Cliquez sur **Nouveau** dans la barre d&#39;outils située au-dessus de la liste des modèles.

![La liste des modèles de campagne se trouve sous Ressources > Modèles, avec le bouton Nouveau en surbrillance dans la barre d’outils.](assets/campaign-template-node.png)

Vous pouvez également **dupliquer** le modèle intégré afin de le réutiliser et d&#39;adapter sa configuration à vos besoins. Pour cela, faites un clic droit sur le modèle et sélectionnez **Dupliquer**.

1. Saisissez le libellé du nouveau modèle d&#39;opération.
1. Cliquez sur **Enregistrer**, puis rouvrez le modèle.
1. Dans l&#39;onglet **Modifier**, définissez les propriétés du modèle.
1. Sélectionnez le lien **Paramètres avancés de la campagne...** pour ajouter un workflow à votre modèle de campagne.

   ![Nouvel onglet Modifier du modèle de campagne avec le lien Paramètres avancés de la campagne mis en surbrillance.](assets/campaign-template-parameters.png)

1. Remplacez la valeur **Ciblage et workflows** par **Oui**, puis confirmez. Découvrez comment ajouter des fonctionnalités dans la [typologie des modules](#typology-of-enabled-modules).
1. L&#39;onglet **Ciblage et workflows** est ajouté au modèle. Cliquez sur **Ajouter un workflow...**, puis saisissez un **libellé** et cliquez sur **Ok**.
1. Créez votre workflow selon vos besoins.

   ![Onglet Ciblage et workflows du modèle avec un workflow contenant Requête et Lecture de liste menant à une diffusion par e-mail.](assets/campaign-template-create-wf.png)

1. Cliquez sur **Enregistrer**. Votre modèle est maintenant prêt à être utilisé pour créer une nouvelle campagne.

Les divers onglets et sous-onglets du modèle de campagne vous permettent d&#39;accéder à ses paramètres, qui sont décrits dans la section [Configuration générale](#general-configuration).

## Sélection des modules {#select-modules}

Le lien **[!UICONTROL Paramètres avancés de la campagne…]** vous permet d&#39;activer et de désactiver des traitements des campagnes basées sur ce modèle. Sélectionnez les fonctionnalités à activer dans les opérations créées à partir de ce modèle.

![Onglet Configuration des paramètres avancés répertoriant chaque fonctionnalité avec une valeur Oui ou Non ; Dépenses et objectifs est Non.](assets/campaign-template-select-modules.png)

Si une fonctionnalité n&#39;est pas sélectionnée, les éléments relatifs au processus (menus, icônes, options, onglets, sous-onglets, etc.) n&#39;apparaissent pas dans l&#39;interface du modèle ou dans les campagnes basées sur ce modèle. Les onglets situés à gauche des détails de la campagne, ainsi que ceux disponibles, coïncident généralement avec les processus sélectionnés dans le modèle. Par exemple, si la fonctionnalité **Dépenses et objectifs** n&#39;est pas sélectionnée, l&#39;onglet **[!UICONTROL Budget]** correspondant n&#39;apparaîtra pas dans les campagnes basées sur ce modèle.

De plus, des raccourcis vers les fenêtres de configuration sont ajoutés dans le tableau de bord de la campagne. Lorsqu’une fonctionnalité est activée, un lien direct permet d’y accéder depuis le tableau de bord de la campagne.

### Modèles de configuration

* Par exemple, avec les paramètres suivants :

  ![Paramètres avancés : population témoin, adresses de contrôle et documents définis sur Oui ; approbations, ciblage et workflows définis sur Non.](assets/campaign-template-select-functionalities.png)

  Le tableau de bord de la campagne affiche :

  ![Tableau de bord de Campaign avec les onglets Tableau de bord et Modifier uniquement, et Ajouter une diffusion et Ajouter des liens vers un document.](assets/campaign-template-dashboard-sample-1.png)

  Notez que l&#39;onglet **[!UICONTROL Ciblage et workflows]** est manquant.

  Les fonctionnalités suivantes sont disponibles :

  ![Onglet Modifier de la campagne avec les sections Propriétés, Documents et Audit et aucune section Budget.](assets/campaign-template-edit-sample-1.png)

  Notez que l&#39;onglet **[!UICONTROL Budget]** est manquant.

  Les paramètres avancés de la campagne reflètent également cette configuration.

  ![Paramètres avancés de Campaign avec les onglets Population témoin et Adresses de contrôle, et aucun onglet Validations.](assets/campaign-template-parameters-sample-1.png)

  Notez que l&#39;onglet **[!UICONTROL Validations]** n&#39;est pas disponible.

* Avec cette configuration :
  ![Paramètres avancés : Validations, Ciblage et workflows, Dépenses et objectifs définis sur Oui ; autres fonctionnalités Non.](assets/campaign-template-dashboard-sample-2.png)

  Le tableau de bord de la campagne affiche :

  ![Tableau de bord de Campaign avec l&#39;onglet Ciblage et workflows et un lien Ajouter une diffusion mais pas de lien Ajouter un document.](assets/campaign-template-select-functionalities-2.png)

  Notez que l&#39;onglet **[!UICONTROL Ciblage et workflows]** est disponible, mais le lien **Ajouter un document** est manquant.

  Les fonctionnalités suivantes sont disponibles :

  ![Onglet Modifier avec la section Budget ouverte, affichant les onglets budget, objectifs et Coûts et Dépenses associés.](assets/campaign-template-edit-sample-2.png)

  Notez que l&#39;onglet **[!UICONTROL Budget]** est disponible.

  Les paramètres avancés de la campagne reflètent également cette configuration.

  ![Paramètres avancés avec l&#39;onglet Approbations et validations de tâches, et aucun onglet Population témoin ou Adresses de contrôle.](assets/campaign-template-parameters-sample-2.png)

  Notez que l&#39;onglet **[!UICONTROL Validations]** est disponible, mais les onglets **[!UICONTROL Population témoin]** et **[!UICONTROL Adresses de contrôle]** ne sont pas activés.


## Typologie des modules {#typology-of-enabled-modules}

* **Population témoin**

  Lorsque ce module est sélectionné, un onglet supplémentaire est ajouté aux paramètres avancés du modèle et des campagnes basées sur ce modèle. La configuration peut être définie à partir du modèle ou individuellement au niveau de chaque campagne. En savoir plus sur les populations témoins dans [Diffusions de campagnes marketing](marketing-campaign-deliveries.md).

  ![Paramètres avancés Onglet Population témoin avec l&#39;option de population témoin activée et un lien Modifier pour sa configuration.](assets/template-activate-1.png)


* **Adresses de contrôle**

  Lorsque ce module est sélectionné, un onglet supplémentaire est ajouté aux paramètres avancés du modèle et des campagnes basées sur ce modèle. La configuration peut être définie à partir du modèle ou individuellement au niveau de chaque campagne.

  ![Onglet Adresses de contrôle des paramètres avancés avec un lien Importer des modèles de contrôle et une liste d’adresses de contrôle.](assets/template-activate-2.png)

* **Documents**

  Lorsque ce module est sélectionné, un onglet supplémentaire est ajouté à l&#39;onglet **[!UICONTROL Modifier]** du modèle et des campagnes basées sur ce modèle. Les documents attachés peuvent être ajoutés à partir du modèle ou individuellement au niveau de chaque campagne. En savoir plus sur les documents dans [Diffusions de campagnes marketing](marketing-campaign-deliveries.md).

  ![Section Documents de l&#39;onglet Modifier répertoriant les documents joints, avec les boutons Ajouter, Supprimer et Détailler.](assets/template-activate-3.png)

* **Composition de diffusion**

  Lorsque ce module est sélectionné, un sous-onglet **[!UICONTROL Compositions de diffusion]** est ajouté à l’onglet **[!UICONTROL Documents]** afin de définir des compositions de diffusion pour l’opération. En savoir plus sur les compositions de diffusion dans [Utiliser les compositions de diffusion](marketing-campaign-assets.md#delivery-outlines).

  ![Sous-onglet compositions de diffusion de la section Documents avec un lien Ajouter une composition de diffusion.](assets/template-activate-4.png)

* **Ciblages et workflows**

  Lorsque vous sélectionnez le module **[!UICONTROL Ciblages et workflows]**, un onglet est ajouté pour vous permettre de créer un ou plusieurs workflows pour les opérations basées sur ce modèle. Les workflows peuvent également être configurés individuellement pour chaque opération en fonction de ce modèle.En savoir plus sur les workflows de campagne dans [Diffusions de campagnes marketing](marketing-campaign-deliveries.md).

  ![Onglet Ciblage et workflows avec un workflow : Requête et lecture de liste, Déduplication, puis Diffusion mobile.](assets/template-activate-5.png)

  Lorsque ce module est activé, un onglet **[!UICONTROL Traitements]** est ajouté dans les paramètres avancés de la campagne afin de définir la séquence d&#39;exécution du processus.

* **Validations**

  Si vous sélectionnez le module **[!UICONTROL Validations]**, vous pouvez sélectionner les processus à valider et choisir les opérateurs chargés de leur validation. En savoir plus sur les validations dans [Sélectionner des réviseurs](marketing-campaign-approval.md#select-reviewers).

  ![Onglet Validations des paramètres avancés avec validation du contenu, de la cible, du budget et de l&#39;extraction activée et réviseurs affectés.](assets/template-activate-6.png)

  Vous pouvez choisir d&#39;activer ou non la validation du processus dans l&#39;onglet **[!UICONTROL Validations]** de la section des paramètres avancés des modèles.

* **Dépenses et objectifs**

  Lorsque ce module est sélectionné, un onglet **[!UICONTROL Budget]** est ajouté dans les détails du modèle et des opérations basées sur ce modèle afin de sélectionner le budget associé.

  ![Section Budget de l&#39;onglet Modifier avec les champs de budget associés, les objectifs et l&#39;onglet Coûts avec les lignes de coût.](assets/template-activate-7.png)


## Propriétés des modèles {#template-properties}

![Onglet Modifier le modèle de campagne avec le menu déroulant Type d’opération ouvert, affichant Unique, Récurrent et Périodique.](assets/template-op-type.png)

Lorsque vous créez un modèle de campagne, vous devez indiquer les informations suivantes :

* Saisissez le **libellé** du modèle : le libellé est obligatoire et constitue le libellé par défaut pour toutes les campagnes basées sur ce modèle.
* Sélectionnez la **nature** de la campagne dans la liste déroulante. Les valeurs proposées dans cette liste correspondent à celles enregistrées dans l’énumération **[!UICONTROL natureOp]**.

  Découvrez comment accéder à vos énumérations et la manière de les configurer dans [Gérer les énumérations](../../v8/config/enumerations.md).

* Sélectionnez le **type de campagne** : unique, récurrente ou périodique. Par défaut, les modèles de campagne s’appliquent aux campagnes uniques. Les campagnes récurrentes et périodiques sont présentées dans la section [Créer des campagnes récurrentes et périodiques](recurring-periodic-campaigns.md).
* Indiquez la durée de la campagne, c’est-à-dire la période sur laquelle la campagne s’étalera. Lors de la création d’une campagne basée sur ce modèle, les dates de début et de fin de la campagne seront automatiquement renseignées.

  S’il s’agit d’une opération récurrente, vous devez indiquer les dates de début et de fin de l’opération directement dans le modèle.

* Indiquez le **programme d&#39;appartenance** du modèle : les campagnes basées sur le modèle seront associées au programme sélectionné.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.
-->
