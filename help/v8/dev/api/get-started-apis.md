---
title: Prise en main des API REST de Campaign
description: Créez des intégrations et construisez votre propre écosystème en interfaçant Campaign avec un ensemble de technologies.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
TQID: https://experienceleague.adobe.com/RRDY-7SFGUwxHk34LLhRHaFN-0U4A9NQfNvLPXO8GM8
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 58%

---

# Prise en main des API REST de Campaign {#get-started-apis}

Les API REST Campaign ont pour but de vous permettre **de créer des intégrations** pour Adobe Campaign et **de créer votre propre écosystème** en interfaçant Adobe Campaign avec l’ensemble des technologies que vous utilisez.

>[!AVAILABILITY]
>
>* Cette fonctionnalité est disponible uniquement à la demande, pour tous les [environnements FDA Campaign](../../architecture/fda-deployment.md). Il n’est **pas** disponible pour les déploiements [ Entreprise (FFDA)](../../architecture/enterprise-deployment.md). Pour y accéder, contactez votre représentant ou représentante Adobe.
>
>* Avant d’effectuer des appels aux API, vérifiez les limites de taille correspondant à votre contrat de licence. Pour en savoir plus à ce sujet, consultez la [Description du produit Adobe Campaign v8](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.


Avec les API REST Adobe Campaign, vous avez accès aux fonctionnalités suivantes :

<table><tr>
 <td valign="top"><a href="retrieving-profiles.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a><p><a href="retrieving-profiles.md">Profils</a></p></td>
<td valign="top"><a href="creating-a-service.md"><img width="60px" alt="conditions" src="assets/icon_services.svg"/></a><p><a href="creating-a-service.md">Services et abonnements</a></p></td>
<td valign="top"><a href="interacting-with-custom-resources.md"><img width="60px" alt="conditions" src="assets/icon_customresources.svg"/></a><p><a href="interacting-with-custom-resources.md">Ressources personnalisées</a></p></td>
<td valign="top"><a href="controlling-a-workflow.md"><img width="60px" alt="conditions" src="assets/icon_workflows.svg"/></a><p><a href="controlling-a-workflow.md">Workflows</a></p></td>
<td valign="top"><a href="managing-transactional-messages.md"><img width="60px" alt="conditions" src="assets/icon_transactionalmessage.svg"/></a><p><a href="managing-transactional-messages.md">Messages transactionnels</a></p></td>
</tr></table>

Pour utiliser les API REST Campaign, vous devez disposer d’un compte Adobe I/O. Il s’agit d’une première étape obligatoire pour découvrir les fonctionnalités des API.
Pour plus d’informations, consultez [cette section](setting-up-api-access.md).

Les API fournies utilisent des **concepts standard** avec une interface REST et des payloads JSON.

Tous les points d’entrée sont décrits en détail dans cette documentation avec les notions générales que vous devez connaître pour manipuler les API, les informations de référence complètes relatives aux API, des exemples de code et des guides de démarrage rapide. Tous les exemples fonctionnent avec Postman, mais n’hésitez pas à utiliser votre client REST préféré.

