---
product: campaign
title: Réception d'emails
description: En savoir plus sur l’activité de workflow de réception d’emails
feature: Workflows, Channels Activity
role: User
exl-id: 6cc2c415-1886-4f31-8020-dbaf97a3cc43
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 80%

---

# Réception d&#39;emails{#inbound-emails}



L&#39;activité **Réception d&#39;emails** permet de récupérer et de traiter des emails depuis une messagerie accessible via le protocole POP3.

![](assets/email_rec_edit_1.png)

Le premier onglet de l&#39;activité **Réception d&#39;email** permet de renseigner les paramètres du serveur POP3 et de saisir le script à exécuter à la réception de chaque message. Le deuxième onglet permet d&#39;affecter un planning à l&#39;activité et le troisième onglet définit les conditions d&#39;expiration de l&#39;activité.

1. **[!UICONTROL Réception d&#39;emails]**

   * **[!UICONTROL Utiliser un compte externe]**

     Lorsque cette option est activée, vous pouvez sélectionner un compte POP3 externe au lieu de saisir les paramètres de connexion. Le **[!UICONTROL Compte externe]** Le champ indique le compte POP3 externe à utiliser pour la connexion au service de messagerie. Ce champ n&#39;est visible que si l&#39;option &#39;Utiliser un compte externe&#39; est activée.

     Si cette option n&#39;est pas sélectionnée, vous devez indiquer les paramètres suivants :

     ![](assets/email_rec_edit_1b.png)

      * **[!UICONTROL Serveur POP3]**

        Nom du serveur POP3.

      * **[!UICONTROL Compte POP3]**

        Nom de l&#39;utilisateur.

      * **[!UICONTROL Mot de passe]**

        Mot de passe du compte d’utilisateur.

      * **[!UICONTROL Port]**

        Numéro de port de la connexion POP3. Le port par défaut est 110.

   * **[!UICONTROL Terminer dès qu&#39;un email est traité]**

     Cette option permet de traiter les emails un par un. L&#39;activité n&#39;active sa transition qu&#39;une seule fois puis termine le traitement en laissant les messages non traités sur le serveur.

1. **[!UICONTROL Script]**

   Le script permet de traiter le message et d&#39;effectuer différentes opérations dépendantes du contenu du message. Le script est exécuté pour chaque message et peut décider de l&#39;opération à effectuer sur la messagerie (laisser ou supprimer le message) et de l&#39;activation de la transition sortante.

   Le code retour doit être une des valeurs suivantes :

   * 1 - Supprime le message sur le serveur et active la transition sortante.
   * 2 - Laisse le message sur le serveur et active la transition sortante.
   * 3 - Supprime le message sur le serveur.
   * 4 - Laisse le message sur le serveur.

   Le contenu du message est accessible depuis la variable globale **[!UICONTROL mailMessage]**.

1. **[!UICONTROL Planning]**

   Pour définir un planning pour l&#39;activité, cliquez sur le lien **[!UICONTROL Planification]** tabulation et vérification **[!UICONTROL Planifier l’exécution]**. Cliquez sur le lien **[!UICONTROL Modification]** pour configurer le planning.

   Le paramétrage du planning est le même que celui de l&#39;activité de planification. Pour plus d&#39;informations, consultez la section [Planificateur](scheduler.md).

1. **[!UICONTROL Expiration]**

   Vous pouvez définir des délais d&#39;expiration à partir de l&#39;onglet **[!UICONTROL Expiration]**.

   ![](assets/email_rec_edit_3.png)

   Le paramétrage est le même que celui de l&#39;activité de planification. Pour plus d&#39;informations, consultez la section [Expirations](define-approvals.md).
