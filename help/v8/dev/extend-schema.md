---
solution: Campaign Classic
product: campaign
title: Étendre les schémas Campaign
description: Découvrez comment étendre les schémas Campaign
translation-type: tm+mt
source-git-commit: 779542ab70f0bf3812358884c698203bab98d1ce
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 78%

---

# Étendre un schéma{#extend-schemas}

Cet article décrit comment configurer des schémas d&#39;extension afin d&#39;étendre le modèle de données conceptuel de la base de données Adobe Campaign.

: bulb: Pour une meilleure compréhension des tableaux intégrés de Campaign et de leur interaction, consultez [cette page](datamodel.md).

La structure physique et logique des données véhiculées dans l&#39;application est décrite en XML et respecte une grammaire propre à Adobe Campaign appelée **schéma**.

Un schéma est un document XML associé à une table de la base de données, il définit la structuration des données et décrit la définition SQL de la table :

* le nom de la table,
* des champs ;
* les liens avec les autres tables,

mais aussi la structure XML utilisée pour stocker les données :

* Eléments et attributs
* la hiérarchie entre les éléments,
* les types des éléments et des attributs,
* Les valeurs par défaut
* les libellés, les descriptions et autres propriétés.

Les schémas servent à définir en base une entité. A chaque entité, correspond un schéma.

## Syntaxe des schémas {#syntax-of-schemas}

L’élément racine du schéma est **`<srcschema>`**. Il contient les sous-éléments **`<element>`** et **`<attribute>`**.

Le premier sous-élément **`<element>`** correspond à la racine de l’entité.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>L&#39;élément racine de l&#39;entité porte le nom du schéma.

![](assets/schema_and_entity.png)

Les balises **`<element>`** définissent les noms des éléments d’entité. Les balises **`<attribute>`** du schéma définissent les noms des attributs dans les balises **`<element>`** auxquelles elles ont été liées.

## Identification d&#39;un schéma {#identification-of-a-schema}

Un schéma de données est identifié par son nom et son espace de noms.

Un espace de noms permet de regrouper un ensemble de schémas par centres d&#39;intérêt. Par exemple, on utilisera l&#39;espace de noms **cus** pour le paramétrage spécifique aux clients (**customers**).

>[!CAUTION]
>
>Par convention, le nom de l&#39;espace de noms doit être concis et ne comprendre que des caractères autorisés conformes aux règles de nommage des noms XML.
>
>Les identifieurs ne doivent pas commencer par des caractères numériques.

Certains espaces de noms sont réservés pour la description des entités systèmes nécessaires au bon fonctionnement de l&#39;application Adobe Campaign :

* **xxl** : concernant les schémas de base de données Cloud,
* **xtk** : relatif aux données système de la plateforme,
* **nl** : relatif à l&#39;utilisation globale de l&#39;application,
* **nms** : relatif à la diffusion (destinataire, diffusion, tracking, etc.),
* **ncm** : relatif à la gestion de contenu,
* **temp** : réservé aux schémas temporaires.

La clé d&#39;identification d&#39;un schéma est une chaîne créée à l&#39;aide de l&#39;espace de nommage et du nom séparés par deux-points ; par exemple : **nms:destinataire**.
