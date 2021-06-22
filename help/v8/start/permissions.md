---
product: Adobe Campaign
title: Octroi d'autorisations pour Campaign v8
description: Découvrez comment octroyer des autorisations pour Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 89%

---

# Prise en main des autorisations

Dans Adobe Campaign, les utilisateurs sont des **opérateurs** et les **groupes d&#39;opérateurs** représentent des rôles d&#39;utilisateur.

Adobe Campaign est fourni avec des groupes d&#39;opérateurs natifs, tels que les Chargés d&#39;opération ou les Superviseurs de workflow. Tous les groupes natifs sont répertoriés dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=fr#default-groups)

En tant que membre d&#39;un groupe d&#39;opérateurs, un utilisateur dispose de droits, appelés &quot;Droits nommés&quot;, qui lui permettent d&#39;effectuer des opérations. Il a également accès aux données qui se trouvent dans les dossiers de la vue **Explorateur**. Un opérateur peut être membre de plusieurs groupes d&#39;opérateurs. Les droits et les autorisations d&#39;accès se cumulent alors.

Les droits nommés octroient des autorisations pour :

* L&#39;exécution d&#39;opérations
Par exemple, le bouton **Analyser** de l&#39;éditeur de diffusions est activé pour les membres du groupe **Chargés de diffusion** qui disposent du droit nommé **Préparer la diffusion**.

* L&#39;accès aux dossiers
L&#39;appartenance à des groupes d&#39;opérateurs peut permettre de bénéficier ou de se voir refuser des droits d&#39;accès aux dossiers, à travers la modification des paramètres de sécurité des dossiers. [Pour en savoir plus, consultez la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=fr#permissions-on-a-folder){target=&quot;_blank&quot;}. Par exemple, elle peut avoir un impact sur : l&#39;**accès en écriture** pour créer de nouvelles entités (telles que des diffusions, des profils, etc.), l&#39;**accès en lecture** pour utiliser des entités, l&#39;**accès en suppression** pour supprimer des entités.

**Apprenez-en davantage**  dans la documentation Adobe Campaign Classic v7 :

[!DNL :arrow_upper_right:] [Droits nommés natifs](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html?lang=fr){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Groupes d’opérateurs intégrés](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Étapes de configuration des autorisations](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=fr){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Paramètres de sécurité des dossiers](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}