---
title: Récupérer des abonnements
description: Découvrez comment récupérer des abonnements à l’aide des API
role: Data Engineer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 100%

---

# Récupérer des abonnements à l’aide des API {#retrieving-subscriptions-api}

## Récupération des profils abonnés à un service

Cette procédure comporte deux étapes.

1. Récupérez l’URL des abonnements pour le service souhaité.
1. Exécutez une requête GET sur l’URL des abonnements. Elle renvoie la liste des abonnements pour le service, avec chaque profil associé.

>[!CAUTION]
>
>L’API REST renvoie la propriété « href », qui contient l’URL à utiliser. <b>Utilisez systématiquement l’URL contenue dans la réponse pour exécuter la requête d’API suivante</b>.

<br/>

***Exemple de requête***

Exécutez une requête GET pour récupérer le service.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie l’URL des abonnements du service.

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

Exécutez une requête GET sur l’URL des abonnements.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

La liste des abonnements pour le service s’affiche, avec chaque profil associé.

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## Récupération des services auxquels un profil s’est abonné

Cette procédure comporte deux étapes.

1. Récupérez l’URL des abonnements pour un profil donné.
1. Exécutez une requête GET sur l’URL. Elle renvoie la liste des abonnements pour le profil, avec chaque service associé.

<br/>

***Exemple de requête***

Exécutez une requête GET pour récupérer le profil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie l’URL des abonnements du profil.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

Exécutez une requête GET sur l’URL des abonnements.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie la liste des services auxquels le profil s’est abonné.

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
