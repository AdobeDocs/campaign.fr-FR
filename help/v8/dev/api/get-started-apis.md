---
title: Prise en main des API REST de Campaign
description: Créez des intégrations et construisez votre propre écosystème en interfaçant Campaign avec un ensemble de technologies.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: 1d9d4111cde1e230220a04c8fd10a126116339ad
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 46%

---

# Prise en main des API REST de Campaign {#get-started-apis}



Les API REST Campaign ont pour but de vous permettre **de créer des intégrations** pour Adobe Campaign et **de créer votre propre écosystème** en interfaçant Adobe Campaign avec l’ensemble des technologies que vous utilisez.

>[!AVAILABILITY]
>
>* Cette fonctionnalité est disponible uniquement à la demande, pour tous les [environnements FDA Campaign](../../architecture/fda-deployment.md). Il n’est **pas** disponible pour les déploiements [ Entreprise (FFDA)](../../architecture/enterprise-deployment.md). Pour y accéder, contactez votre représentant ou représentante Adobe.
>
>* Avant d’effectuer des appels aux API, vérifiez les limites de taille correspondant à votre contrat de licence. Pour plus d&#39;informations, consultez la page [Description du produit Campaign](https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html#RessourcesdinfrastructureinformatiqueparniveauxdeProfilsactifs){target="_blank"}.


Avec les API REST Adobe Campaign, vous avez accès aux fonctionnalités suivantes :

<table><tr>
 <td valign="top"><a href="retrieving-profiles.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a><p><a href="retrieving-profiles.md">Profils</a></p></td>
<td valign="top"><a href="creating-a-service.md"><img width="60px" alt="conditions" src="assets/icon_services.svg"/></a><p><a href="creating-a-service.md">Services et abonnements</a></p></td>
<td valign="top"><a href="interacting-with-custom-resources.md"><img width="60px" alt="conditions" src="assets/icon_customresources.svg"/></a><p><a href="interacting-with-custom-resources.md">Ressources personnalisées</a></p></td>
<td valign="top"><a href="controlling-a-workflow.md"><img width="60px" alt="conditions" src="assets/icon_workflows.svg"/></a><p><a href="controlling-a-workflow.md">Workflows</a></p></td>
<td valign="top"><a href="managing-transactional-messages.md"><img width="60px" alt="conditions" src="assets/icon_transactionalmessage.svg"/></a><p><a href="managing-transactional-messages.md">Messages transactionnels</a></p></td>
</tr></table>

Pour utiliser les API REST Campaign, vous devez disposer d’un compte Adobe I/O. Il s’agit d’une première étape obligatoire pour découvrir les fonctionnalités des API.
Voir à ce propos [cette section](setting-up-api-access.md).

Les API fournies utilisent des **concepts standard** avec une interface REST et des payloads JSON.

Tous les points d’entrée sont décrits en détail dans cette documentation avec les notions générales que vous devez connaître pour manipuler l’API, la référence complète de l’API, des exemples de code et des guides de démarrage rapide. Tous les exemples fonctionnent avec Postman, mais n’hésitez pas à utiliser votre client REST préféré.

S’il manque quelque chose ou si une information semble incorrecte, posez une question à la [communauté](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community?profile.language=fr){target="_blank"}.
