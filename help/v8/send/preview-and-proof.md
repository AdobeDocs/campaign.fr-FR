---
title: Prévisualiser et tester l’e-mail
description: Découvrez comment valider votre diffusion avant l'envoi
feature: Personalization
role: User
level: Beginner
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 10%

---

# Prévisualiser et tester l’e-mail {#preview-test}

Une fois le contenu de votre message défini, vous pouvez utiliser des profils de test pour le prévisualiser et le tester. Si vous avez inséré [contenu personnalisé](personalize.md), vous pouvez vérifier l’affichage de ce contenu dans le message à l’aide des données de profil de test. De plus, pour détecter d&#39;éventuelles erreurs dans le contenu du message ou les paramètres de personnalisation, envoyez des bons à tirer aux profils de test. Un bon à tirer doit être envoyé chaque fois qu’une modification est apportée pour valider le contenu le plus récent.

## Aperçu du contenu{#preview-content}

Avant d&#39;envoyer des BAT, il est recommandé de vérifier le contenu du message dans la section d&#39;aperçu de la fenêtre de diffusion.

Pour prévisualiser le contenu du message, procédez comme suit :

1. Accédez au **Aperçu** de la diffusion.
1. Cliquez sur le bouton **[!UICONTROL Test de la personnalisation]** pour sélectionner un profil afin de renseigner les données de personnalisation. Vous pouvez choisir un destinataire spécifique dans la base, une adresse de contrôle ou sélectionner un profil parmi la population cible, s&#39;il a déjà été défini. Vous pouvez également vérifier le contenu sans personnalisation.

   ![](assets/test-personalization.png)

1. L&#39;aperçu est généré afin que vous puissiez vérifier le rendu du message. Dans l&#39;aperçu du message, les éléments personnalisés sont remplacés par les données de profil de test sélectionnées.

   ![](assets/test-personalization-with-a-recipient.png)

1. Sélectionnez d&#39;autres profils de test pour prévisualiser le rendu des emails pour chaque variante de votre message.

## Envoyer des BAT {#send-proofs}

L&#39;envoi de BAT permet de vérifier le lien de désinscription (opt-out), la page miroir et d&#39;autres liens, de valider le message, de vérifier le bon affichage des images, de détecter les erreurs possibles, etc. Vous souhaiterez peut-être également vérifier votre conception et le rendu sur différents appareils.

Un BAT est un message spécifique qui vous permet de tester un message avant de l’envoyer à l’audience principale. Les destinataires du BAT sont chargés de la validation du message : rendu, contenu, paramètres de personnalisation, configuration.

### Destinataires des BAT {#proofs-recipients}

La cible du BAT peut être définie dans le modèle de diffusion ou spécifique à une diffusion. Dans les deux cas, accédez à l’écran de définition de la cible à partir du **[!UICONTROL À]** et sélectionnez la variable **[!UICONTROL Cible des BAT]** .

![](assets/target-of-proofs.png)

Le type de cible du BAT est sélectionné dans la variable **[!UICONTROL Mode Ciblage]** liste déroulante.

* Utilisez la variable **[!UICONTROL Définition d’une cible spécifique au BAT]** pour sélectionner les destinataires en base comme cible du BAT.
* Utilisez la variable **[!UICONTROL Substitution de l&#39;adresse]** pour saisir les adresses email et utiliser les données du destinataire pour valider le contenu. Les adresses de substitution peuvent être saisies manuellement ou sélectionnées dans la liste déroulante. L&#39;énumération associée est Adresse de substitution (rcpAddress).
Par défaut, la substitution est effectuée de manière aléatoire, mais vous pouvez sélectionner un destinataire spécifique dans la cible principale, via la variable  **[!UICONTROL Détail]** icône .

   ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

   Choisissez la **[!UICONTROL Sélectionner un profil (doit être inclus dans la cible)]** et sélectionnez un destinataire.

   ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* Utilisez la variable **[!UICONTROL Adresses de contrôle]**  option pour utiliser des adresses de contrôle en tant que cible du BAT. Ces adresses peuvent être importées depuis un fichier ou saisies manuellement.

   >[!NOTE]
   >
   >Les adresses de contrôle n&#39;appartiennent pas à la table des destinataires par défaut (nms:recipient), elles sont créées dans une table distincte. Si vous étendez la table des destinataires avec de nouvelles données, vous devez étendre la table des adresses de contrôle avec les mêmes données.

   En savoir plus sur les adresses de contrôle dans [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.htmll){target="_blank"}.

* Utilisez la variable **[!UICONTROL Cible spécifique et Adresses de contrôle]** pour combiner des adresses de contrôle et des adresses email spécifiques. Les paramétrages correspondants sont alors définis dans deux sous-onglets distincts.

### Envoyer un BAT{#proofs-send}

Pour envoyer des BAT de message, procédez comme suit :

1. Dans l’écran de définition du message, cliquez sur le bouton **[!UICONTROL Envoyer un bon à tirer]** bouton .
1. Dans la **[!UICONTROL Envoyer un bon à tirer]** , vérifiez les destinataires du BAT.
1. Cliquez sur **[!UICONTROL Analyser]** pour démarrer la préparation des messages du BAT.

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. Une fois la préparation de la diffusion terminée, utilisez la méthode **[!UICONTROL Confirmer l&#39;envoi]** pour commencer à envoyer des messages de BAT.

Accédez au **[!UICONTROL Audit]** onglet de la diffusion pour vérifier la diffusion des copies de BAT.

Il est recommandé d&#39;envoyer des bons à tirer après chaque modification du contenu du message.

>[!NOTE]
>
>Dans le BAT envoyé, le lien vers la page miroir n&#39;est pas principal. Il n’est actif que dans les messages finaux.

### Propriétés du BAT{#proofs-properties}

Les propriétés de BAT sont définies dans la variable **[!UICONTROL Avancé]** de la fenêtre des propriétés de la diffusion. Accédez au **[!UICONTROL Propriétés du bon à tirer...]** lien pour définir les paramètres et le libellé des BAT. Vous pouvez choisir de conserver :

* Dupliquer les adresses dans le BAT
* Adresses Placées sur la liste bloquée dans le BAT
* Adresses en quarantaine dans le BAT

Par défaut, les messages du BAT sont identifiés par la variable `Proof #N` mention dans l’objet, où `N` est le numéro du BAT. Ce nombre est incrémenté avec chaque analyse de diffusion du BAT. Vous pouvez modifier la variable `proof` , le cas échéant.

![](assets/proof-parameters.png){width="800" align="left"}


## Vidéo pratique {#video-proof}

Découvrez comment envoyer et valider un BAT pour une diffusion e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/333404)
