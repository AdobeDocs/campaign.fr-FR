---
title: Passage au nouveau connecteur SMS v2
description: Découvrez comment passer au nouveau connecteur SMS v2
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 30ab5a10f17baddfc455dc406a4f31f058ea05ba
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Passage au nouveau connecteur SMS v2

Adobe Campaign v8 introduit un nouveau **connecteur de processus SMS dédié** (v2), qui offre des performances et une fiabilité améliorées par rapport à l’ancien connecteur SMS basé sur MTA.

## Pourquoi passer au connecteur v2

Le processus SMS dédié introduit la prise en charge du mode émetteur-récepteur SMPP, réduisant le nombre de connexions et améliorant l’efficacité des ressources, tout en prenant toujours en charge les configurations émetteur/récepteur si nécessaire. Il offre une stabilité nettement supérieure, avec une récupération plus rapide en cas d’erreur, des connexions persistantes et aucune dépendance aux fichiers locaux ou à la communication entre processus. Les performances sont également améliorées, avec une latence plus faible, un débit plus élevé et un microtraitement intelligent pour équilibrer la vitesse et la fiabilité. En outre, l’isolation du processus SMS simplifie la résolution des problèmes et réduit l’impact cross-canal. Ces améliorations font du connecteur dédié une solution plus robuste et évolutive pour la diffusion de SMS.

## Configuration

Avec Adobe Campaign Managed Cloud Services, la configuration du serveur et la migration du connecteur SMS sont gérées par Adobe. Cette procédure technique nécessite un accès direct aux fichiers de configuration du serveur et aux opérations de base de données.

Si vous devez migrer vers le nouveau connecteur SMS v2, contactez votre représentant Adobe ou l’assistance clientèle Adobe. Ils planifient et exécutent les mises à jour nécessaires pour votre instance.

Pour plus d’informations sur le canal SMS dans Campaign v8, reportez-vous à la [documentation SMS](../../v8/send/sms/sms.md).
