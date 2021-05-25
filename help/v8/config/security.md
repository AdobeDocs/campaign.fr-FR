---
solution: Campaign v8
product: Adobe Campaign
title: Bonnes pratiques relatives à la sécurité Campaign
description: Prise en main des bonnes pratiques en matière de sécurité dans Campaign
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 46%

---

# Bonnes pratiques relatives à la sécurité Campaign {#ac-security}

En Adobe, nous prenons la sécurité de votre expérience numérique très au sérieux. Les pratiques de sécurité sont profondément enracinées dans nos processus internes de développement logiciel et d’exploitation et nos outils, et sont rigoureusement suivies par nos équipes interfonctionnelles afin de prévenir, de détecter et de réagir rapidement aux incidents.

De plus, notre collaboration avec des partenaires, des chercheurs de premier plan, des institutions de recherche sur la sécurité et d’autres organisations du secteur nous aide à rester au fait des dernières menaces et vulnérabilités et à intégrer régulièrement des techniques de sécurité avancées dans les produits et services que nous offrons.

## Confidentialité

La configuration et le renforcement de la confidentialité sont des éléments clés en matière d’optimisation de la sécurité. Voici quelques bonnes pratiques à suivre en matière de confidentialité :

* Protect de vos informations personnelles client en utilisant HTTPS au lieu de HTTP
* Utilisez la [restriction des vues PI](../dev/restrict-pi-view.md) pour protéger la confidentialité et empêcher l’utilisation abusive des données.
* Vérifiez que les mots de passe cryptés sont restreints
* Protégez les pages pouvant contenir des informations personnelles, telles que les pages miroir, les applications web, etc.

:speak_ballon: En tant qu’utilisateur Cloud Services géré, Adobe collaborera avec vous pour mettre en oeuvre ces configurations dans votre environnement.

## Personnalisation 

Lorsque vous ajoutez des liens personnalisés à votre contenu, évitez toujours toute personnalisation dans la partie du nom d’hôte de l’URL afin d’éviter des failles de sécurité potentielles. Les exemples suivants ne doivent jamais être utilisés dans tous les attributs d’URL &lt;`a href="">` ou `<img src="">` :

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restriction des données

Vous devez vous assurer que les mots de passe cryptés ne sont pas accessibles par un utilisateur authentifié avec de faibles privilèges. Pour ce faire, deux méthodes principales sont possibles : restreindre l’accès aux champs de mot de passe uniquement ou à l’entité entière ;

Cette restriction vous permet de supprimer les champs de mots de passe, mais laisse le compte externe accessible à tous les utilisateurs depuis l’interface. En savoir plus sur [cette page](../dev/restrict-pi-view.md).

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Schémas de données]**.

1. Créez une **[!UICONTROL Extension d’un schéma]**.

1. Sélectionnez **[!UICONTROL Compte externe]** (extAccount).

1. Dans le dernier écran, vous pouvez modifier votre nouveau srcSchema pour restreindre l&#39;accès à tous les champs de mot de passe :

   Vous pouvez remplacer l’élément principal (`<element name="extAccount" ... >`) par :

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
   >Vous pouvez remplacer `$(loginId) = 0 or $(login) = 'admin'` par `hasNamedRight('admin')` pour permettre à tous les utilisateurs disposant du droit d’administrateur de voir ces mots de passe.


## Gestion des accès

La gestion des accès joue un rôle important dans le renforcement de la sécurité. Vous trouverez ci-dessous quelques-unes des principales bonnes pratiques à appliquer.

* Créez suffisamment de groupes de sécurité.
* Vérifiez que chaque opérateur dispose des droits d’accès adéquats.
* Évitez d’utiliser l’opérateur admin et d’ajouter trop d’opérateurs au groupe admin.

:flèche_upper_right : En savoir plus dans la [documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator)

## Consignes de codage

Lorsque vous effectuez des tâches de développement dans Adobe Campaign (workflows, Javascript, JSSP, autres), suivez toujours ces instructions :

* **Scripts** : évitez si possible d’utiliser des instructions SQL. Utilisez des fonctions paramétrables plutôt que la concaténation de chaîne et évitez toute injection SQL en ajoutant les fonctions SQL à utiliser à la liste autorisée.

* **Sécurisation du modèle de données** : utilisez des droits nommés pour limiter les actions des opérateurs et ajoutez des filtres système (sysFilter).

* **Ajoutez des captchas dans les applications** web : ajoutez des captchas dans vos landing pages publiques et vos pages d&#39;abonnement.

:flèche_upper_right : En savoir plus dans la [documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic)
