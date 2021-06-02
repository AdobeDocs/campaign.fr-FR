---
product: Adobe Campaign
title: 'Gestion des clés dans Campaign '
description: Prise en main de la gestion des clés
source-git-commit: 08c1f2fbe79845fe54670e25ac4a63ab65517513
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Gestion des clés et unicité {#key-management}

Dans Campaign v8, la clé Principale est un UUID (Universally Unique IDentifier), qui est une chaîne sur les caractères. Pour créer cet UUID, l’élément principal du schéma doit contenir les attributs **autouuid** et **autopk** définis sur **true**.

Adobe campaign v8 est fourni avec Snowflake comme base de données. L’architecture répartie de la base de données du Snowflake ne fournit pas de mécanismes permettant de gérer l’unicité d’une clé dans un tableau : les utilisateurs finaux assurent la cohérence des clés au sein de la base de données Adobe Campaign.

Pour préserver la cohérence de la base de données relationnelle, il est obligatoire d’éviter les doublons sur les clés, et notamment sur les Principales. Les doublons sur des clés Principales entraînent des problèmes avec les activités de workflow de gestion des données telles que **Requête**, **Réconciliation**, **Mise à jour de données**, etc.

Adobe Campaign propose de puissants outils de gestion des données pour réconcilier les données, veiller à insérer ou mettre à jour les données en fonction de leur présence dans la base de données (**Réconciliation**) et supprimer les doublons avant l’ingestion de données (**Déduplication**). Adobe recommande, en règle générale, d’adopter une stratégie [Détecter](#detect-duplicates) et [Corriger](#correct-duplicates) dans le cadre de votre processus de gestion des données global, en cas de chargement de clés dupliquées dans la base de données.

## Détecter les doublons{#detect-duplicates}

Campaign est fourni avec une nouvelle barrière de sécurité qui supprime automatiquement tout UUID dupliqué d’une audience lors de la préparation de la diffusion. Ce nouveau mécanisme empêche toute erreur lors de la préparation d&#39;une diffusion.

En tant qu&#39;utilisateur final, vous pouvez vérifier ces informations dans les logs de diffusion : certains destinataires peuvent être exclus de la cible principale en raison de la clé dupliquée. Dans ce cas, l&#39;avertissement suivant s&#39;affiche : `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/delivery-log-duplicates.png)

Dans ce cas, vous pouvez créer un workflow pour identifier les clés en double. Vous pourrez alors corriger ces clés. Pour ce faire, suivez les étapes ci-après :

1. Créez un nouveau workflow.

   ![](assets/new-wf.png)

1. Ajouter une activité **Requête**
1. Sélectionnez la table **Destinataire**

   ![](assets/add-query-on-rcp.png)

1. Ajoutez une activité **Déduplication** et dédupliquez-la sur la clé Principale (UUID). Conserver un seul doublon et cochez l&#39;option **Générer le complémentaire** pour créer une transition sortante pour le ou les doublons.

   ![](assets/deduplicate.png)

1. Enregistrez le ou les doublons dans une liste à l&#39;aide d&#39;une activité Mise à jour de liste .

   ![](assets/list-update.png)

Vous pouvez désormais accéder directement aux destinataires dupliqués depuis la liste. Même si la transition ne contient que l&#39;une des lignes dupliquées, tous les doublons seront consignés dans la liste.


## Corriger les doublons{#correct-duplicates}

Pour corriger les doublons, les clients doivent mettre à jour les données de Campaign. Le type d’action est étroitement lié à la nature des doublons et à la mise en oeuvre. Nous pouvons faire face à de multiples cas qui doivent nécessiter une stratégie d’atténuation différente (suppression, fusion ou mise à jour).

>[!IMPORTANT]
>
>Les clés Principales dupliquées vous empêchent d’utiliser des activités de workflow intégrées pour sélectionner ou mettre à jour une ligne spécifique. En raison de l’UUID dupliqué, la déduplication des données échoue et peut affecter l’intégrité de votre base de données. Il est donc vivement recommandé de corriger les doublons.

Par exemple :

* **Cas 1**  - Destinataires en double partageant le même UUID et les mêmes informations de profil (même email, prénom, etc.) : les destinataires ressemblent à de &quot;vrais&quot; doublons et la limitation pourrait être de supprimer un des doublons.
Une autre approche pourrait consister à fusionner les informations d’un destinataire dans l’autre.

* **2e cas**  : destinataires en double avec le même UUID mais des informations de profil différentes (email, prénom, etc.):
cette fois-ci, il semble qu&#39;il existe différents profils et que vous vouliez conserver les deux dans la base de données Campaign, ce qui signifie que nous préférons peut-être simplement mettre à jour l&#39;un des doublons générant un nouvel UUID. [En savoir plus dans cet exemple](#deduplicate-sample).

Selon votre stratégie de limitation, vous pouvez toujours interroger la liste à partir d’un autre workflow, puis appliquer la mise à jour selon vos besoins. Pour plus d’informations, contactez l’Adobe.

### Exemple de déduplication{#deduplicate-sample}

En cas de doublon de destinataires, vous pouvez conserver les deux enregistrements dans la base de données Campaign. Dans ce cas, vous devez mettre à jour l’un d’eux avec un nouvel UID.

Pour exécuter une requête SQL de mise à jour sur Cloud Database, vous pouvez utiliser l’activité de workflow **Gestion des données SQL** et exécuter la mise à jour SQL suivante :

```sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

Une fois la ligne sélectionnée mise à jour avec un nouvel UUID, vous pouvez vérifier la ligne mise à jour dans l’interface et constater que l’UUID a été mis à jour comme prévu. Vous pouvez également détecter des doublons dans la base de données en exécutant le workflow **Détecter les doublons** [comme expliqué ici](#detect-duplicates).
