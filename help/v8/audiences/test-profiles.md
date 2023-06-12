---
title: Création de profils de test dans Campaign
description: Découvrez comment créer et gérer des profils de test dans Adobe Campaign
feature: Audiences, Profiles
role: User
level: Beginner
source-git-commit: 19c42bcd2a96173f3d33e3e259192107b5e64c6c
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 49%

---

# Création et gestion des profils de test {#create-test-profiles}

## Qu&#39;est-ce qu&#39;une adresse de contrôle ? {#gs-seeds}

Les profils de test sont créés en tant qu&#39;adresses de contrôle. Ils sont utilisés pour cibler des destinataires qui ne correspondent pas aux critères de ciblage définis. Les adresses de contrôle vous permettent de prévisualiser et de tester la personnalisation et le rendu avant l&#39;envoi de votre diffusion, en leur envoyant des BAT.

Les adresses de contrôle présentent les avantages suivants :

* Substitution aléatoire des champs avec des données issues des profils des destinataires : vous pouvez ainsi ne saisir que l&#39;adresse email, par exemple dans la section adresse de contrôle, et laisser Campaign renseigner automatiquement les autres champs du profil. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=en){target="_blank"}.
* Dans un contexte de workflow avec utilisation des fonctionnalités de Datamanagement, les données additionnelles exploitées dans les diffusions peuvent être renseignées au niveau des adresses de contrôle afin d&#39;en forcer la valeur : on s&#39;affranchit ainsi de la substitution aléatoire des valeurs.
* Les adresses de contrôle sont automatiquement exclues des rapports sur les statistiques de diffusions suivants : **[!UICONTROL Clics]**, **[!UICONTROL Ouvertures]**, **[!UICONTROL Désinscriptions]**.

Les adresses de contrôle sont ajoutées à la cible de diffusions en étant importées ou créées directement au niveau de la diffusion ou de la campagne.

>[!NOTE]
>
>Les adresses de contrôle ne sont pas créées dans la table des destinataires, mais dans une table distincte. Si vous étendez le tableau des destinataires avec de nouvelles données, vous devez étendre le tableau des adresses de contrôle avec les mêmes données. Sinon, les champs étendus ne seront pas pris en compte pour les adresses de contrôle.
>
>Un exemple d&#39;extension du tableau des adresses de contrôle est présenté dans la section [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.



## Créer des adresses de contrôle

Les adresses de contrôle ne sont pas gérées via des profils et des cibles standard, mais dans un noeud dédié de l&#39;explorateur Adobe Campaign : **[!UICONTROL Ressources > Gestion de campagne > Adresses de contrôle]**. Vous pouvez créer des sous-dossiers pour organiser les adresses de contrôle.

Adobe Campaign permet également de créer des modèles dʼadresses de contrôle qui sont importées au niveau des diffusions ou des campagnes et sont ensuite adaptées selon les besoins spécifiques aux diffusions et campagnes concernées. Consultez la section [Création de modèles dʼadresses de contrôle](#creating-seed-address-templates).

### Définition dʼadresses {#defining-addresses}

Pour créer des adresses de contrôle, procédez comme suit :

1. Cliquez sur le bouton **[!UICONTROL Nouveau]** situé au-dessus de la liste des adresses de contrôle.
1. Saisissez les données associées à l&#39;adresse dans les champs correspondants de l&#39;onglet **[!UICONTROL Destinataire]**. Les champs disponibles correspondent aux champs standards dans les profils des destinataires de la diffusion (nms:recipient table) : nom, prénom, email, etc.

   >[!NOTE]
   >
   >Le libellé de l&#39;adresse reprend automatiquement le nom et le prénom saisis.
   >
   >Lors de la création d’une adresse de contrôle, il n’est pas nécessaire de renseigner tous les champs de chaque onglet. En effet, les éléments de personnalisation manquants sont renseignés de manière aléatoire lors de l’analyse de la diffusion.

1. Dans le **[!UICONTROL Champs d’adresse]** , saisissez les valeurs à insérer dans les logs de diffusion lors de la phase d&#39;analyse, dans la variable **[!UICONTROL nms:broadLog]** table.

1. Dans l&#39;onglet **[!UICONTROL Données additionnelles]**, renseignez les données de personnalisation utilisées pour les diffusions créées dans les workflows Data management et auxquelles vous souhaitez affecter une valeur spécifique.

   Assurez-vous que des données cibles supplémentaires ont été définies avec un alias commençant par &quot;@&quot; dans la variable **[!UICONTROL Enrichissement]** activité de workflow. Sinon, vous ne pourrez pas les utiliser correctement avec vos adresses de contrôle dans votre activité de diffusion.

### Créer des modèles d&#39;adresses de contrôle {#creating-seed-address-templates}

Vous pouvez créer des modèles d&#39;adresses qui pourront être importés et modifiés pour chaque diffusion. Le processus est le même que lors de la définition d&#39;une nouvelle adresse de contrôle. La seule différence est que les adresses des modèles d&#39;adresses de contrôle doivent être stockées dans un dossier de type &#39;Modèle&#39;.

### Adresses de contrôle pour les diffusions courrier {#direct-mail-seed-addresses}

Pour [diffusions courrier](../send/direct-mail.md), les adresses de contrôle sont ajoutées lors de l&#39;extraction et mélangées dans le document de sortie.

Pour les diffusions courrier, le format du fichier d&#39;extraction doit respecter les limitations suivantes :

* Il ne doit pas utiliser l&#39;option **[!UICONTROL Gérer les groupements (GROUP BY+HAVING)]**.

* Si des collections d’éléments sont extraites, ces champs auront une valeur vide pour les adresses de contrôle, sauf si la variable **[!UICONTROL Ligne unique (utilisateur expert)]** est sélectionnée.

## Ajouter des adresses de contrôle dans une diffusion{#seed-addresses-in-a-delivery}

Pour ajouter des adresses de contrôle spécifiques à une diffusion, cliquez sur le lien **[!UICONTROL Pour]**, puis sélectionnez l&#39;onglet **[!UICONTROL Adresses de contrôle]**.

Trois modes d&#39;insertion sont possibles :

1. Saisissez des adresses de contrôle uniques.  Pour cela, cliquez sur le bouton **[!UICONTROL Ajouter]** et définissez le contenu des champs de l&#39;adresse. Répétez l&#39;opération pour chaque adresse à ajouter.

1. Importer [modèles d&#39;adresses de contrôle](#creating-seed-address-template) et les adapter en fonction de vos besoins. Pour cela, cliquez sur le lien **[!UICONTROL Importer des adresses de contrôle...]** et sélectionnez le dossier contenant les modèles d&#39;adresses.

   Au besoin, une fois ajoutées, vous pouvez double-cliquer dessus ou cliquer sur le bouton **[!UICONTROL Détail...]** pour adapter le contenu des champs de chaque adresse.

1. Créez une condition pour sélectionner dynamiquement les adresses de contrôle à insérer. Pour cela, cliquez sur le lien **[!UICONTROL Editer la condition dynamique...]**, puis indiquez les paramètres de sélection des adresses de contrôle. Vous pouvez par exemple inclure toutes les adresses de contrôle contenues dans un dossier spécifique ou les adresses de contrôle appartenant à un service particulier de votre société.

   Un exemple est présenté dans la section [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

Pour les diffusions courrier, vous pouvez personnaliser le mode d&#39;insertion des adresses dans le fichier d&#39;extraction. Par défaut, elles sont insérées dans l&#39;ordre de tri du fichier de sortie, mais vous pouvez choisir de les insérer à la fin ou au début du fichier, ou aléatoirement parmi les destinataires de la cible principale.

## Ajouter des adresses de contrôle dans une opération {#seed-addresses-in-a-campaign}

Pour ajouter des adresses de contrôle dans la cible au niveau d&#39;une opération, sélectionnez l&#39;opération visée et cliquez sur l&#39;onglet **[!UICONTROL Edition]**.

Cliquez sur le bouton **[!UICONTROL Paramètres avancés de l&#39;opération...]** puis le lien **[!UICONTROL Adresses de contrôle]** . Les adresses de contrôle insérées depuis l&#39;opération sont ajoutées à la cible de chaque diffusion de l&#39;opération.

## Adresses de contrôle et tableau personnalisé {#using-an-external-recipient-table}

Si la table des diffusions est une table externe, vous devrez effectuer des paramétrages complémentaires. Le **[!UICONTROL nms:seedmember]** schéma doit être étendu. Un onglet est ajouté au niveau des adresses de contrôle afin de définir les champs adéquats.

Dans ce cas, pour ajouter des adresses de contrôle à la diffusion, renseignez les champs adéquats directement dans l&#39;onglet correspondant ou importez les modèles d&#39;adresses.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->

