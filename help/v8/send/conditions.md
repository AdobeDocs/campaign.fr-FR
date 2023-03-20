---
title: Contenu conditionnel
description: Découvrez comment créer du contenu conditionnel
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 43%

---


# Créer du contenu conditionnel{#conditional-content}

Le paramétrage de champs de contenu conditionnel permet d&#39;atteindre un niveau de personnalisation évolué. Des blocs complets de texte et/ou des images sont remplacés lorsqu&#39;une condition particulière est remplie.


## Utilisation de conditions dans un e-mail {#conditions-in-an-email}

Dans l&#39;exemple ci-dessous, découvrez comment créer un message, personnalisé dynamiquement en fonction de la ville et des centres d&#39;intérêt du destinataire.

* Modifiez le message en fonction de la ville du destinataire,
* Personnalisez le contenu de l&#39;offre en fonction des intérêts du destinataire.

Pour créer un contenu conditionnel en fonction de la valeur d&#39;un champ, respectez les étapes suivantes :

1. Ouvrez une diffusion existante ou créez une diffusion email.
1. Dans l&#39;éditeur de contenu d&#39;email, cliquez sur l&#39;icône de personnalisation et sélectionnez **[!UICONTROL Contenu conditionnel > Si]**.

   ![Insérer une condition](assets/condition-insert.png)

   Les éléments de personnalisation sont insérés dans le corps du message : vous devez maintenant les paramétrer.

1. Renseignez les paramètres du **if** expression.

   * Sélectionnez le premier élément de l&#39;expression, **`<FIELD>`**, puis cliquez sur l’icône de personnalisation pour la remplacer par le champ de test.
   * Remplacez **`<VALUE>`** par la valeur du champ pour lequel la condition sera remplie. Cette valeur doit être entre guillemets.
   * Spécifiez le contenu à insérer lorsque la condition est remplie. Il peut s’agir d’un texte, d’une image, d’un formulaire, d’un lien hypertexte, etc.

   ![Condition dans un email](assets/condition-in-email.png)

1. Cliquez sur le bouton **[!UICONTROL Aperçu]** pour visualiser le contenu du message en fonction du destinataire de la diffusion. Sélectionnez un destinataire pour lequel la condition est vraie pour vérifier le contenu. Sélectionnez ensuite un autre destinataire dont la valeur est false et vérifiez à nouveau.

Vous pouvez ajouter d&#39;autres cas et définir un contenu différent en fonction des valeurs d&#39;un ou plusieurs champs. Utilisez pour cela les options **[!UICONTROL Contenu conditionnel > Sinon]** et **[!UICONTROL Contenu conditionnel > Sinon si]**. Le paramétrage de ces expressions est le même que pour l&#39;expression **if**.

>[!CAUTION]
>
>Le **%> &lt;%** Les caractères doivent être supprimés après l’ajout de **Else** et **Sinon si** conditions.


## Cas pratique : créer un email multilingue {#creating-multilingual-email}

Dans l&#39;exemple ci-dessous, découvrez comment créer un email multilingue. Le contenu s&#39;affiche dans une langue ou une autre selon la préférence linguistique du destinataire.

1. Créez un email et sélectionnez la population cible. Dans cet exemple, la condition d’affichage d’une version ou d’une autre sera basée sur la variable **Langue** valeur du profil du destinataire. Ces valeurs sont définies sur **EN**, **FR**, **ES**.
1. Dans le contenu HTML de l&#39;email, cliquez sur l&#39;onglet **[!UICONTROL Source]** et collez le code suivant :

   ```
   <% if (language == "EN" ) { %>
   <DIV id=en-version>Hello <%= recipient.firstName %>,</DIV>
   <DIV>Discover your new offers!</DIV>
   <DIV><a href="https://www.adobe.com/products/en">www.adobe.com/products/en</A></FONT></DIV><%
    } %>
   <% if (language == "FR" ) { %>
   <DIV id=fr-version>Bonjour <%= recipient.firstName %>,</DIV>
   <DIV>Découvrez nos nouvelles offres !</DIV>
   <DIV><a href="https://www.adobe.com/products/fr">www.adobe.com/products/fr</A></DIV><%
    } %>
    <% if (language == "ES" ) { %>
   <DIV id=es-version><FONT face=Arial>
   <DIV>Olà <%= recipient.firstName %>,</DIV>
   <DIV>Descubra nuestros nuevas ofertas !</DIV>
   <DIV><a href="https://www.adobe.com/products/es">www.adobe.com/products/es</A></DIV>
   <% } %>
   ```

1. Testez le contenu de l&#39;email dans l&#39;onglet **[!UICONTROL Aperçu]** en sélectionnant des destinataires avec des préférences linguistiques différentes.

   >[!NOTE]
   >
   >Comme aucune autre version n&#39;a été définie dans le contenu de l&#39;email, veillez à filtrer la population cible avant d&#39;envoyer l&#39;email.

## Tutoriel vidéo {#conditionnal-content-video}

Découvrez comment ajouter du contenu conditionnel à une diffusion en prenant pour exemple une newsletter multilingue.

>[!VIDEO](https://video.tv.adobe.com/v/335682?quality=12)

