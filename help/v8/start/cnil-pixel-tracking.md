---
title: Pixels de tracking e-mail et conseils de la CNIL
description: Présentation des conseils mis à jour de la CNIL sur les pixels de tracking e-mail et les fonctionnalités d’Adobe Campaign pouvant prendre en charge les efforts de conformité.
feature: Overview
role: User
level: Beginner
hide: true
source-git-commit: 5c27d45ebac8ad300d35ef0ff858fbdaef6ec9fb
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 2%

---

# Comprendre les nouveaux conseils de la CNIL sur les pixels de tracking email

Cette publication est fournie à titre d&#39;information uniquement. Il ne s&#39;agit pas d&#39;un avis juridique et ne garantit pas votre conformité avec la loi applicable. Les fonctionnalités du produit Adobe Campaign décrites ci-dessous sont des blocs de création qui, configurés et utilisés de manière appropriée, peuvent prendre en charge une mise en œuvre conforme. Chaque client est responsable de déterminer et de respecter ses obligations en vertu de la loi applicable.

## Présentation

Le 14 avril 2026, la Commission nationale de l&#39;informatique et des libertés (CNIL), l&#39;autorité française de protection des données, a publié une [recommandation sur l&#39;utilisation des pixels de tracking dans les emails](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). Ces conseils clarifient le moment où le consentement est requis et soulignent l’importance de bonnes pratiques de consentement pour le suivi des pixels d’e-mail. Cette politique peut avoir un impact sur les pratiques d’envoi pour toute entité diffusant des e-mails aux abonnés basés en France.

La CNIL a prévu un délai de trois mois à compter de la date de la recommandation pour que les entreprises informent leurs destinataires d&#39;emails (« utilisateurs ») de la présence des pixels de tracking, de leur finalité et du droit de désinscription des utilisateurs. Pendant cette période de transition, les clients doivent informer les utilisateurs du suivi des pixels et fournir un droit d’opposition si nécessaire. La CNIL devrait commencer ses activités d&#39;application après le 14 juillet 2026.

Alors que la CNIL et d&#39;autres organismes de réglementation clarifient les conseils sur le tracking des pixels et les problèmes associés, Adobe continuera à surveiller les mises à jour et à informer les clients des fonctionnalités techniques des produits Adobe qui prennent en charge le marketing par e-mail, y compris Adobe Campaign.

Les applications d’exécution du marketing par e-mail d’Adobe, notamment Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign et Marketo Engage, fournissent des contrôles qui peuvent aider les clients à gérer le suivi des ouvertures au niveau de la diffusion ou de l’e-mail. Il incombe aux clients de déterminer leurs propres obligations de conformité en vertu des conseils de la CNIL et d’autres lois applicables, mais ces fonctionnalités peuvent soutenir les efforts de conformité des clients.

## Qu’est-ce qu’un pixel de tracking e-mail ?

Un pixel de tracking d’e-mail est une image transparente 1x1 incorporée dans l’HTML d’un e-mail. Lorsque le client de messagerie du destinataire charge cette image, le pixel envoie un ping à un serveur qui enregistre des données telles qu’une date et une heure, un type d’appareil, un client de messagerie et parfois une adresse IP pour un emplacement approximatif. Ce journal est ensuite lié à l’enregistrement d’un destinataire, ce qui permet aux spécialistes marketing de voir si un e-mail est ouvert.

## Service clientèle

Les clients qui demandent de l’aide pour mettre en œuvre les modifications décrites ci-dessus peuvent interagir avec leur écosystème Adobe existant. Pour toute question technique sur les fonctionnalités Adobe référencées, contactez votre responsable du succès client ou votre gestionnaire de compte technique.

## Fonctionnalité d’Adobe Campaign liée au tracking e-mail

Les clients peuvent utiliser les mécanismes natifs de tracking, de schéma et de personnalisation d&#39;Adobe Campaign pour répondre à certains éléments lors de la configuration de l&#39;architecture pour répondre aux conseils de la CNIL :

* **Classification de la diffusion.** Étendez nms:delivery avec un attribut emailType (authentification, délivrabilité seule, transactionnel, marketing, service public, prospection B2B). La classification détermine les pixels autorisés sans consentement.
* **Capture du consentement.** Étendez nms:recipient avec une structure de consentement spécifique portant la version de formulation, l’horodatage, la source de capture et l’expiration. Étendez les formulaires d’inscription et les centres de préférences pour collecter le consentement en pixels séparément de l’accord préalable par e-mail.
* **Émission de pixels.** Définissez une valeur NmsTracking_OpenFormula par objectif en pixels (authentification, délivrabilité, performances, profilage, détection des fraudes). Une règle de typologie de diffusion sélectionne les formules à émettre en fonction du type d’e-mail et du consentement spécifique du destinataire. Les blocs de personnalisation encapsulent la logique afin qu’elle ne réside pas dans les contenus publicitaires individuels.
* **Retrait.** Ajouter un lien Gérer les préférences du dispositif de suivi à chaque pied de page d’e-mail, distinct du lien de désabonnement. Le lien pointe vers une page de destination nms:webApp authentifiée via idTracking ; le destinataire retire son consentement en un clic, sans saisir à nouveau son adresse e-mail. Une étape de filtrage ajoutée au workflow de tracking standard empêche les réouvertures d’e-mails précédemment diffusés d’être exploitées après le retrait.
* **Preuve de consentement.** Capturez chaque événement de consentement dans un journal d’ajout uniquement (un espace de noms d’extension pix:consentLog, par exemple), avec la version de libellé stockée séparément pour la récupérabilité après les modifications de libellé. Affichez le journal via l’explorateur Adobe Campaign et en tant qu’exportation périodique.
* **Gouvernance de la re-sollicitation.** Un champ lastPixelRefusalDate et une règle de typologie de filtrage empêchent la re-sollicitation pendant au moins six mois après un refus. Un workflow périodique peut vous aider à gérer l’expiration du consentement.
* **Reporting.** Les rapports Adobe Campaign existants continuent à fonctionner par rapport aux nouveaux champs (urlCategory, emailType, indicateurs de consentement) sans modifications de code.

Pour plus d’informations sur le tracking e-mail dans les applications de marketing par e-mail Adobe, consultez la documentation ici :

| Produit | Référence de documentation |
|---|---|
| Campaign v8 | [Suivi des messages](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [Prise en main du tracking des messages](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Campaign Standard | [Configuration du canal Email](https://experienceleague.adobe.com/fr/docs/campaign-standard/using/administrating/configuring-channels/configuring-email-channel){target="_blank"} |
| Journey Optimizer | [Documentation sur le tracking des messages](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [Désactiver le suivi d’un lien e-mail](https://experienceleague.adobe.com/fr/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer B2B | [Documentation sur les paramètres d’e-mail](https://experienceleague.adobe.com/fr/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |
