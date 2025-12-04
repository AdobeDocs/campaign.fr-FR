---
title: Suivre les liens personnalisés
description: Découvrez comment effectuer le suivi des liens personnalisés dans les emails
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 50%

---

# Suivre les liens personnalisés {#tracking-personalized-links}

Les liens inclus dans le contenu des emails qui comportent des éléments de personnalisation ont besoin d&#39;une syntaxe spécifique pour être suivis.

L’utilisation de JavaScript dans le contenu des emails (HTML ou Texte) vous permet de générer et d&#39;envoyer du contenu dynamique aux destinataires, avec deux restrictions :

* Le script ne peut pas accéder directement à la base de données (la fonction SQL et les fonctions API ne sont pas disponibles),
* Adobe Campaign doit être en mesure de détecter les URL afin que les liens puissent être suivis.

## Instructions de pré-traitement {#pre-processing-instructions}

Vous pouvez ajouter des instructions de pré-traitement spécifiques pour effectuer le script et le suivi de l’URL. Ces instructions doivent être écrites en JavaScript et commencer par `<%@`.

Par exemple :

```
<%@ value object="myObject" xpath="@myField" %>
```

Cette instruction récupère la valeur du champ `myField` de l’objet `myObject`.

## Détection des URL {#url-detection}

Pour la détection du tracking, Adobe Campaign incorpore [Tidy](https://www.html-tidy.org/) pour analyser la source HTML et détecter le modèle. Il répertorie toutes les URL du contenu afin qu’elles puissent être suivies individuellement. Adobe Campaign utilise à nouveau Tidy pour remplacer l&#39;URL (`http://myurl.com`) par une URL pointant vers le serveur de redirection d&#39;Adobe Campaign.

Par exemple, dans le contenu initial : `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>` est remplacé pour un destinataire particulier par : `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`

Où :

* « h » signifie du contenu HTML (ou « t » pour le contenu texte).
* 617791 correspond à l&#39;identifiant du message/identifiant du broadLog (hexadécimal).
* 71ffa3 correspond à l&#39;identifiant NmsDelivery (hexadécimal).
* 71ffa8 correspond à l&#39;identifiant NmsTrackingUrl (hexadécimal).
* p1, p2, etc., sont tous les paramètres à remplacer dans l&#39;URL.

### Exemple de non-détection {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>` fonctionne et envoie le contenu de la page web par email aux destinataires. Mais aucun des liens n&#39;est tracké. La raison en est que le MTA exécute `"<%=getURL(..."` pour chaque email avant de l’envoyer. Cela peut être différent pour chaque destinataire, de sorte qu’Adobe Campaign ne peut pas connaître les URL de tracking et leur attribuer un identifiant de balise.

Lorsque la page à télécharger est la même pour tous les destinataires, il est recommandé d’utiliser les méthodes suivantes :

```
<%@ include url="http://mynewsletter.com" %>
```

Dans ce cas, la page est téléchargée pendant l’analyse, avant la détection du tracking. Adobe Campaign peut ainsi découvrir les liens, attribuer un identifiant de balise et les tracké.

### Modèle recommandé {#recommended-pattern}

Après avoir traité `<%@` instructions, l’URL à tracker doit respecter la syntaxe suivante :

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>Tous les autres modèles ne sont pas pris en charge par Adobe et doivent être évités afin d&#39;éviter les éventuelles lacunes en matière de sécurité.

## Paramètres de l&#39;URL {#url-parameters}

Pour garantir le suivi correct des URL personnalisées, vous devez utiliser la fonction `escapeUrl()` ou la méthode de codage appropriée pour les paramètres de vos URL.

**Exemple :**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

Vous aurez ainsi la garantie que le paramètre personnalisé est correctement encodé et suivi par Adobe Campaign.

## Bouclage avec `<%@ foreach %>` {#foreach}

L’instruction `<%@ foreach %>` vous permet d’effectuer une itération sur des tableaux d’objets chargés dans la diffusion pour effectuer le suivi de liens individuels liés aux objets.

### Syntaxe

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**Paramètres:**

* **`object`** : nom de l’objet de départ (généralement un objet de script supplémentaire, mais il peut s’agir d’une diffusion)
* **`xpath`** (facultatif) : XPath de la collection sur laquelle effectuer la boucle. La valeur par défaut est « . », ce qui signifie que l’objet est le tableau sur lequel effectuer une boucle
* **`index`** (facultatif) : si xpath n’est pas « . » et objet est un tableau lui-même, index d’élément de l’objet (commence à 0)
* **`item`** (facultatif) : nom d’un nouvel objet accessible avec des `<%@ value %>` à l’intérieur de la boucle foreach. La valeur par défaut est le nom du lien dans le schéma

### Exemple

Dans les propriétés/personnalisation de la diffusion, chargez un tableau d’articles et une table de relations entre le destinataire et les articles.

Vous pouvez afficher des liens vers ces articles avec un suivi individuel :

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

Cela permet à Adobe Campaign de suivre l’article spécifique sur lequel chaque destinataire a cliqué, plutôt que de simplement suivre l’utilisateur sur lequel un lien d’article a été cliqué.

## Bonnes pratiques {#best-practices}

* Utilisez toujours la fonction `escapeUrl()` pour les paramètres d’URL dynamiques
* Utilisez `<%@ foreach %>` lorsque vous devez effectuer le suivi d’éléments individuels dans des collections
* Testez le tracking avant d’envoyer votre diffusion pour vous assurer que tous les liens fonctionnent correctement
* Vérifier que les liens personnalisés sont correctement formatés dans le contenu de la diffusion
* Vérifiez les logs de tracking pour vous assurer que les paramètres personnalisés sont correctement capturés

## Rubriques connexes {#related-topics}

* [Découvrez comment configurer des liens suivis](tracked-links.md)
* [Découvrez comment configurer les options de tracking d’URL](url-tracking.md)
* [Découvrez comment ajouter des champs de personnalisation.](personalization-fields.md)

