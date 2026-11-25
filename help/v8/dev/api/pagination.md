---
title: Pagination
description: Découvrez comment effectuer des opérations de pagination.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: f058ae441fff4b10bcffd84e1b7e44f00e4828a8
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 76%
---
# Pagination

Par défaut, 25 ressources sont chargées dans une liste.

Le paramètre **_lineCount** permet de limiter le nombre de ressources répertoriées dans la réponse.  Vous pouvez ensuite utiliser le nœud **suivant** pour afficher les résultats suivants.

>[!NOTE]
>
>Utilisez toujours la valeur d’URL renvoyée dans le nœud **suivant** pour effectuer une requête de pagination.
>
>La requête **_lineStart** est calculée et doit toujours être utilisée dans l’URL renvoyée dans le nœud **suivant**.

<br/>

***Exemple de requête***

Exemple de requête GET pour afficher 1 enregistrement de la ressource de profil.

```bash
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Réponse à la requête, avec le nœud **suivant** pour effectuer la pagination.

```json
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Par défaut, le nœud **next** n’est pas disponible lors de l’interaction avec des tables contenant une grande quantité de données. Pour pouvoir effectuer une pagination, vous devez ajouter le paramètre **_forcePagination=true** à votre URL d’appel.

```bash
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Le nombre d&#39;enregistrements au-dessus desquels un tableau est considéré comme volumineux est défini dans l&#39;option Campaign Standard **XtkBigTableThreshold**. La valeur par défaut est 100 000 enregistrements.
