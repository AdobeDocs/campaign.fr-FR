---
title: Bonnes pratiques de sécurité de Campaign
description: Prise en main des bonnes pratiques de sécurité de Campaign
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 97%

---

# Bonnes pratiques de sécurité de Campaign {#ac-security}

Chez Adobe, nous prenons la sécurité de votre expérience digitale très au sérieux. Les bonnes pratiques de sécurité sont profondément ancrées dans nos processus internes de développement et d&#39;exploitation de logiciels ainsi que dans nos outils. Nos équipes transverses suivent scrupuleusement ces différentes règles afin d&#39;éviter les incidents, mais aussi de pouvoir les détecter et y répondre rapidement.

De plus, notre travail en collaboration avec des partenaires, des chercheurs de premier plan, des instituts de recherche en sécurité et d&#39;autres organisations du secteur nous aide à nous tenir informés des dernières menaces et vulnérabilités. Nous incorporons ainsi régulièrement des techniques de sécurité avancées à nos produits et services.

## Confidentialité

La configuration et le renforcement de la confidentialité sont des éléments clés en matière d&#39;optimisation de la sécurité. Voici quelques bonnes pratiques à suivre en matière de confidentialité :

* Protégez les informations personnelles (PI) de vos clients en utilisant HTTPS au lieu de HTTP.
* Utilisez la [limitation de l&#39;affichage des PI](../dev/restrict-pi-view.md) pour protéger la confidentialité et empêcher toute utilisation abusive des données.
* Vérifiez que les mots de passe chiffrés sont restreints.
* Protégez les pages pouvant contenir des informations personnelles, telles que les pages miroir, les applications web, etc.

![](../assets/do-not-localize/speech.png)  En tant qu’utilisateur Managed Cloud Services, Adobe vous accompagne dans l’implémentation de ces configurations dans votre environnement.


## Gestion des accès

La gestion des accès joue un rôle important dans le renforcement de la sécurité. Vous trouverez ci-dessous quelques-unes des principales bonnes pratiques à appliquer.

* Créez suffisamment de groupes de sécurité.
* Vérifiez que chaque opérateur dispose des droits d&#39;accès adéquats.

Pour en savoir plus sur les autorisations, consultez [cette section](../start/gs-permissions.md)

## Instructions de codage

Lorsque vous effectuez des tâches de développement dans Adobe Campaign (workflows, Javascript, JSSP, autres), suivez toujours ces instructions :

* **Scripts** : évitez si possible d&#39;utiliser des instructions SQL. Utilisez des fonctions paramétrables plutôt que la concaténation de chaîne et évitez toute injection SQL en ajoutant les fonctions SQL à utiliser à la liste autorisée.

* **Sécurisation du modèle de données** : utilisez des droits nommés pour limiter les actions des opérateurs et ajoutez des filtres système (sysFilter).

* **Ajout de captchas dans les applications web** : ajoutez des captchas dans vos pages d&#39;abonnement et landing pages publiques.

![](../assets/do-not-localize/book.png) En savoir plus dans [Documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=fr#installing-campaign-classic){target="_blank"}


## Personnalisation

Lorsque vous ajoutez des liens personnalisés à votre contenu, évitez toujours toute personnalisation dans la partie du nom d&#39;hôte de l&#39;URL afin d&#39;éviter des failles de sécurité potentielles. Les exemples suivants ne doivent jamais être utilisés dans tous les attributs d&#39;URL &lt;`a href="">` ou `<img src="">` :

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restriction des données

Vous devez vous assurer que les mots de passe chiffrés ne sont pas accessibles par un utilisateur authentifié avec de faibles privilèges. Pour ce faire, il existe deux méthodes : restreindre l&#39;accès aux champs de mots de passe uniquement ou à l&#39;entité entière.

Cette restriction vous permet de supprimer les champs de mots de passe. Le compte externe reste toutefois accessible par tous les utilisateurs dans l&#39;interface. Apprenez-en davantage en consultant [cette page](../dev/restrict-pi-view.md).

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Schémas de données]**.

1. Créez une **[!UICONTROL Extension d&#39;un schéma]**.

1. Sélectionnez **[!UICONTROL Compte externe]** (extAccount).

1. Dans le dernier écran, vous pouvez modifier le nouveau srcSchema afin de restreindre l&#39;accès à tous les champs de mots de passe :

   Vous pouvez remplacer l&#39;élément principal (`<element name="extAccount" ... >`) par :

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   Le srcSchema étendu peut ressembler à ceci :

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >Vous pouvez remplacer `$(loginId) = 0 or $(login) = 'admin'` par `hasNamedRight('admin')` pour autoriser tous les utilisateurs disposant du droit admin à voir ces mots de passe.


## Gestion des accès

La gestion des accès joue un rôle important dans le renforcement de la sécurité. Vous trouverez ci-dessous quelques-unes des principales bonnes pratiques à appliquer.

* Créez suffisamment de groupes de sécurité.
* Vérifiez que chaque opérateur dispose des droits d&#39;accès adéquats.

En savoir plus sur les autorisations [dans cette section](../start/gs-permissions.md).

## Instructions de codage

Lorsque vous effectuez des tâches de développement dans Adobe Campaign (workflows, Javascript, JSSP, autres), suivez toujours ces instructions :

* **Scripts** : évitez si possible d&#39;utiliser des instructions SQL. Utilisez des fonctions paramétrables plutôt que la concaténation de chaîne et évitez toute injection SQL en ajoutant les fonctions SQL à utiliser à la liste autorisée.

* **Sécurisation du modèle de données** : utilisez des droits nommés pour limiter les actions des opérateurs et ajoutez des filtres système (sysFilter).

* **Ajout de captchas dans les applications web** : ajoutez des captchas dans vos pages d&#39;abonnement et landing pages publiques.

![](../assets/do-not-localize/book.png) En savoir plus dans [Documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=fr#installing-campaign-classic){target="_blank"}
