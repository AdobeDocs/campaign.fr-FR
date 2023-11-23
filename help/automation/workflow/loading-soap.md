---
product: campaign
title: Chargement (SOAP)
description: Chargement (SOAP)
feature: Workflows
role: User
exl-id: 21c42a36-9a50-49b8-8a07-b041ba8b2026
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 100%

---

# Chargement (SOAP){#loading-soap}



>[!CAUTION]
>
>L&#39;activité **Chargement (SOAP)** nécessite l&#39;installation du module **FDA (Federated Data Access)**. Vérifiez votre contrat de licence.

L&#39;activité de **Chargement (SOAP)** est notamment utilisée en complément de l&#39;activité de **chargement (SGBD)** pour les cas où la collecte de données directement via le FDA dans une base externe n&#39;est pas possible.

Le principe de fonctionnement est le suivant :

1. Choisissez entre l&#39;utilisation d&#39;un XML d&#39;exemple ou d&#39;une WSDL.

   L&#39;exemple suivant est issu d&#39;un workflow technique du module Message Center.

   ![](assets/load_soap_002.png)

1. Dans le cas d&#39;un XML d&#39;exemple, sélectionnez un fichier d&#39;exemple. Le fichier est analysé afin d&#39;établir un exemple de résultat.

   Dans le cas d&#39;une WSDL, entrez l&#39;URL d&#39;accès correspondante puis générez le squelette du code. Le service et l&#39;appel sélectionnés sont automatiquement mis à jour et s&#39;affichent.

   ![](assets/soap_load_003.png)

1. Sélectionnez **[!UICONTROL Cliquez ici pour visualiser et modifier le résultat de l&#39;analyse]** afin de définir chaque colonne identifiée.

   ![](assets/soap_load_001.png)

   Si vous souhaitez mettre à jour l&#39;exemple, sélectionnez **[!UICONTROL Ré-analyser l&#39;exemple]**.

1. Si vous le souhaitez, vous pouvez choisir d&#39;utiliser le numéro de ligne comme identifiant et/ou indiquer que l&#39;appel SOAP renvoie plusieurs éléments.
1. Saisissez les scripts des onglets suivants selon leur fonction :

   * **[!UICONTROL Initialisation]** : établissement de la connexion SOAP.
   * **[!UICONTROL Itération]** : appel du service SOAP. Le retour de cette fonction doit être un objet XML compatible avec la description de l&#39;exemple ou la WSDL.

     Le code de cet onglet sera appelé en boucle par Adobe Campaign jusqu&#39;à ce qu&#39;un objet XML null soit retourné.

   * **[!UICONTROL Finalisation]** : fermeture de la connexion et/ou libération des autres ressources créées lors du traitement.
