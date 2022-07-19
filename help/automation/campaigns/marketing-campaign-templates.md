---
product: campaign
title: Modèles de campagne marketing
description: Modèles de campagne marketing
feature: Campaigns, Templates
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 49%

---

# Création et configuration de modèles d’opération {#campaign-templates}

Toutes les opérations marketing sont basées sur un modèle qui stocke les principales caractéristiques et fonctionnalités. Campaign est fourni avec un modèle intégré pour créer des campagnes. Toutes les fonctionnalités de ce modèle sont activées : Documents, Adresses de contrôle, Validations, Compositions de diffusion, etc.

Les fonctionnalités disponibles dépendent de vos autorisations, modules complémentaires et de la configuration de votre plateforme Adobe Campaign.


>[!NOTE]
>
>Vous pouvez afficher l’arborescence en cliquant sur l’icône de l’**[!UICONTROL Explorateur]** sur la page d’accueil.

Un modèle natif est fourni pour créer une opération pour laquelle aucune configuration spécifique n’a été définie. Vous pouvez créer et configurer des modèles d&#39;opération, puis créer des opérations à partir de ces modèles.

## Création d’un modèle d’opération {#create-a-campaign-template}

Pour créer un modèle d’opération, procédez comme suit :

1. Ouvrir la campagne **Explorateur** et accédez à **Ressources > Modèles > Modèles d’opération**.
1. Cliquez sur **Nouveau** dans la barre d’outils située au-dessus de la liste des modèles.

![](assets/campaign-template-node.png)

Vous pouvez également **duplicata** le modèle intégré pour réutiliser et adapter sa configuration. Pour cela, cliquez avec le bouton droit sur le modèle et sélectionnez **Dupliquer**.

1. Saisissez le libellé du nouveau modèle d&#39;opération.
1. Cliquez sur **Enregistrer**, puis rouvrez le modèle.
1. Dans le **Modifier** , définissez les propriétés du modèle.
1. Sélectionner **Paramètres avancés de l&#39;opération...** lien pour ajouter un workflow à votre modèle d&#39;opération.

   ![](assets/campaign-template-parameters.png)

1. Modifiez la variable **Ciblage et workflows** valeur à **Oui** et confirmez. Découvrez comment ajouter des fonctionnalités dans [cette section](#typology-of-enabled-modules).
1. Le **Ciblage et workflows** est ajouté au modèle. Cliquez sur **Ajouter un workflow...**, saisissez une **Libellé** et cliquez sur **Ok**.
1. Créez votre workflow selon vos besoins.

   ![](assets/campaign-template-create-wf.png)

1. Cliquez sur **Enregistrer**. Votre modèle est maintenant prêt à être utilisé pour créer une nouvelle campagne.

Les divers onglets et sous-onglets du modèle d’opération vous permettent d’accéder à ses paramètres, qui sont décrits dans la section [Configuration générale](#general-configuration).

## Sélection des modules {#select-modules}

Le **[!UICONTROL Paramètres avancés de l&#39;opération...]** lien permet d&#39;activer et désactiver les traitements pour les opérations basées sur ce modèle. Sélectionnez les fonctionnalités à activer dans les opérations créées à partir de ce modèle.

![](assets/campaign-template-select-modules.png)

Si une fonctionnalité n&#39;est pas sélectionnée, les éléments concernant le processus (menus, icônes, options, onglets, sous-onglets, etc.) ne s’affichent pas dans l’interface du modèle ni dans les campagnes basées sur ce modèle. Les onglets situés à gauche des détails de l&#39;opération, ainsi que les onglets disponibles, correspondent aux fonctionnalités sélectionnées dans le modèle. Par exemple, la variable **Dépenses et objectifs** La fonctionnalité n’est pas activée. **[!UICONTROL Budget]** ne s’affichent pas dans les campagnes basées sur ce modèle.

De plus, des raccourcis vers les fenêtres de configuration sont ajoutés dans le tableau de bord de l&#39;opération : lorsqu&#39;une fonctionnalité est activée, un lien direct permet d&#39;y accéder depuis le tableau de bord de l&#39;opération.

### Exemples de configuration

* Par exemple, avec les paramètres suivants :

   ![](assets/campaign-template-select-functionalities.png)

   Le tableau de bord de l&#39;opération affiche :

   ![](assets/campaign-template-dashboard-sample-1.png)

   Notez que la variable **[!UICONTROL Ciblage et workflows]** est manquant.

   Les fonctionnalités suivantes sont disponibles :

   ![](assets/campaign-template-edit-sample-1.png)

   Notez que la variable **[!UICONTROL Budget]** est manquant.

   Les paramètres avancés de la campagne reflètent également cette configuration.

   ![](assets/campaign-template-parameters-sample-1.png)

   Notez que la variable **[!UICONTROL Approbations]** n’est pas disponible.

* Avec cette configuration :
   ![](assets/campaign-template-dashboard-sample-2.png)

   Le tableau de bord de l&#39;opération affiche :

   ![](assets/campaign-template-select-functionalities-2.png)

   Notez que la variable **[!UICONTROL Ciblage et workflows]** est disponible, mais la variable **Ajouter un document** lien manquant.

   Les fonctionnalités suivantes sont disponibles :

   ![](assets/campaign-template-edit-sample-2.png)

   Notez que la variable **[!UICONTROL Budget]** est disponible.

   Les paramètres avancés de la campagne reflètent également cette configuration.

   ![](assets/campaign-template-parameters-sample-2.png)

   Notez que la variable **[!UICONTROL Approbations]** est disponible, mais la variable **[!UICONTROL Population témoin]** et **[!UICONTROL Adresses de contrôle]** les onglets ne sont pas activés.


## Typologie des modules {#typology-of-enabled-modules}

* **Population témoin**

   Lorsque ce module est sélectionné, un onglet supplémentaire est ajouté dans les paramètres avancés du modèle et des opérations basées sur ce modèle. La configuration peut être définie à partir du modèle ou individuellement, au niveau de chaque opération. En savoir plus sur les populations témoins dans [cette section](marketing-campaign-deliveries.md#defining-a-control-group).

   ![](assets/template-activate-1.png)


* **Adresses de contrôle**

   Lorsque ce module est sélectionné, un onglet supplémentaire est ajouté dans les paramètres avancés du modèle et des opérations basées sur ce modèle. Le paramétrage peut être défini depuis le modèle ou individuellement au niveau de chaque opération.

   ![](assets/template-activate-2.png)

* **Documents**

   Lorsque ce module est sélectionné, un onglet supplémentaire est ajouté au **[!UICONTROL Modifier]** de l&#39;onglet du modèle et des opérations basées sur ce modèle. Les documents attachés peuvent être ajoutés depuis le modèle ou individuellement au niveau de chaque opération. En savoir plus sur les documents dans [cette section](marketing-campaign-deliveries.md#manage-associated-documents).

   ![](assets/template-activate-3.png)

* **Composition de diffusion**

   Lorsque ce module est sélectionné, un sous-onglet **[!UICONTROL Compositions de diffusion]** est ajouté à l’onglet **[!UICONTROL Documents]** afin de définir des compositions de diffusion pour l’opération. En savoir plus sur les compositions de diffusion dans [cette section](marketing-campaign-assets.md#delivery-outlines).

   ![](assets/template-activate-4.png)

* **Ciblages et workflows**

   Lorsque vous sélectionnez le module **[!UICONTROL Ciblages et workflows]**, un onglet est ajouté pour vous permettre de créer un ou plusieurs workflows pour les opérations basées sur ce modèle. Les workflows peuvent également être configurés individuellement pour chaque opération en fonction de ce modèle. En savoir plus sur les workflows des opérations dans [cette section](marketing-campaign-deliveries.md#build-the-main-target-in-a-workflow).

   ![](assets/template-activate-5.png)

   Lorsque ce module est activé, une **[!UICONTROL Tâches]** est ajouté aux paramètres avancés de l&#39;opération pour définir l&#39;ordre d&#39;exécution des processus.

* **Validations**

   Si vous activez la variable **[!UICONTROL Approbations]**, vous pouvez sélectionner les traitements à valider et les opérateurs chargés de leur validation. En savoir plus sur les validations dans [cette section](marketing-campaign-approval.md#select-reviewers).

   ![](assets/template-activate-6.png)

   Vous pouvez choisir d&#39;activer ou non la validation des traitements via le **[!UICONTROL Approbations]** de la section paramètres avancés des modèles .

* **Dépenses et objectifs**

   Lorsque ce module est sélectionné, un onglet **[!UICONTROL Budget]** est ajouté dans les détails du modèle et des opérations basées sur ce modèle afin de sélectionner le budget associé.

   ![](assets/template-activate-7.png)


## Propriétés des modèles {#template-properties}

![](assets/template-op-type.png)

Lorsque vous créez un modèle d&#39;opération, vous devez indiquer les informations suivantes :

* Saisissez le **label** du modèle : le libellé est obligatoire et est le libellé par défaut pour toutes les opérations basées sur ce modèle.
* Sélectionnez la **nature** de l&#39;opération dans la liste déroulante. Les valeurs proposées dans cette liste correspondent à celles enregistrées dans l&#39;énumération **[!UICONTROL natureOp]**.
   <!--
  >[!NOTE]
  >
  >For more information on enumerations, refer to the [Getting Started](../../platform/using/managing-enumerations.md) section.-->

* Sélectionnez le **type de campagne** : unique, récurrente ou périodique. Par défaut, les modèles de campagne s’appliquent aux campagnes uniques. Les opérations périodiques et récurrentes sont décrites dans [cette section](recurring-periodic-campaigns.md).
* Indiquez la durée de l&#39;opération, c&#39;est-à-dire la période sur laquelle s&#39;étalera l&#39;opération. Lors de la création d&#39;une opération basée sur ce modèle, les dates de début et de fin de l&#39;opération seront alors automatiquement renseignées.

   S&#39;il s&#39;agit d&#39;une opération récurrente, vous devez indiquer les dates de début et de fin de l&#39;opération directement dans le modèle.

* Spécifiez la variable **programme associé** du modèle : les opérations basées sur ce modèle sont liées au programme sélectionné.

<!--
## Track campaign execution{#campaign-reverse-scheduling}

You can create a schedule for a campaign and track accomplishments, for instance to prepare an event schedule for a specific date. Campaign templates now let you calculate the start date of a task based on the end date of a campaign.


In the task configuration box, go to the **[!UICONTROL Implementation schedule]** area and check the **[!UICONTROL The start date is calculated based on the campaign end date]** box. (Here, "start date" is the task start date). Go to the **[!UICONTROL Start]** field and enter an interval: the task will start this long before the campaign end date. If you enter a period which is longer than the campaign is set to last, the task will begin before the campaign.

![](assets/mrm_task_in_template_start_date.png)

When you create a campaign using this template, the task start date will be calculated automatically. However, you can always change it later.-->
