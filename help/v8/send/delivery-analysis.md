---
title: Analyse des diffusions
description: Découvrez comment préparer et vérifier votre diffusion
feature: Personalization
role: User
level: Beginner
source-git-commit: 8f04981e38da79e69afc890311c559f9ffa136f4
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 53%

---

# Analyse des diffusions {#analyze-delivery}

L’analyse est l’étape de préparation de la diffusion. Il peut être démarré une fois que votre audience cible est définie et que le contenu du message est prêt et testé. Lors de l&#39;analyse de la diffusion, la population cible est calculée et le contenu de la diffusion est préparé. Une fois la diffusion terminée, elle est prête à être envoyée.

## Lancer l&#39;analyse {#start-the-analysis}

Pour préparer la diffusion, vérifiez que le contenu et la cible de la diffusion ont été définis et procédez comme suit :

1. Dans les fenêtres de diffusion, cliquez sur le bouton **[!UICONTROL Envoyer]** bouton .
1. Sélectionner **[!UICONTROL Diffuser dès que possible]** pour effectuer le calcul de l’audience et la préparation du contenu pour un envoi immédiat. Vous pouvez également reporter la diffusion à une date ultérieure ou obtenir une estimation de la population sans préparer le contenu.

   ![](assets/delivery-analysis-start.png)

1. Cliquez sur **[!UICONTROL Analyser]** pour lancer l’analyse manuellement. La barre de progression indique la progression de l’analyse.

   Un ensemble de règles de vérification est appliqué lors de l&#39;analyse de la diffusion. Ces règles sont définies dans une **typologie**, qui est sélectionné dans la variable **[!UICONTROL Typologie]** dans les propriétés de la diffusion. En savoir plus sur les typologies dans [cette section](../../automation/campaign-opt/campaign-typologies.md).

   Par défaut, pour les emails, l&#39;analyse porte sur les points suivants :

   * validation de l&#39;objet,
   * validation des URL et des images,
   * validation des libellés des URL,
   * validation du lien de désinscription,
   * vérification de la taille des BAT,
   * vérification de la durée de validité,
   * vérification de la planification des vagues.


1. Vous pouvez arrêter l’analyse à tout moment en cliquant sur le bouton **[!UICONTROL Arrêter]** bouton .

   Aucun message n’est envoyé pendant la phase de préparation. Vous pouvez donc démarrer ou annuler l’analyse sans risque.

   >[!IMPORTANT]
   >
   >Lors de l’exécution, l’analyse gèle la diffusion (ou le BAT). Toute modification apportée à la diffusion (ou au BAT) doit être suivie d’une autre analyse pour devenir applicable.

Une fois l’analyse terminée, la section supérieure de la fenêtre indique si la préparation de la diffusion est terminée ou si des erreurs se sont produites. Toutes les étapes de validation, les avertissements et les erreurs sont répertoriés. Les icônes colorées indiquent le type de message :

* Une icône bleue indique un message informatif.
* Une icône jaune indique une erreur de traitement non critique.
* Une icône rouge indique une erreur critique qui empêche l&#39;envoi de la diffusion.

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. Cliquez sur **[!UICONTROL Fermer]** pour corriger les erreurs, le cas échéant. Après avoir effectué les modifications, redémarrez l’analyse en cliquant sur **[!UICONTROL Analyser]**.

   >[!NOTE]
   >
   >Cliquez sur le bouton **[!UICONTROL Modifier la cible principale de la diffusion]** lien si le nombre de messages à envoyer ne correspond pas à vos attentes. Cette option permet de modifier la définition de la population cible et de relancer l&#39;analyse.

1. Après avoir vérifié le résultat de l’analyse, cliquez sur **[!UICONTROL Confirmer l&#39;envoi]** pour envoyer le message à la cible principale.


## Paramètres d’analyse {#analysis-settings}

Accédez au **[!UICONTROL Analyse]** onglet des propriétés de la diffusion pour définir les paramètres de préparation du message lors de la phase d’analyse.

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

Cet onglet permet d&#39;accéder aux options suivantes :

* **[!UICONTROL Libellé et code diffusion]** : les options de cette section sont utilisées pour calculer les valeurs de ces champs pendant la phase d’analyse de diffusion. Le champ **[!UICONTROL Calculer le dossier d’exécution lors de l’analyse de la diffusion]** calcule le nom du dossier qui contiendra cette action de diffusion pendant la phase d’analyse.

* **[!UICONTROL Mode de validation]** : ce champ permet de définir une diffusion manuelle ou automatique, une fois l’analyse terminée.

   Si des avertissements sont générés lors de l&#39;analyse (par exemple, si certains caractères sont accentués dans l&#39;objet de la diffusion, etc.), vous pouvez paramétrer la diffusion pour définir si elle doit encore être exécutée ou non. Par défaut, l’utilisateur ou l’utilisatrice doit confirmer l’envoi des messages à la fin de la phase d’analyse : il s’agit d’une validation **manuelle**.

   Vous pouvez choisir un autre mode de validation dans la liste déroulante du champ correspondant.

   Les modes de validation possibles sont les suivants :

   * **[!UICONTROL Manuel]** : à la fin de la phase d’analyse, l’utilisateur doit confirmer la diffusion pour commencer l’envoi. Pour cela, cliquez sur le bouton **[!UICONTROL Démarrer]** afin de lancer la diffusion.
   * **[!UICONTROL Semi-automatique]** : les envois démarrent automatiquement si la phase d’analyse ne génère aucun message d’avertissement.
   * **[!UICONTROL Automatique]** : les envois démarrent automatiquement à la fin de la phase d’analyse, quel qu’en soit le résultat.

* **[!UICONTROL Lancer le traitement dans un processus détaché]** : cette option permet de lancer l’analyse de la diffusion dans un processus à part. Par défaut, la fonction d’analyse utilise le processus du serveur applicatif d’Adobe Campaign (nlserver web). En cochant cette option, vous êtes assuré que l’analyse sera menée à son terme, même en cas de défaillance du serveur applicatif.
* **[!UICONTROL Enregistrer les requêtes de ciblage et de personnalisation dans le journal]** : cette option permet d&#39;ajouter les logs des requêtes SQL dans le journal de la diffusion lors de la phase d&#39;analyse.
* **[!UICONTROL Ignorer les scripts de personnalisation lors de l’envoi]** : cette option permet de ne pas interpréter les directives JavaScript présentes dans le contenu du HTML. Ils s’affichent tels quels dans le contenu diffusé. Ces directives sont introduites avec la méthode `<%=` balise .


