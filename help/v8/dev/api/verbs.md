---
title: Verbes GET / POST / PATCH / DELETE
description: Découvrez les verbes utilisés dans les API de Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: de97a194-d497-4665-906e-53178fd3b119
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 100%

---

# Verbes GET / POST / PATCH / DELETE {#verbs}

Les verbes disponibles pour effectuer des opérations sur les ressources sont les suivants :

* `GET` : récupère un élément ou une collection d’éléments.
* `POST` : crée une ressource avec des paramètres.
* `PATCH` : met à jour une ressource avec des paramètres.
* `DELETE` : supprime une ressource.

<!-- ajouter codes retour -->

<br/>

***Exemples de demande***

* Exemple de requête GET sur la collection de profils.


  ```
  $curl  
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Elle renvoie un tableau de profils.


  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "firstName": "Olivia",
              "lastName": "Varney",
              "birthDate": "1977-09-°4",
              "email": "o.varney@mail.com",
          },
          {
              "PKey": "<PKEY>",
              "firstName": "John",
              "lastName": "Doe",
              "birthDate": "1985-08-17",
              "email": "johndoe@mail.com",
          }
      ],
  }
  ```

* Exemple de requête GET sur un profil spécifique.


  ```
  $curl  
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Elle renvoie le profil demandé.


  ```
  {
      "PKey": "<PKEY>",
      "firstName": "John",
      "lastName": "Doe",
      "birthDate": "1985-08-17",
      "email": "johndoe@mail.com",
      ...
  }
  ```

* Exemple de requête POST pour créer un profil.


  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -d '{"lastName":"Doe"}'
  ```

  Elle renvoie le profil avec les champs par défaut.

  ```
  {
      "PKey": "<PKEY>",
      "firstName": "John",
      "lastName": "Doe",
      "birthDate": "1985-08-17",
      "email": "johndoe@mail.com",
  }
  ```

* Exemple de requête PATCH pour mettre à jour un profil.

  ```
  -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -d '{"firstName":"Mark"',"lastName":"Smith"}'
  ```

  Elle renvoie la clé PKEY et l’URL pour récupérer le profil mis à jour.

  ```
  {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>"
  }
  ```

* Exemple de requête DELETE pour supprimer un profil.

  ```
  -X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Elle renvoie une réponse 200, confirmant que le profil a été supprimé.
