---
title: Octroi d'autorisations pour Campaign v8
description: Découvrez comment octroyer des autorisations pour Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 100%

---

# Commencer avec les autorisations

Dans Adobe Campaign, les utilisateurs sont des **opérateurs** et les **groupes d’opérateurs** représentent des rôles d’utilisateur.

Un opérateur/une opératrice est un utilisateur/une utilisatrice Adobe Campaign qui possède des autorisations pour se connecter et effectuer des actions. Les opérateurs sont stockés par défaut dans le nœud **[!UICONTROL Administration > Gestion des accès > Opérateurs]**.

Adobe Campaign est fourni avec des groupes d’opérateurs natifs, tels que les Chargé(e)s d’opération ou les Superviseurs/superviseuses de workflow. Pour en savoir plus sur les autorisations, consultez [cette section](../start/gs-permissions.md)

En tant que membre d&#39;un groupe d&#39;opérateurs, un utilisateur dispose de droits, appelés &quot;Droits nommés&quot;, qui lui permettent d&#39;effectuer des opérations. Il a également accès aux données qui se trouvent dans les dossiers de la vue **Explorateur**. Un opérateur /une opératrice peut être membre de plusieurs groupes d’opérateurs. Les droits et les autorisations d’accès se cumulent alors.

Les droits nommés octroient des autorisations pour :

* L&#39;exécution d&#39;opérations
Par exemple, le bouton **Analyser** de l&#39;éditeur de diffusions est activé pour les membres du groupe **Chargés de diffusion** qui disposent du droit nommé **Préparer la diffusion**.

* L&#39;accès aux dossiers
L&#39;appartenance à des groupes d&#39;opérateurs peut permettre de bénéficier ou de se voir refuser des droits d&#39;accès aux dossiers, à travers la modification des paramètres de sécurité des dossiers. En savoir plus sur [cette page](../start/folder-permissions.md). Par exemple, elle peut avoir un impact sur : l&#39;**accès en écriture** pour créer de nouvelles entités (telles que des diffusions, des profils, etc.), l&#39;**accès en lecture** pour utiliser des entités, l&#39;**accès en suppression** pour supprimer des entités.

## Zones de sécurité

Chaque opérateur doit être associé à une zone pour se connecter à une instance et l’adresse IP de l’opérateur doit faire partie des adresses ou des plages d’adresses définies dans la zone de sécurité. La configuration des zones de sécurité est effectuée dans le fichier de configuration du serveur Adobe Campaign.

Un opérateur est lié à une zone de sécurité à partir de son profil dans la console, accessible dans le nœud **[!UICONTROL Administration > Gestion des accès > Opérateurs.]**

![](../assets/do-not-localize/speech.png)  En tant qu’utilisateur Managed Cloud Services, Adobe définit les zones de sécurité pour vous. Pour plus d’informations, [contactez Adobe](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**En savoir plus**

* [Droits nommés natifs](../start/gs-permissions.md)

* [Étapes de configuration des autorisations](../start/manage-permissions.md)
