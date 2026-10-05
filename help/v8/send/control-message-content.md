---
product: campaign
title: À propos de la délivrabilité dans Adobe Campaign Classic
description: En savoir plus sur la gestion de la délivrabilité dans Adobe Campaign
feature: Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: dcd3a9f9-5fe9-4c28-a4a5-5aed67b036ab
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 63876777-85c3-57e1-a2da-81f02956c63c
    internal-label: Deliverability
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 97%
---
# Contrôle du contenu de votre message{#control-message-content}

Pour que vos emails atteignent vos destinataires et améliorer ainsi leur taux de délivrabilité, assurez-vous qu’ils respectent un certain nombre de règles. Dans le cas contraire, le contenu de certains messages peut être détecté comme du spam. Adobe Campaign fournit plusieurs outils vous permettant de vérifier que votre contenu respecte ces règles.

Suivez les principes ci-dessous lors de la conception du contenu de votre message :

* [Adresse expéditeur](#sender-address) : l’adresse doit identifier explicitement l’expéditeur. Le domaine doit appartenir à l’expéditeur et être enregistré auprès de lui. Le registre des domaines ne doit pas être privatisé.
* [Personnalisation](#personalization) : la personnalisation du contenu et la définition d’une heure d’envoi par destinataire augmentent les chances d’ouverture de votre message.
* Images et texte : respectez un ratio texte/images correct (par exemple, 60 % de texte et 40 % d’images).
* [Lien de désinscription](#opt-out) et page de destination correspondante : le lien de désinscription est indispensable. Il doit être visible et valide, et le formulaire doit être fonctionnel.
* Prévisualisation : utilisez les outils fournis par Adobe Campaign pour vérifier et optimiser le contenu de votre email ([Inbox Rendering](#message-responsiveness), [ SpamAssassin emails](#spamassassin)).

Pour obtenir des conseils supplémentaires sur l’optimisation de la délivrabilité lors de la conception du contenu, consultez le [Guide des bonnes pratiques relatives à la délivrabilité d’Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=fr){target="_blank"}.

>[!NOTE]
>
>Pour plus d’informations sur la modification du contenu des e-mails, consultez cette [page](defining-the-email-content.md).

## Adresse d’expéditeur {#sender-address}

Certains FAI vérifient la validité de l’adresse d’expédition (**[!UICONTROL De]**) avant d’accepter les messages. Une adresse erronée peut causer un refus de la part du serveur receveur.

Vous devez vous assurer qu’une adresse correcte est bien renseignée au niveau de l’instance (menu **[!UICONTROL Outils > Avancé > Assistant de déploiement…]**) ou dans les scénarios les plus fréquemment utilisés.

Pour plus d&#39;informations sur la définition de l&#39;adresse de l&#39;expéditeur, consultez cette [page](defining-the-email-content.md#sender).

## Personnalisation {#personalization}

Pour améliorer l’expérience de vos destinataires et les inciter à ouvrir votre e-mail, Adobe Campaign vous permet de personnaliser vos messages.

Pour plus d’informations sur l’utilisation des champs de personnalisation dans Adobe Campaign, voir [cette section](personalization-fields.md).

## Lien et formulaire d’opt-out {#opt-out}

Par défaut, une [règle de typologie](../../automation/campaign-opt/apply-rules.md) vérifie au moment de l’analyse du message qu’un lien d’exclusion est bien présent dans le contenu d’une diffusion et génère un avertissement en cas d’absence. Vous pouvez modifier le niveau d’alerte de cette règle afin qu’elle génère une erreur, de façon à ce qu’en aucun cas une diffusion ne puisse être démarrée sans ce lien.

Vous devez vérifier le bon fonctionnement du lien d&#39;opt-out avant chaque envoi. Par exemple, lors de l’envoi du BAT, vérifiez que le lien est valide, que le formulaire est en ligne et que sa validation change bien la valeur de **[!UICONTROL Ne plus contacter cette personne]** à **[!UICONTROL Oui]**. Cette vérification doit être systématique car on ne peut pas exclure une erreur humaine dans la saisie du lien ou dans la modification du formulaire.

Découvrez comment insérer un lien d&#39;opt-out [dans cette section](personalization-blocks.md#ootb-personalization-blocks).

Au cas où un problème empêchant l’exclusion ne serait détecté qu’après le démarrage de la diffusion, il sera toutefois possible d’exclure manuellement (à l’aide d’une mise à jour en masse, par exemple) les destinataires qui ont cliqué sur le lien d’opt-out, même s’ils n’ont pas pu confirmer ce choix.

De manière générale, n’essayez pas de faire obstacle aux personnes destinataires qui souhaitent se désinscrire en leur demandant de remplir des champs tels que leur adresse e-mail ou leur nom, par exemple. Le formulaire ne doit comporter qu’un seul bouton de validation et la réconciliation ne doit porter que sur l’identifiant chiffré.

Demander une confirmation supplémentaire n’est pas fiable, car un utilisateur peut disposer de deux adresses email redirigées vers la même boîte (par exemple : prénom.nom@club.com et prénom.nom@internet-club.com). Si le destinataire est capable de se souvenir uniquement de la première adresse et souhaite s’exclure via un message envoyé à l’autre, le formulaire refusera cette adresse, car l’identifiant chiffré et l’adresse e-mail saisie ne correspondront pas.

## Rendu de la boîte de réception {#message-responsiveness}

Avant d’envoyer votre message, vous pouvez tester sa réactivité en vérifiant son apparence sur différents appareils. Vous vous assurez ainsi que son affichage sera optimal sur divers clients web, webmails et appareils.

Pour permettre cette opération, Adobe Campaign capture le rendu et le rend disponible dans un rapport dédié. Vous pouvez ainsi prévisualiser le message envoyé dans les différents contextes de réception.

Pour plus d&#39;informations, consultez la section [Inbox rendering](inbox-rendering.md).

## SpamAssassin {#spamassassin}

Adobe Campaign peut être configuré pour fonctionner avec SpamAssassin. Cela permet d&#39;attribuer un score aux emails afin de déterminer si un message risque d&#39;être considéré comme indésirable par les outils anti-spams utilisés à sa réception.

Avant qu’une diffusion ne soit lancée, l’onglet **[!UICONTROL Prévisualisation]** vous permet d’évaluer les risques. Un message d’avertissement fournit le résultat du test.

En savoir plus dans cette [section](spamassassin.md).
