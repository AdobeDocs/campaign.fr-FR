---
title: Notes de mise à jour anticipées de Campaign v8
description: Version anticipée de Campaign v8
feature: Release Notes
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: ht
source-wordcount: '586'
ht-degree: 100%

---

# Notes de mise à jour anticipées {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign .v8 Ce contenu est sujet à des modifications sans préavis jusqu’à la date de mise à jour. Les notes de mise à jour officielles sont disponibles sur cette [page](../start/release-notes.md).

## Version 8.5.1 {#release-8-5}

_30 juin 2023_

**Nouveautés**

<table> 
<thead>
<tr> 
<th> <strong>Service de notifications push amélioré</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign 8.5.1 présente son dernier service de notifications push sur v8, optimisé par un framework robuste reposant sur une technologie de pointe. Ce service est conçu pour atteindre des niveaux d’évolutivité supérieurs, afin que vos notifications puissent atteindre une audience plus large avec une efficacité optimale. Grâce à notre infrastructure améliorée et à nos processus optimisés, vous bénéficierez d’une plus grande échelle et d’une meilleure fiabilité. Vous pourrez ainsi communiquer avec vos utilisateurs et utilisatrices d’applications mobiles comme jamais auparavant. Cette fonctionnalité est réservée à un groupe de clients et clientes restreint (disponibilité limitée).</p>
</td> 
</tr> 
</tbody> 
</table>

**Mises à jour de compatibilité**

* La version 32 bits de la console cliente est désormais obsolète. À compter de la version 8.6, la console cliente sera uniquement disponible en 64 bits. La mise à niveau vers la version 64 bits de la console cliente est transparente. Pour plus d’informations sur la mise à niveau de votre système d’exploitation, reportez-vous à cette [note technique](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=fr).
* Vous pouvez désormais connecter votre instance Campaign v8 à la base de données externe Azure Synapse. Cette connexion est gérée à l&#39;aide d&#39;un nouveau compte externe.

**Améliorations**

* Le débit des SMS a été considérablement amélioré par la mise en œuvre d’une série d’optimisations. Ces modifications ont permis d’optimiser la vitesse et l’efficacité des communications SMS.
* Campaign v8.5.1 et les versions ultérieures ont apporté des améliorations au processus d’authentification de Campaign v8. Les opérateurs ou opératrices techniques doivent utiliser Adobe Identity Management System (IMS) pour se connecter à Campaign.
* Vous pouvez désormais tirer parti des connexions Destination et Source pour synchroniser les attributs de profil tels que les données de désinscription entre Adobe Experience Platform et la base de données Campaign v8.
* La préparation de la diffusion a été optimisée.
* Une nouvelle option d’authentification par clé a été ajoutée pour le compte externe SFTP, outre la méthode d’authentification utilisateur/mot de passe existante. Les utilisateurs et utilisatrices peuvent désormais s’authentifier en toute sécurité à l’aide d’une clé privée, ce qui renforce la sécurité et fournit un autre mécanisme d’authentification pour l’accès SFTP.

**Améliorations de la sécurité**

* Vous ne pouvez plus créer d’opérateurs ou d’opératrices à partir de la console cliente. Vous devez désormais utiliser Admin Console. [En savoir plus](../start/gs-permissions.md).
* Plusieurs outils tiers ont été mis à jour pour optimiser la sécurité.

**Correctifs**

* Correction d’une erreur qui entraînait le codage incorrect des caractères spéciaux dans le contenu HTML d’une diffusion dans plusieurs navigateurs. (NEO-60081)
* Correction d’un problème qui empêchait l’enregistrement d’un rapport sur un déploiement Campaign v8 Enterprise (FFDA). (NEO-56836)
* Correction d’un problème lors de l’insertion ou de la mise à jour de données dans un schéma FFDA personnalisé via une activité de workflow Mise à jour de données. (NEO-54708)
* Correction d’une erreur qui empêchait le workflow de nettoyage de la base de données de supprimer des adresses dans la table nms:address sur FFDA. (NEO-54460)
* Correction d’un problème en raison duquel le workflow de facturation pouvait échouer avec un message d’erreur « Mémoire de compilation épuisée ». (NEO-51137)
* Correction d’un problème qui empêchait le bon fonctionnement du déchiffrement GPG dans l’activité de workflow Chargement de données (fichier). (NEO-50257)
* Correction d’un problème qui empêchait le bon fonctionnement de la fonction `JSPContext.sqlExecWithOneParam`. (NEO-50066)
* Correction d’un problème qui entraînait des échecs de diffusion lors de l’utilisation de caractères non imprimables dans des champs de personnalisation. (NEO-48588)
* Correction d’un problème qui entraînait des erreurs de diffusion lors de l’insertion d’images dynamiques Adobe Target. (NEO-62689)
* Correction d’un problème qui empêchait les navigateurs d’ajouter des espaces supplémentaires lors de l’utilisation de contenu conditionnel dans une diffusion. (NEO-62132)
* Correction d’un problème en raison duquel une fenêtre contextuelle s’ouvrait lors d’un clic sur une image dans l’éditeur de contenu d’e-mail. (NEO-60752)
* Correction d’un problème qui entraînait une erreur et empêchait le défilement lors de l’édition du contenu d’une diffusion. (NEO-61364)
