---
title: Statuts de diffusion
description: En savoir plus sur les statuts disponibles sur votre tableau de bord de diffusion
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 71%

---

# Statuts de diffusion {#delivery-statuses}

Une fois qu’une diffusion a été envoyée, le tableau de bord de diffusion affiche un statut qui vous permet de vérifier si l’envoi a réussi. Les statuts possibles sont détaillés dans la section ci-dessous.

![](assets/delivery-status.png)

Pour plus d’informations sur les différents échecs de diffusion que vous pouvez rencontrer et sur la manière de les résoudre, consultez la section [Comprendre les échecs de diffusion](delivery-failures.md).

**Rubriques connexes :**

* [Envoyer et surveiller vos e-mails](send.md)
* [Comprendre les diffusions en échec](delivery-failures.md)
* [Prise en main de la délivrabilité](about-deliverability.md)

## Liste des statuts de diffusion {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> Status<br /> </th> 
   <th> Définition et solution<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Envoyés<br /> </td> 
   <td> La diffusion a été correctement transmise au fournisseur de messagerie (mais le destinataire ne l'a pas nécessairement reçu).<br /> </td> 
  </tr> 
  <tr> 
   <td> Ignoré<br /> </td> 
   <td> La diffusion n’a pas été envoyée au destinataire en raison d’une erreur liée à son adresse. Elle était soit sur liste bloquée, soit mise en quarantaine, soit non fournie, ou il s'agissait d'un doublon.<br /> </td> 
  </tr> 
  <tr> 
   <td> En échec<br /> </td> 
   <td> La diffusion n'a pas pu atteindre le destinataire en raison d'une adresse invalide ou d'une boîte de réception pleine par exemple.La raison peut être également un problème lié aux blocs de personnalisation.Ils peuvent générer des erreurs lorsque les schémas ne correspondent pas au mapping de diffusion. Voir <a href="delivery-failures.md" target="_blank">Comprendre les diffusions en échec</a><br /> </td> 
  </tr>
  <tr> 
   <td> En attente<br /> </td> 
   <td> La diffusion est prête à être envoyée.Elle sera traitée par le serveur de diffusion (MTA). Pour plus d'informations, consultez la section <a href="#pending-status" target="_blank">Statut En attente</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Non applicable<br /> </td> 
   <td> La diffusion a été prise en compte par le serveur (MTA), mais ce dernier ne l'a pas traitée.<br /> </td> 
  </tr>  
  <tr> 
   <td> Diffusion annulée<br /> </td> 
   <td> La diffusion a été annulée par un opérateur.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pris en compte par le fournisseur de services<br /> </td> 
   <td> Pour les diffusions SMS, le fournisseur de services SMS a reçu la diffusion.<br /> Pour les diffusions par e-mail, le message a été relayé avec succès de Campaign vers le MTA (Mail Transfer Agent).</td> 
  </tr> 
  <tr> 
   <td> Reçu sur le mobile<br /> </td> 
   <td> Le destinataire a reçu le SMS sur son appareil mobile.<br /> </td> 
  </tr>
  <tr> 
   <td> Transmis au prestataire<br /> </td> 
   <td> La diffusion a été envoyée au fournisseur de services SMS qui ne l'a pas encore reçue.<br />
   </td> 
  </tr> 
  <tr> 
   <td> Préparé<br /> </td> 
   <td> Statut intermédiaire utilisé uniquement pour les connecteurs externes tels que le canal mobile. Il succède à l'état 'En attente' et c'est le connecteur externe qui déterminera le statut suivant.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Pour découvrir comment optimiser la délivrabilité de vos emails Adobe Campaign, reportez-vous à [cette section](about-deliverability.md). Pour un examen plus approfondi de la délivrabilité, consultez le [Guide des bonnes pratiques relatives à la délivrabilité d’Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr).

## Statut En attente {#pending-status}

Après avoir validé votre diffusion, vous pouvez constater que son statut est **[!UICONTROL En attente]**.Ce statut signifie que le processus d&#39;exécution attend la disponibilité de certaines ressources.

Le statut **[!UICONTROL En attente]** peut d&#39;abord signifier que votre diffusion a été planifiée et qu&#39;elle est en attente jusqu&#39;à la date spécifiée. Pour plus d&#39;informations, consultez la section [Planifier l&#39;envoi des diffusions](configure-and-send.md#schedule-delivery-sending) .

Si votre diffusion n&#39;est pas envoyée et reste dans un état **[!UICONTROL En attente]**, la raison peut en être la suivante :

* **Trop de campagnes exécutées simultanément**

  La limite des campagnes simultanées est définie dans l’option **[!UICONTROL NmsOperation_LimitConcurrency]**. La valeur par défaut est 10.

  En tant qu&#39;utilisateur Managed Cloud Services, vous pouvez travailler avec Adobe pour ajuster cette limite si nécessaire. En savoir plus sur les options dans la documentation de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html){target="_blank"}.

* **Problèmes de disponibilité des ressources**

  Le MTA (Message Transfer Agent) peut attendre que les ressources soient disponibles avant de traiter votre diffusion.

>[!NOTE]
>
>En tant qu&#39;utilisateur de Campaign v8 Managed Cloud Services, l&#39;infrastructure MTA est surveillée et gérée par Adobe. Si vous rencontrez des problèmes persistants avec des diffusions en attente, contactez l’Assistance clientèle d’Adobe.

**Rubriques connexes :**

* [Envoyer et surveiller vos e-mails](send.md#email-monitoring)
* [Comprendre les diffusions en échec](delivery-failures.md)
* [Surveillance de votre environnement Campaign](../start/monitor.md#monitor-deliveries)

