---
solution: Campaign
product: Adobe Campaign
title: Octroi d’autorisations à Campaign v8
description: Découvrez comment accorder des autorisations à Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 2%

---

# Prise en main des permissions

En Adobe Campaign, les utilisateurs sont **opérateurs** et **groupes d’opérateurs** représentent des rôles d’utilisateur.

Adobe Campaign est fourni avec des groupes d’opérateurs intégrés tels que les gestionnaires de Campaign ou les superviseurs de flux de travail. Tous les groupes intégrés sont répertoriés dans [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

En tant que membre d’un groupe d’opérateurs, un utilisateur a les droits d’effectuer des opérations, appelées &quot;Droits nommés&quot;, et a accès aux données, qui se trouvent dans les dossiers de la vue **Explorateur**. Un opérateur peut être membre de plusieurs groupes d’opérateurs : droits et autorisations d’accès sont additifs.

Les droits nommés accordent des autorisations à :

* Exécution d’opérations
Par exemple, le bouton **Analyser** de l’éditeur de Diffusions est activé pour les membres du groupe **Opérateur de Diffusion** qui ont le **Préparer la Diffusion** nommé à droite.

* Accès aux dossiers
L&#39;appartenance à des groupes d&#39;opérateurs peut accorder ou restreindre des droits d&#39;accès aux dossiers, en modifiant les paramètres de [sécurité des dossiers](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder). Par exemple, elle peut avoir un impact : **Accès en écriture** pour créer de nouvelles entités (telles que des diffusions, des profils, etc.), **Accès en lecture** pour utiliser des entités, **Supprimer l&#39;accès** pour supprimer des entités.

**En savoir plus**

* [Droits nommés intégrés](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html)

* [Groupes d&#39;opérateurs intégrés](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

* [Procédure de configuration des autorisations](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html)
