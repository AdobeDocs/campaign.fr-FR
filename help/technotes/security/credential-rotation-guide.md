---
product: campaign
title: Note technique - Guide de rotation des informations d’identification
description: Note technique Adobe Campaign - Guide de rotation des informations d’identification
hide: true
hidefromtoc: true
exl-id: 0848ee2d-3506-4167-9aea-a1589aa82805
source-git-commit: 14e49a0b4de1b82239113bd670213449f464c27f
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 93%

---

# Note technique : guide de rotation des informations d’identification {#ac-customer-credentials}

En tant que client ou cliente, vous devez périodiquement remplacer vos informations d’identification par un nouvel ensemble, afin d’atténuer le risque de compromission.

## Informations d’identification des options Adobe Campaign {#ac-options-credentials}

Depuis l’explorateur Adobe Campaign, le nœud **Administration > Plateforme > Options** vous permet d’apporter des modifications aux options Adobe Campaign. Si vous avez stocké des informations d’identification ici, veillez à procéder à leur rotation.

![](assets/technote-2.png)

## Informations d’identification du compte externe {#ac-accounts-credentials}

Le nœud **Administration > Plateforme > Comptes externes** vous permet d’apporter des modifications aux comptes externes Adobe Campaign.

Effectuez une rotation de toutes vos informations d’identification enregistrées dans les comptes externes.

>[!CAUTION]
>
>**Ne modifiez pas** les informations d’identification gérées par Adobe. Les comptes externes ayant un serveur lié à `adobe` ne doivent pas être modifiés.

![](assets/technote-1.png)

Pour les opérateurs techniques `mc*` (par exemple, mc1, mc2, etc.) et `Interaction*` (par exemple, interaction1, interaction2, etc.) spécifiques, l’une des deux approches ci-dessous peut être suivie :

1. Adobe peut modifier les informations d’identification de ces opérateurs et les partager avec vous. Notez que toutes les intégrations utilisant ces opérateurs cesseront de fonctionner jusqu’à ce que les informations d’identification de ces opérateurs soient mises à jour de votre côté.

1. Adobe peut créer de **nouveaux** opérateurs correspondant à chaque opérateur existant et les partager avec vous. Adobe supprimera toutes les occurrences des anciens opérateurs une fois que vous aurez choisi les nouveaux.


## Clé privée/certificat Mobile Services  {#ac-key-credentials}

Pour la rotation des clés privées et du certificat associés à Mobile Services, reportez-vous aux liens ci-dessous.

* Pour Android, consultez [cette documentation](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android){target="_blank"}.
Accédez à la section **Créer l’application mobile Android > Configurer la version d’API**.

* Pour iOS, consultez [cette documentation](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application){target="_blank"}.
Accédez à la section **Créer une application mobile iOS > Mode d’authentification**.

## Clés GPG {#ac-gpg-credentials}

Pour la rotation des clés GPG, les étapes suivantes doivent être suivies :

1. Déchiffrez les données existantes à l’aide de la clé existante. [En savoir plus](https://experienceleague.adobe.com/fr/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Créez une paire de clés GPG. En savoir plus sur la gestion des clés GPG dans [cette documentation](https://experienceleague.adobe.com/fr/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Remplacez l’utilisation de clés GPG existante dans tous les workflows par la clé nouvellement créée.

1. Supprimez la clé GPG existante.
