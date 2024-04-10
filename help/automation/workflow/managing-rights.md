---
product: campaign
title: Gestion des autorisations relatives aux workflows
description: Découvrez comment gérer les autorisations relatives aux workflows
feature: Workflows, Permissions
role: Admin
exl-id: 3cb8aeec-e758-4b71-adef-67942cf9ded7
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 75%

---

# Gestion des autorisations relatives aux workflows{#managing-rights}



Pour créer, exécuter ou modifier les workflows, les opérateurs Adobe Campaign, lorsqu&#39;ils ne sont pas Administrateurs, doivent avoir les droits correspondants.

D&#39;une manière générale, les opérateurs qui agissent sur les workflows doivent pouvoir accéder aux dossiers contenant les données utilisées dans les différentes activités (destinataires, listes de destinataires, abonnements, diffusions, etc.), et éventuellement à leurs sous-dossiers.

Ils doivent également être associés aux droits nommés correspondants aux actions réalisées par les workflows sur lesquels ils sont amenés à intervenir (import de destinataires, accès aux fichiers, fusion, exécution de scripts SQL, etc.).

La gestion des opérateurs et des autorisations associées est présentée dans [cette section](../../v8/start/gs-permissions.md).

## Les groupes d&#39;opérateurs {#operator-groups-wf}

Les groupes d&#39;opérateurs associés aux workflows sont les suivants :

* Le groupe **[!UICONTROL Exécution des workflows]** permet de contrôler l’exécution et l’approbation des workflows de ciblage : le droit nommé WORKFLOW est associé aux opérateurs et opératrices de ce groupe. Il est requis pour toutes les actions sur les workflows, en plus des droits d’accès aux fichiers de données. Par défaut, le groupe **[!UICONTROL Exécution des workflows]** a un accès en lecture seule aux fichiers de workflow de ciblage standard et aux modèles de workflow. Les opérateurs et opératrices de ce groupe ont également accès en lecture et écriture au fichier d’approbations en attente.
* Le groupe **[!UICONTROL Superviseurs de workflows]** permet aux opérateurs de gérer les validations de workflows.
* Le groupe **[!UICONTROL Chargés d&#39;opération]** pour accéder aux workflows des opérations.

## Droits nommés {#named-rights}

Seul le droit nommé WORKFLOW est spécifique aux workflows : il permet de créer, démarrer et arrêter des workflows. Les droits de lecture sur le fichier de workflow sont requis pour que le droit nommé soit applicable. Pour les workflows de ciblage, la lecture qui se trouve à droite de la **[!UICONTROL Profils et cibles]** Le fichier est nécessaire.

## Compte d&#39;exécution d&#39;un workflow {#workflow-execution-account}

Vous pouvez paramétrer, au niveau du modèle de workflow, le compte d&#39;exécution à utiliser. Le compte d&#39;exécution permet d&#39;associer les permissions directement au workflow, indépendamment de l&#39;opérateur Adobe Campaign qui lancera son exécution. Par défaut, chaque workflow s&#39;exécute avec les droits de l&#39;opérateur qui l&#39;a démarré.

Pour associer un compte d&#39;exécution à un workflow, accédez à la liste des modèles de workflow et cliquez avec le bouton droit sur le modèle associé au workflow. Choisir **[!UICONTROL Action > Modifier le compte d&#39;exécution...]** sélectionnez ensuite le compte à utiliser.
