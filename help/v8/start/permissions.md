---
solution: Campaign v8
product: Adobe Campaign
title: Octroi d’autorisations à Campaign v8
description: Découvrez comment accorder des autorisations à Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 2%

---

# Prise en main des permissions

Dans Adobe Campaign, les utilisateurs sont **opérateurs** et les **groupes d’opérateurs** représentent des rôles d’utilisateur.

Adobe Campaign est fourni avec des groupes d’opérateurs intégrés tels que les responsables de campagne ou les responsables de workflow. Tous les groupes intégrés sont répertoriés dans [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

En tant que membre d’un groupe d’opérateurs, un utilisateur est autorisé à effectuer des opérations, appelées &quot;Droits nommés&quot;, et a accès à des données contenues dans des dossiers de la vue **Explorateur**. Un opérateur peut être membre de plusieurs groupes d&#39;opérateurs : les droits et les autorisations d’accès sont additifs.

Les droits nommés accordent des autorisations à :

* Exécution des opérations
Par exemple, le bouton **Analyser** dans l’éditeur de diffusion est activé pour les membres du groupe **Opérateur de diffusion** qui ont le **Préparer la diffusion** droit nommé

* Accès aux dossiers
L’appartenance à des groupes d’opérateurs peut accorder ou restreindre des droits d’accès aux dossiers en modifiant les [paramètres de sécurité des dossiers](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder). Par exemple, cela peut avoir un impact : **Accès en écriture** pour créer de nouvelles entités (comme des diffusions, des profils, etc.), **Accès en lecture** pour utiliser les entités, **Supprimer l’accès** pour supprimer des entités.

**En savoir plus**

* [Droits nommés intégrés](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html)

* [Groupes d’opérateurs intégrés](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

* [Procédure de configuration des autorisations](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html)
