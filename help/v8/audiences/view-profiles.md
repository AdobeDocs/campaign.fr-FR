---
title: Affichage des profils existants dans Campaign
description: Découvrez comment accéder aux données de contact dans Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: c316da3c431e42860c46b5a23c73a7c129abf3ac
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 28%

---

# Affichage des profils existants{#view-profiles}

Accédez à **[!UICONTROL Profils et cibles]** pour accéder aux destinataires stockés dans la base de données Adobe Campaign.

À partir de cette page, vous pouvez [créer un nouveau destinataire](create-profiles.md), éditez un destinataire existant et accédez aux détails de son profil.

![](assets/profiles-and-targets.png)

Pour des manipulations de profils plus avancées, accédez à l&#39;arborescence de Campaign à partir de la page **[!UICONTROL Explorateur]** lien sur la page d’accueil d’Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>L’écran de destinataire intégré est défini par le biais d’un schéma XML et de son formulaire associé. Le schéma XML est stocké dans la variable **[!UICONTROL Administration > Paramétrage > Schémas de données]** noeud de l’arborescence de l’explorateur Adobe Campaign. Seuls les utilisateurs experts peuvent apporter des modifications à ces schémas.

## Modification d’un profil{#edit-a-profiles}

Sélectionnez un profil pour afficher les détails dans un nouvel onglet.

![](assets/edit-a-profile.png)

Les données relatives à un profil sont regroupées dans des onglets. Ces onglets et leur contenu dépendent de vos paramètres spécifiques et des packages installés.

Pour un destinataire standard, vous pouvez accéder aux onglets suivants :

* **[!UICONTROL Général]**, pour toutes les données de profil générales. Il contient notamment le nom, le prénom, l&#39;adresse email, le format des emails, etc.

   Cet onglet stocke également la variable **opt-out** Indicateur pour le profil : lorsque la variable **[!UICONTROL Ne plus contacter (tous canaux)]** est sélectionnée, le profil est en liste bloquée. Ces informations sont ajoutées aux données de contact si le destinataire a cliqué sur un lien de désinscription dans une newsletter par exemple. Ce destinataire ne sera plus ciblé sur aucun canal (email, courrier, etc.). Pour en savoir plus, reportez-vous à [cette page](../send/quarantines.md).

* **Coordonnées**, qui contient l’adresse postale du profil sélectionné.

   Vous pouvez vérifier dans cet écran l&#39;index de qualité de l&#39;adresse et le nombre d&#39;erreurs que contient l&#39;adresse. Ces informations sont directement utilisées par le prestataire de services postaux, en fonction du nombre d&#39;erreurs rencontrées lors des diffusions précédentes, et ne peuvent pas être modifiées manuellement.

* **Autre**, pour des champs spécifiques qui peuvent être personnalisés et renseignés selon vos besoins.

   Utilisez la variable **[!UICONTROL Propriétés du champ...]** menu contextuel permettant de modifier les noms des champs et de définir leur format.

   ![](assets/other-tab-field-properties.png)

   Saisissez les nouveaux paramètres comme ci-dessous :

   ![](assets/change-field-properties.png)

   Vérifiez la mise à jour dans l’interface utilisateur :

   ![](assets/other-tab-updated.png)


   >[!CAUTION]
   >Les modifications s&#39;appliquent à tous les destinataires.


* **Abonnements**, pour tous les abonnements principaux aux services. Utilisez la variable **Histoire** pour accéder aux détails des abonnements et des désabonnements de ce contact.

   ![](assets/subscription-tab.png)

   En savoir plus sur les abonnements [dans cette section](../start/subscriptions.md).

* **Diffusions**, pour tous les logs de diffusion du profil sélectionné. Utilisez cet onglet pour accéder à l&#39;historique marketing du contact : libellés, dates et état de toutes les actions de diffusion adressées au profil via tous les canaux.


* **Tracking**, pour tous les logs de tracking du profil sélectionné. Ces informations sont utilisées pour effectuer le suivi du comportement des profils suite aux diffusions. Cet onglet présente le cumul de toutes les URL trackées dans les diffusions. La liste est paramétrable et contient typiquement : l&#39;URL cliquée, la date et l&#39;heure du clic, le document dans lequel l&#39;URL figurait

   En savoir plus sur le suivi [dans cette section](../start/tracking.md).


## Profils actifs {#active-profiles}

Les profils actifs sont les profils qui sont comptabilisés à des fins de facturation.

La facturation ne concerne que les profils **actifs**. Un profil est considéré comme actif s’il a été ciblé ou s’il a reçu des communications au cours des 12 derniers mois via n’importe quel canal.

Un profil qui a été ciblé par plusieurs diffusions n’est comptabilisé qu’une seule fois.

Le nombre de profils actifs est disponible pour les **instances marketing** uniquement. Il n’est pas disponible pour les instances d’exécution, c’est-à-dire les instances MID (mid-sourcing) et RT (Message Center / messagerie en temps réel).

>[!NOTE]
>
>Vous pouvez également surveiller le nombre de profils actifs utilisés sur vos instances directement à partir du Panneau de contrôle de Campaign. Pour plus d’informations, consultez la [documentation du Panneau de contrôle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=fr).
