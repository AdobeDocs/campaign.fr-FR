---
solution: Campaign
product: Adobe Campaign
title: Meilleures pratiques de sécurité Campaign
description: Commencer avec les meilleures pratiques de sécurité de Campaign
translation-type: tm+mt
source-git-commit: 5592dd4e79391d953a4bc54cdd47475417e07b56
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 46%

---

# Meilleures pratiques de sécurité Campaign {#ac-security}

En Adobe, nous prenons la sécurité de votre expérience numérique très au sérieux. Les pratiques de sécurité sont profondément ancrées dans nos processus internes de développement logiciel et d&#39;exploitation et nos outils, et sont rigoureusement suivies par nos équipes interfonctionnelles afin de prévenir, de détecter et de réagir rapidement aux incidents.

En outre, notre collaboration avec des partenaires, des chercheurs de premier plan, des instituts de recherche en sécurité et d&#39;autres organisations du secteur nous aide à nous tenir au courant des dernières menaces et vulnérabilités et nous incorporons régulièrement des techniques de sécurité avancées dans les produits et services que nous offres.

## Confidentialité

La configuration et le renforcement de la confidentialité sont des éléments clés en matière d’optimisation de la sécurité. Voici quelques bonnes pratiques à suivre en matière de confidentialité :

* Protect vos informations personnelles client (PI) en utilisant HTTPS au lieu de HTTP
* Utiliser [la restriction de vue PI](../dev/restrict-pi-view.md) pour protéger la confidentialité et empêcher l&#39;utilisation abusive des données
* Vérifiez que les mots de passe cryptés sont restreints
* Protégez les pages pouvant contenir des informations personnelles, telles que les pages miroir, les applications web, etc.

:speak_bulon: En tant qu’utilisateur Cloud Services géré, l’Adobe collaborera avec vous pour mettre en oeuvre ces configurations sur votre environnement.

## Personnalisation 

Lorsque vous ajoutez des liens personnalisés à votre contenu, évitez toujours toute personnalisation dans la partie du nom d’hôte de l’URL afin d’éviter des failles de sécurité potentielles. Les exemples suivants ne doivent jamais être utilisés dans tous les attributs d’URL &lt;`a href="">` ou `<img src="">` :

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restriction des données

Vous devez vous assurer que les mots de passe cryptés ne sont pas accessibles par un utilisateur authentifié avec de faibles privilèges. Pour ce faire, il existe deux moyens principaux : limiter l&#39;accès aux champs de mot de passe uniquement ou à l&#39;entité entière.

Cette restriction vous permet de supprimer des champs de mots de passe, mais laisse le compte externe accessible à tous les utilisateurs depuis l’interface. En savoir plus sur [cette page](../dev/restrict-pi-view.md).

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Schémas de données]**.

1. Créez une **[!UICONTROL Extension d’un schéma]**.

1. Sélectionnez **[!UICONTROL Compte externe]** (extAccount).

1. Dans le dernier écran, vous pouvez modifier votre nouveau srcSchema pour restreindre l’accès à tous les champs de mot de passe :

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
   >Vous pouvez remplacer `$(loginId) = 0 or $(login) = 'admin'` par `hasNamedRight('admin')` pour permettre à tous les utilisateurs disposant du droit d’administration de voir ces mots de passe.


## Gestion des accès

La gestion des accès joue un rôle important dans le renforcement de la sécurité. Vous trouverez ci-dessous quelques-unes des principales bonnes pratiques à appliquer.

* Créez suffisamment de groupes de sécurité.
* Vérifiez que chaque opérateur dispose des droits d’accès adéquats.
* Évitez d’utiliser l’opérateur admin et d’ajouter trop d’opérateurs au groupe admin.

:flèche_supérieur_droite : En savoir plus sur [la documentation Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator)

## Instructions de codage

Lorsque vous effectuez des tâches de développement dans Adobe Campaign (workflows, Javascript, JSSP, autres), suivez toujours ces instructions :

* **Scripts** : évitez si possible d’utiliser des instructions SQL. Utilisez des fonctions paramétrables plutôt que la concaténation de chaîne et évitez toute injection SQL en ajoutant les fonctions SQL à utiliser à la liste autorisée.

* **Sécurisation du modèle de données** : utilisez des droits nommés pour limiter les actions des opérateurs et ajoutez des filtres système (sysFilter).

* **Ajoutez captchas dans les applications** Web : ajoutez des casquettes dans vos landings page publics et vos pages d’abonnement.

:flèche_supérieur_droite : En savoir plus sur [la documentation Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic)
