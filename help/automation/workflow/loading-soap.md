---
product: campaign
title: Chargement (SOAP)
description: Chargement (SOAP)
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 21c42a36-9a50-49b8-8a07-b041ba8b2026
TQID: 'https://experienceleague.adobe.com/CBO5ddwOwsFclqdXq-ahz6ZMg0fXVc4L8vIruKz17j4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 82%
---
# Chargement (SOAP){#loading-soap}



>[!CAUTION]
>
>L’activité **Chargement (SOAP)** nécessite l’installation du module **FDA (Federated Data Access)**. Veuillez vérifier votre contrat de licence.

L&#39;activité de **Chargement (SOAP)** est notamment utilisée en complément de l&#39;activité de **chargement (SGBD)** pour les cas où la collecte de données directement via le FDA dans une base externe n&#39;est pas possible.

Le principe de fonctionnement est le suivant :

1. Choisissez entre l&#39;utilisation d&#39;un XML d&#39;exemple ou d&#39;une WSDL.

   L&#39;exemple suivant est issu d&#39;un workflow technique du module Message Center.

   ![Activité Chargement (SOAP) avec Utiliser un exemple XML sélectionné, un exemple de résultat et le script d&#39;initialisation.](assets/load_soap_002.png)

1. Pour obtenir un exemple XML, sélectionnez un fichier d’exemple. Le fichier est analysé afin d’établir un exemple de résultat.

   Pour un fichier WSDL, saisissez l’URL d’accès correspondante, puis générez le squelette du code. Le service et l’appel sélectionnés sont automatiquement mis à jour et affichés.

   ![Format du résultat avec Utiliser un WSDL sélectionné, un champ URL d&#39;accès et le lien Générer le squelette du code.](assets/soap_load_003.png)

1. Sélectionnez **[!UICONTROL Cliquez ici pour visualiser et modifier le résultat de l&#39;analyse]** afin de définir chaque colonne identifiée.

   ![Fenêtre Format de fichier répertoriant les colonnes identifiées, avec le libellé, le type de données et le nom interne de la colonne sélectionnée.](assets/soap_load_001.png)

   Si vous souhaitez mettre à jour l&#39;exemple, sélectionnez **[!UICONTROL Ré-analyser l&#39;exemple]**.

1. Si vous le souhaitez, vous pouvez choisir d&#39;utiliser le numéro de ligne comme identifiant et/ou indiquer que l&#39;appel SOAP renvoie plusieurs éléments.
1. Saisissez les scripts des onglets suivants selon leur fonction :

   * **[!UICONTROL Initialisation]** : établissement de la connexion SOAP.
   * **[!UICONTROL Itération]** : effectue l’appel au service SOAP. Le retour de cette fonction doit être un objet XML compatible avec la description de l’exemple ou la WSDL.

     Le code de cet onglet sera appelé en boucle par Adobe Campaign jusqu&#39;à ce qu&#39;un objet XML null soit retourné.

   * **[!UICONTROL Finalisation]** : fermeture de la connexion et/ou libération des autres ressources créées lors du traitement.
