---
product: campaign
title: Bonnes pratiques relatives aux interactions Adobe Campaign
description: Recommandations relatives à la gestion du module Interaction dans Adobe Campaign
source-git-commit: 7234ca65f785b005b11851a5cd88add8cddeff4f
workflow-type: ht
source-wordcount: '1164'
ht-degree: 100%

---

# Bonnes pratiques relatives aux interactions{#interaction-best-practices}

## Recommandations générales {#general-recommendations}

Une gestion des offres efficace dans Adobe Campaign requiert une attention toute particulière. Pour éviter tout problème, vous devez trouver le juste milieu entre le nombre de contacts et le nombre de catégories dʼoffres et le nombre dʼoffres.

Cette section présente les bonnes pratiques pour gérer le module **nteraction** dans Adobe Campaign, y compris les règles dʼéligibilité, les filtres prédéfinis, les activités de workflow et les options de bases de données.

* Lors de lʼ&#x200B;**implémentation et de la configuration des interactions**, vous devez tenir compte des recommandations suivantes :

   * Dans le cas du moteur batch (généralement utilisé dans les communications sortantes, telles que les emails), le débit est la préoccupation centrale, car plusieurs contacts peuvent être gérés simultanément. Le goulot d’étranglement typique est la performance de la base de données.
   * La principale contrainte du moteur unitaire (généralement utilisé dans les communications entrantes, telles qu’une bannière sur un site web) est la latence, car quelqu’un attend une réponse. Le goulot d’étranglement typique est la performance de l’unité centrale.
   * La conception du catalogue dʼoffres a un impact considérable sur la performance dʼAdobe Campaign.
   * Lorsque vous travaillez avec un nombre élevé dʼoffres, il est recommandé de les diviser en plusieurs catalogues dʼoffres.

* Retrouvez ci-dessous quelques bonnes pratiques relatives à lʼutilisation des **règles dʼéligibilité** :

   * Simplifiez les règles. La complexité des règles a une incidence sur la performance, car elle prolonge la recherche. Une règle est complexe si elle comprend plus de cinq conditions.
   * Afin dʼaccroître la performance, les règles peuvent être décomposées en différents filtres prédéfinis partagés entre des offres multiples.
   * Placez les règles de catégorie d’offres les plus restrictives à la position la plus élevée possible dans l’arbre. De cette manière, elles excluront le plus grand nombre de contacts en premier, ce qui réduit le nombre de cibles et empêche leur traitement par d’autres règles.
   * Placez les règles les plus coûteuses en termes de temps ou de traitement en bas de l’arbre. De cette façon, ces règles seront uniquement exécutées sur l’audience cible restante.
   * Démarrez au niveau d’une catégorie spécifique afin d’éviter d’analyser l’ensemble de l’arbre.
   * Pour économiser le temps de traitement, précalculez les agrégats au lieu de créer des règles complexes avec des jointures. Pour ce faire, essayez de stocker les données client dans une table de référence qui peut être consultée au sein des règles d’éligibilité.
   * Utilisez un nombre minimum de poids pour limiter le nombre de requêtes.
   * Il est recommandé de disposer d’un nombre limité d’offres par emplacement d’offre. Cela accélère la récupération des offres dans n’importe quel emplacement donné.
   * Servez-vous d’index, en particulier pour les colonnes de recherche fréquemment utilisées.

* Vous trouverez ci-dessous quelques bonnes pratiques concernant la **table de proposition** :

   * Utilisez un nombre minimum de règles pour que le traitement soit le plus rapide possible.
   * Limitez le nombre d’enregistrements dans la table de propositions : conservez uniquement les enregistrements requis pour contrôler la mise à jour de son statut et ce que requièrent les règles, puis archivez-les dans un autre système.
   * Réalisez une maintenance de base de données intensive sur la table de propositions, par exemple, en reconstruisant les index ou en recréant la table.
   * Limitez le nombre de propositions par cible. N’en définissez pas davantage par rapport à ce que vous allez utiliser.
   * Dans la mesure du possible, évitez les jointures dans les critères des règles.

## Conseils pour la gestion des offres {#tips-managing-offers}

Cette section contient des conseils plus détaillés sur la gestion des offres et lʼutilisation du module Interaction dans Adobe Campaign.

### Plusieurs emplacements dans un e-mail {#multiple-offer-spaces}

Lorsque vous incluez des offres dans des diffusions, elles sont généralement sélectionnées en amont dans le workflow Campaign par le biais dʼune activité de workflow **Enrichissement** (ou dʼune autre activité similaire).

Lors de la sélection des offres dans une activité **Enrichissement**, vous pouvez choisir lʼemplacement à utiliser. Cependant, quel que soit l&#39;emplacement sélectionné, le menu de personnalisation de la diffusion dépend de l&#39;espace d&#39;offre configuré dans la diffusion.

Dans l&#39;exemple ci-dessous, l&#39;emplacement d&#39;offre sélectionné dans la diffusion est **[!UICONTROL Email (Environnement - Destinataire)]**:

![](assets/Interaction-best-practices-offer-space-selected.png)

Si l&#39;emplacement d&#39;offre sélectionné dans la diffusion ne dispose pas d&#39;une fonction de rendu HTML configurée, vous ne la verrez pas dans le menu de diffusion et elle ne sera pas disponible pour pouvoir le sélectionner. Cette situation est indépendante de lʼemplacement sélectionné dans lʼactivité **Enrichissement**.

Dans l&#39;exemple ci-dessous, la fonction de rendu HTML est disponible dans la liste déroulante, car l&#39;emplacement d&#39;offre sélectionné dans la diffusion comporte une fonction de rendu :

![](assets/Interaction-best-practices-HTML-rendering.png)

Cette fonction insère du code tel que : `<%@ include proposition="targetData.proposition" view="rendering/html" %>`.

Lorsque vous sélectionnez la proposition, la valeur de l&#39;attribut **[!UICONTROL vue]** est la suivante :
* &quot;render/html&quot; : rendu HTML. Il utilise la fonction de rendu HTML.
* &quot;offer/view/html&quot; : contenu HTML. Il n&#39;utilise pas la fonction de rendu HTML et n&#39;inclut que le champ HTML.

Lorsque vous incluez plusieurs emplacements d&#39;offre dans une diffusion par email unique alors que seuls certains d&#39;entre eux ont des fonctions de rendu, vous devez vous rappeler des offres et des emplacements d&#39;offre correspondants, et dans ces emplacements, ceux dotés de fonctions de rendu.

Pour éviter tout problème, il est donc recommandé de définir une fonction de rendu HTML pour tous les emplacements d&#39;offre, même si le vôtre ne nécessite que du contenu HTML.

### Définition du rang dans la table du log des propositions {#rank-proposition-log-table}

Les emplacements d&#39;offre permettent de stocker des données dans la table des propositions après génération ou acceptation de propositions :

![](assets/Interaction-best-practices-offer-space-storage.png)

Toutefois, cela ne s&#39;applique qu&#39;aux interactions entrantes.

Il est également possible de stocker des données supplémentaires dans la table des propositions si vous utilisez les interactions sortantes, ou les offres sortantes sans le module Interaction.

Un champ de la table temporaire de workflow dont le nom correspond à celui d&#39;un champ de la table des propositions est copié dans le même champ de la table des propositions.

Par exemple, en cas de sélection manuelle dʼune offre (sans le module Interaction) dans une activité de workflow **Enrichissement**, les champs standard sont définis comme suit :

![](assets/Interaction-best-practices-manual-offer-std-fields.png)

Il est possible dʼajouter dʼautres champs, par exemple un champ `@rank` :

![](assets/Interaction-best-practices-manual-offer-add-fields.png)

Puisquʼil existe un champ appelé `@rank` dans la table des propositions, la valeur contenue dans la table temporaire du workflow sera copiée.

Pour plus dʼinformations sur le stockage de champs supplémentaires dans la table des propositions, consultez [cette section](interaction-send-offers.md#storing-offer-rankings-and-weights).

Pour les offres sortantes avec le module Interaction, cette possibilité est utile lorsque plusieurs offres sont sélectionnées et que vous souhaitez enregistrer l&#39;ordre dans lequel elles seront affichées dans un email.

Vous pouvez également stocker des métadonnées supplémentaires directement dans la table des propositions, par exemple le niveau de dépense actuel, pour conserver des historiques enregistrés relatifs aux dépenses au moment de la génération des offres.

En cas dʼutilisation dʼune interaction sortante, il est possible dʼajouter le champ `@rank` comme dans lʼexemple ci-dessus. Cependant, sa valeur est automatiquement définie en fonction de lʼordre renvoyé par le module Interaction. Par exemple, si vous utilisez le module Interaction pour sélectionner trois offres, les valeurs 1, 2 et 3 sont renvoyées dans le champ `@rank`.

Lorsque vous utilisez le module Interaction et que vous sélectionnez manuellement des offres, lʼutilisateur peut combiner les deux approches. Par exemple, lʼutilisateur peut définir manuellement le champ `@rank` sur 1 pour lʼoffre sélectionnée manuellement et utiliser une expression telle que `"1 + @rank"` pour les offres renvoyées par le module Interaction. En supposant que le module Interaction sélectionne trois offres, les offres renvoyées par les deux approches seront classées de 1 à 4 :

![](assets/Interaction-best-practices-manual-offer-combined.png)

### Extension du schéma nms:offer {#extending-nms-offer-schema}

Lors de l&#39;extension du schéma nms:offer, veillez à suivre la structure prête à l&#39;emploi déjà configurée :
* Définissez un nouveau champ pour le stockage du contenu sous `<element name="view">`.
* Un nouveau champ doit être défini deux fois. Une fois sous forme de champ XML normal, et une autre fois sous forme de champ XML CDATA en ajoutant &quot;_jst&quot; au nom. Par exemple :

   ```
   <element label="Price" name="price" type="long" xml="true"/>
   <element advanced="true" label="Script price" name="price_jst" type="CDATA" xml="true"/>
   ```

* Un champ contenant des URL à tracker doit être placé sous `<element name="trackedUrls">`, lequel se trouve sous `<element name="view" >`.
