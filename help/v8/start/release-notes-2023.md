---
title: Notes de mise à jour de Campaign v8 (console) 2023
description: Liste des fonctionnalités et améliorations des versions 2023 de Campaign v8.
feature: Release Notes
role: User
level: Beginner
exl-id: b860c843-155e-4abb-bdd6-b68dc7eaa0ee
source-git-commit: ad198540dc65152680e1d14c45286b94397948fd
workflow-type: ht
source-wordcount: '1476'
ht-degree: 100%

---

# Notes de mise à jour 2023 {#2023-rn}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **versions 2023 de Campaign v8**.


## Version 8.5.2 {#release-8-5-2}

_2 août 2023_

Correction d’un problème de sécurité qui pouvait survenir lors de la mise à niveau vers la version 8.5.1. (NEO-64767)

## Version 8.5.1 {#release-8-5}

_30 juin 2023_


**Service de notifications push amélioré**

Campaign v8.5.1 présente son dernier service de notifications push, optimisé par un framework robuste reposant sur une technologie de pointe. Ce service est conçu pour atteindre des niveaux d’évolutivité supérieurs, afin que vos notifications puissent atteindre une audience plus large avec une efficacité optimale. Grâce à notre infrastructure améliorée et à nos processus optimisés, vous bénéficierez d’une plus grande échelle et d’une meilleure fiabilité. Vous pourrez ainsi communiquer avec vos utilisateurs et utilisatrices d’applications mobiles comme jamais auparavant. Cette fonctionnalité est réservée à un groupe de clients et clientes restreint (disponibilité limitée).

Pour plus d’informations, consultez la [documentation détaillée](../send/push-data-collection.md).


<table style="table-layout:fixed" text-align="bottom"><tr style="border: 0;">
<td>
<br/><img alt="Améliorations du débit" src="../start/assets/do-not-localize/improvements.jpeg">
<p>
</td>
<td>
<div>
<p><strong>Débit accru du canal mobile</strong></p>
<p>Le nouveau service de notification push présente d’importantes améliorations du débit pour Push Android et Push iOS par rapport à notre version précédente (v8.4). Les utilisateurs et utilisatrices bénéficieront de performances considérablement améliorées avec le service mis à niveau dans la dernière version (v8.5). </p>
<ul>
<li>Notifications push (Android) : jusqu’à <strong>5x</strong> plus rapides </li>
<li>Notifications push (iOS) : jusqu’à <strong>2,2x</strong> plus rapides</li>
</ul>
<p>Le débit des SMS a fait l’objet d’améliorations substantielles grâce à une série d’optimisations. Ces modifications ont permis d’optimiser considérablement la vitesse et l’efficacité des communications SMS. Ces mises à niveau se traduisent par une augmentation du débit entre la version précédente (v8.4) et la version la plus récente (v8.5), comprenant à la fois des mises à jour d’envoi et de retour. Les utilisateurs et utilisatrices peuvent désormais bénéficier des avantages de ce service SMS amélioré.</p>
<ul>
<li>Débit des SMS : jusqu’à <strong>5x</strong> plus rapide</li>
</ul>
<p><em>Ces performances de débit maximales ont été mesurées par des équipes de test d’Adobe, dans des conditions de laboratoire.</em></p>
</div>
<p></p>
</td>
</tr></table>


**Améliorations générales**

* Vous pouvez désormais tirer parti de la connexion à la destination Adobe Experience Platform pour synchroniser les attributs de profil tels que les données de désinscription entre Adobe Experience Platform et la base de données Campaign v8.
* La préparation de la diffusion a été optimisée sur tous les canaux.
* Une nouvelle option d’authentification par clé a été ajoutée pour le compte externe SFTP, outre la méthode d’authentification utilisateur/mot de passe existante. Les utilisateurs et utilisatrices peuvent désormais s’authentifier en toute sécurité à l’aide d’une clé privée, ce qui renforce la sécurité et fournit un autre mécanisme d’authentification pour l’accès SFTP. En savoir plus dans [cette section](../config/external-accounts.md).

**Améliorations de la sécurité**

* Avec Campaign v8.5.1, le processus d’authentification de Campaign v8 a été amélioré et sécurisé. Les opérateurs ou opératrices techniques doivent à présent utiliser Adobe Identity Management System (IMS) pour se connecter à Campaign. Découvrez comment migrer votre ou vos comptes techniques existants dans [cette note technique](../../technotes/upgrades/ims-migration.md).
* À compter de la version v8.6, vous n’aurez plus l’autorisation de créer des opérateurs et opératrices à partir de la console cliente Campaign. Si vous utilisez l’authentification native nom d’utilisateur/mot de passe, vous devez migrer vos opérateurs et opératrices vers Adobe Identity Management System (IMS). Découvrez comment effectuer la migration de vos opérateurs et opératrices dans [cette note technique](../../technotes/upgrades/migrate-users-to-ims.md).
* Plusieurs outils tiers ont été mis à jour pour optimiser la sécurité.

**Mises à jour de compatibilité**

* La version 32 bits de la console cliente est désormais obsolète. À compter de la version 8.6, la console cliente sera uniquement disponible en 64 bits. La mise à niveau vers la version 64 bits de la console cliente est transparente. Pour plus d’informations sur la mise à niveau de votre système d’exploitation, reportez-vous à cette [note technique](../../technotes/upgrades/console.md).
* Vous pouvez désormais connecter votre instance Campaign v8 à la base de données externe Azure Synapse. Cette connexion est gérée à l’aide d’un nouveau compte externe. En savoir plus sur la [matrice de compatibilité de Campaign](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda).


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
* Le connecteur Adobe Analytics exporte désormais les mesures avec le type de canal approprié. Auparavant, il était toujours défini sur le canal « e-mail ». (NEO-26340)
* Correction d’un problème qui entraînait des erreurs lors de l’utilisation du connecteur Big Query avec les champs dateTime. (NEO-49768)


## Version 8.4.5 {#release-8-4-5}

_3 avril 2023_

**Correctifs**

* Correction d’un problème qui pouvait entraîner une erreur de contrainte de clé en double si plusieurs workflows d’approbation étaient définis sur le même planning. (NEO-48968)
* Correction d’un problème de régression introduit par NEO-54474 (8.4.4) qui entraînait la modification de l’attribut de style de la balise body lors du chargement d’une image dans Digital Content Editor (DCE). (NEO-57697)
* Correction d’un problème qui pouvait entraîner une erreur lors de l’export de données à l’aide d’un connecteur CRM si la table temporaire avait une clé primaire définie sur long au lieu d’uuid. (NEO-54153)
* Correction d’un problème de régression introduit dans la version 8.4.1 qui pouvait entraîner des erreurs dans l’export de packages, FDA via HTTP et le reporting. (NEO-57731)
* Correction d’un problème de régression introduit dans la version 8.3.8 qui pouvait empêcher la mise à jour correcte du statut de diffusion pour les diffusions avec des identifiants négatifs. (NEO-54675)
* Correction d’un problème lié aux champs booléens lors de l’import de données à l’aide du connecteur BigQuery (NEO-49181).


## Version 8.4.4 {#release-8-4-4}

_8 mars 2023_

**Amélioration de la sécurité**

* Afin d’améliorer la sécurité, Tomcat a été mis à jour de la version 8.5.81 vers la version 8.5.85. (NEO-50530)

**Correctifs**

* Correction d’un problème qui empêchait le défilement dans l’onglet **Modifier** de Digital Content Editor (DCE). (NEO-54474)
* Correction d’un problème qui pouvait entraîner un blocage du serveur web lors de la réplication. (NEO-53670)


## Version 8.4.3 {#release-8-4-3}


_27 janvier 2023_

**Correctifs**

* Correction d’un problème de synchronisation des indicateurs de diffusion entre le serveur marketing et le serveur de midsourcing. (NEO-50724) <!--OKKKK-->
* Correction d’un problème qui entraînait une erreur lors de l’exportation d’un workflow. (NEO-50555) <!--OKKKK-->
* Correction d’un problème lors de l’extension d’un schéma précédemment étendu. (NEO-49118) <!--OKKKK-->
* Correction d’un problème lors de l’utilisation de deux activités d’enrichissement avec le même identifiant dans la définition du lien. (NEO-48851)
* Correction de deux problèmes qui entraînaient l’échec de la préparation de diffusion. La préparation de la diffusion pouvait échouer lorsque le nombre d’offres potentielles manipulées était trop élevé. Le deuxième problème survenait lorsque les URL des images étaient définies comme URL à suivre dans une diffusion au format texte. (NEO-48807) <!--OKKKK-->
* Correction d’un problème qui entraînait l’échec d’un workflow lorsqu’il remplaçait le nom de l’entrepôt de données défini dans le compte externe pour les comptes non FFDA. (NEO-43209) <!--OKKKK-->
* Amélioration de la sécurité des applications web pour empêcher les attaques DDoS. (NEO-50757) <!--OKKKK-->
* La gestion des données de tracking consolidées a été améliorée dans la table FFDA (nms:trackingStats) **[!UICONTROL Tracking consolidé]** afin d’éviter les doublons. (NEO-46409)
* Correction d’un problème d’opérateur logique dans les requêtes de workflow lors de l’utilisation d’une propriété `enableIf` dans une condition d’opérateur logique. La condition logique précédente a été remplacée. (NEO-45815)  <!--OKKKK-->
* La génération des profils actifs a été optimisée dans le workflow de facturation afin d’améliorer les performances. (NEO-47658) <!--OKKKK-->
* Correction d’un problème lié à l’importation de fichiers HTML lorsque les nœuds d’image (img) contenaient des URL avec des champs de personnalisation. (NEO-48396)
* Correction d’un problème avec Snowflake (tous les déploiements) lors de l’utilisation du paramètre de tri dans une activité de workflow **Partage**. (NEO-45899) <!--OKKKK-->
* Correction d’un problème qui entraînait une erreur lorsqu’un utilisateur ou une utilisatrice disposant de droits d’accès en lecture sur le dossier nmsDeliveryMapping essayait de lancer une campagne ou un workflow. (NEO-48230)
* Correction d’un problème de performances dans l’onglet HTML d’une diffusion, qui pouvait se produire lors de l’utilisation d’un code HTML volumineux. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Correction d’un problème qui empêchait l’utilisation de l’option de workflow **Fusionner les lignes sélectionnées**. (NEO-48488)
* Correction d’un problème sur le connecteur Snowflake FDA en raison duquel les enregistrements étaient supprimés lors de l’utilisation de « Jointure simple de cardinalité 0 ou 1 » pendant l’enrichissement. (NEO-48737)
* Les autres références à la bibliothèque log4j ont été supprimées dans l’installation de Campaign sous Windows. (NEO-44851)
* Correction d’un problème qui pouvait entraîner une erreur lors de l’ajout de l’indicateur **Destinataires ayant ouvert** (estimatedRecipientOpen) dans les données additionnelles d’une activité de workflow **Requête**. (NEO-46665)
* La gestion des URL de tracking a été améliorée dans les workflows comportant plusieurs diffusions afin d’améliorer les performances. (NEO-50894) <!--OKKKK-->
* Correction d’un problème qui entraînait l’échec de la réplication des schémas utilisant Xtkfolder. (NEO-46787) <!--OKKKK-->
* Correction d’un problème en raison duquel la colonne personnalisée « lastModified » était déposée dans la table NmsSubscription. (NEO-48402)
