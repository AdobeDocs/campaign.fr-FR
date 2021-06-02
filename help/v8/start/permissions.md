---
product: Adobe Campaign
title: Octroi d’autorisations pour Campaign v8
description: Découvrez comment octroyer des autorisations pour Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 4bd67cd3e4e88015d8044f07ca95927b6d7867f3
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 90%

---

# Prise en main des autorisations

Dans Adobe Campaign, les utilisateurs sont des **opérateurs** et les **groupes d’opérateurs** représentent des rôles d’utilisateur.

Adobe Campaign est fourni avec des groupes d’opérateurs natifs, tels que les Chargés d’opération ou les Superviseurs de workflow. Tous les groupes intégrés sont répertoriés dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=fr#default-groups)

En tant que membre d’un groupe d’opérateurs, un utilisateur dispose de droits, appelés « Droits nommés », qui lui permettent d’effectuer des opérations. Il a également accès aux données qui se trouvent dans les dossiers de la vue **Explorateur**. Un opérateur peut être membre de plusieurs groupes d’opérateurs. Les droits et les autorisations d’accès se cumulent alors.

Les droits nommés octroient des autorisations pour :

* L’exécution d’opérations
Par exemple, le bouton **Analyser** de l’éditeur de diffusions est activé pour les membres du groupe **Chargés de diffusion** qui disposent du droit nommé **Préparer la diffusion**.

* L’accès aux dossiers
L’appartenance à des groupes d’opérateurs peut permettre de bénéficier ou de se voir refuser des droits d’accès aux dossiers, à travers la modification des paramètres de sécurité des dossiers. [Pour en savoir plus, consultez la documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=fr#permissions-on-a-folder) de Campaign Classic v7. Par exemple, elle peut avoir un impact sur : l’**accès en écriture** pour créer de nouvelles entités (telles que des diffusions, des profils, etc.), l’**accès en lecture** pour utiliser des entités, l’**accès en suppression** pour supprimer des entités.

**En savoir plus** dans la documentation de Campaign Classic v7 :

[!DNL :arrow_upper_right:] [Droits nommés natifs](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html?lang=fr)

[!DNL :arrow_upper_right:] [Groupes d’opérateurs natifs](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

[!DNL :arrow_upper_right:] [Étapes de configuration des autorisations](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=fr)

[!DNL :arrow_upper_right:] [Paramètres de sécurité des dossiers](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder).