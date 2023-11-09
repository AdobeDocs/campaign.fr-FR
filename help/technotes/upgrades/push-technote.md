---
product: campaign
title: Modifications à venir du canal de notification push
description: Modifications à venir du canal de notification push
hide: true
hidefromtoc: true
source-git-commit: 70d1e7336cce7660890b13def5efcb614c0dc12e
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 6%

---

# Modifications à venir du canal de notification push {#push-upgrade}

Le service Firebase Cloud Messaging (FCM) a fait l’objet de modifications importantes qui peuvent avoir un impact sur votre implémentation de Adobe Campaign Classic.

Dans le cadre des efforts continus de Google pour améliorer ses services, les API FCM héritées seront abandonnées en juin 2024 ([Protocole HTTP Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/http-server-ref))

Ces API sont actuellement intégrées à Adobe Campaign Classic pour envoyer des messages de notification push. Nous comprenons que bon nombre de nos clients, comme vous, dépendent de ces services pour vos campagnes marketing et vos besoins de communication, en particulier pour les appareils Android.

## Cela vous concerne-t-il ?

* **Utilisateurs de l’API HTTP (hérités)**: si l’une de vos campagnes de notification push active utilise l’API HTTP (héritée), votre configuration sera directement affectée par cette modification. Nous vous encourageons vivement à revoir vos configurations actuelles et à vous préparer à la migration vers les API plus récentes.

* **Bonnes nouvelles pour les utilisateurs de l’API HTTP v1**: si votre configuration utilise exclusivement l’API HTTP v1 pour les notifications push Android, vous êtes déjà en conformité et aucune autre action ne sera requise de votre part.

## Que Faisons-Nous ?

* **Plan de transition**: notre équipe travaille activement à l’élaboration d’un plan de transition complet. Cela vous permettra, si nécessaire, de mettre à jour votre mise en oeuvre vers les API FCM les plus récentes déjà disponibles dans les versions récentes d’Adobe Campaign et avec un minimum de perturbations dans vos campagnes.

* **Instructions détaillées**: nous vous fournirons un guide détaillé et d’autres ressources pour faciliter le processus de transition.

* **Assistance**: notre équipe d’assistance clientèle sera à votre disposition pour vous aider tout au long de cette transition. Nous pouvons également accueillir des webinaires et des sessions d&#39;activation pour couvrir les aspects techniques et les bonnes pratiques de la transition.

## Qu&#39;attendons-nous de vous ?

* **Rester informé**: gardez un oeil sur votre boîte de réception pour toute communication supplémentaire de notre part, y compris le plan de transition détaillé.

* **Vérification de la configuration actuelle**: prenez le temps de passer en revue votre configuration et personnalisation actuelles dans Adobe Campaign Classic afin que vous soyez prêt à apporter les modifications nécessaires si nécessaire.

* **Nous contacter**: Si vous avez des questions ou des préoccupations immédiates, n’hésitez pas à contacter notre équipe d’assistance.

## Étapes dʼimplémentation

Au cours des prochaines semaines, nous partagerons plus de détails sur le plan de transition pour les API FCM héritées, y compris les calendriers et les éléments d’action. Soyez assuré, notre principal objectif est de rendre cette transition aussi transparente que possible pour vous et votre équipe.

Nous vous remercions de votre compréhension et de votre compréhension de ces changements. Votre succès est notre priorité, et nous nous engageons à vous soutenir à chaque étape.

Vous pouvez donc anticiper la modification. Voici les étapes générales nécessaires pour migrer la configuration push de HTTP (hérité) vers l’API FCM HTTPv1.

### Mise à niveau de build

* Campaign Classic : la prise en charge de HTTPv1 a été ajoutée dans la version 20.3.1. Si vous utilisez une version précédente, vous devez d’abord effectuer la mise à niveau vers le dernier build du Campaign Classic.

* Campaign v8 : HTTPv1 est pris en charge par toutes les versions de Campaign v8. Aucune mise à niveau n’est nécessaire.

### Serveur marketing

Les modifications de configuration peuvent être effectuées par le client/partenaire.

1. Tout d’abord, vous devez extraire votre fichier JSON. Le fichier JSON du compte du SDK Firebase Admin est nécessaire pour que l’application mobile soit déplacée vers HTTPv1. Voir cette [page](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. Accédez à votre liste de **Services et abonnements**.

1. Localisez toutes les applications mobiles à l’aide de la version d’API HTTP (héritée).

1. Pour chacune de ces applications mobiles, définissez **Version de l’API** vers HTTPv1 et suivez les instructions de configuration présentées dans la section [documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=fr).

>[!NOTE]
>
>Le passage à l’API HTTPv1 sera pris en compte pour les nouvelles diffusions. Les diffusions en reprise, en cours et en cours d’utilisation continueront à utiliser l’API HTTP (héritée).

### Serveur de mid-sourcing

Aucune modification n’est requise.

### Serveur d’exécution en temps réel

Pour cela, vous devez contacter l’assistance d’Adobe Campaign. La procédure de migration est la même que pour le serveur marketing.

### Système d’exploitation Android et application mobile Android

Aucune modification spécifique n’est requise du code des applications mobiles Android et le comportement de notification ne doit pas changer.

Cependant, HTTPv1 introduit trois nouveaux éléments de payload :

| Nom | Valeur par défaut |
|---|---|
| collant | False |
| priority | Par défaut |
| visibility | False |
| collant | Privée |
