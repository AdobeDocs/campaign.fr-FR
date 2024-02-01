---
title: Envoi de courriers avec Adobe Campaign
description: Prise en main du courrier dans Campaign
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: f04db53bee75c935bc8737eef93fa05ec6868ebc
workflow-type: ht
source-wordcount: '392'
ht-degree: 100%

---

# Création de diffusions courrier

Les diffusions courrier permettent de générer un fichier d&#39;extraction contenant les données relatives à la population cible. Vous pouvez ensuite partager ce fichier avec le fournisseur qui enverra les messages aux populations cibles.

Les étapes de génération du fichier sont les suivantes :

1. Création de la diffusion

   Créez une diffusion courrier à partir du modèle. Vous pouvez dupliquer et configurer le modèle intégré **[!UICONTROL Diffuser par courrier (papier)]**.

   ![](../assets/do-not-localize/book.png)Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html?lang=fr){target="_blank"}.

1. Définition de l’audience

   Les profils des destinataires doivent contenir au minimum leurs noms et adresses postales.

   Les adresses postales sont des champs calculés. Par défaut, une adresse peut contenir jusqu’à six lignes : la première contient le prénom et le nom, les suivantes contiennent les coordonnées postales (rue et compléments), et la dernière contient le code postal et la ville. La définition du champ calculé postalAddress par défaut peut être vérifiée dans le schéma nms:recipient.

   Une adresse est considérée comme complète si les champs relatifs au nom, au code postal et à la ville ne sont pas vides. Les personnes destinataires dont les adresses sont incomplètes seront exclues des diffusions par courrier.

   ![](../assets/do-not-localize/book.png)Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=fr){target="_blank"}.

1. Définition du contenu du fichier

   Utilisez l&#39;assistant d&#39;extraction pour définir les informations (colonnes) à exporter dans le fichier de sortie.

   ![](../assets/do-not-localize/book.png)Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html?lang=fr){target="_blank"}.

1. Validation de la diffusion

   Vérifiez le résultat de l&#39;analyse et le contenu du fichier de sortie.

   ![](../assets/do-not-localize/book.png)Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html?lang=fr){target="_blank"}.

   Dans le cadre d&#39;une opération marketing, à la date d&#39;extraction, le fichier d&#39;extraction est créé. Vous pouvez visualiser le contenu du fichier extrait, le valider ou modifier le format et relancer l&#39;extraction en cas de besoin. Une fois le fichier validé, vous pouvez envoyer l’e-mail de notification au routeur. Apprenez-en davantage en consultant [cette page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=fr).

1. Lancement de la diffusion

   Une fois le fichier d&#39;extraction validé, cliquez sur **Confirmer l&#39;envoi**. Un message de confirmation vous permet de lancer la diffusion.

   La confirmation démarre l&#39;extraction des données dans le fichier spécifié.

   Dans le cadre d’une campagne marketing, lorsque toutes les validations ont été accordées, les fichiers d’extraction sont créés via un workflow spécifique qui, dans une configuration par défaut, démarre automatiquement lorsqu’une diffusion de publipostage direct est en attente d’extraction. En savoir plus dans [cette section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=fr)
