---
product: campaign
title: Note technique - Chiffrement et déchiffrement asymétriques dans Adobe Campaign
description: Note technique - Chiffrement et déchiffrement asymétriques dans Adobe Campaign
hide: true
hidefromtoc: true
source-git-commit: 1d9d4111cde1e230220a04c8fd10a126116339ad
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 2%

---

# Note technique : chiffrement et déchiffrement asymétriques dans Adobe Campaign {#asymetric-encryption}

La cryptographie à clé publique, ou cryptographie asymétrique, est le domaine des systèmes cryptographiques qui utilisent des paires de clés associées. Chaque paire de clés se compose d’une **clé publique** et d’une **clé privée** correspondante.

* La **clé publique** est partagée ouvertement et utilisée pour chiffrer les données.

* La **clé privée** est gardée secrète et utilisée pour déchiffrer les données.

Cette approche garantit que même si une personne dispose de la clé publique, elle ne peut pas déchiffrer le message sans la clé privée. Il fournit des fonctionnalités de sécurité clés telles que la confidentialité, l’authentification et l’intégrité.

Depuis Adobe Campaign v8.8.3, deux nouvelles fonctions JavaScript sont ajoutées pour le chiffrement et le déchiffrement :

* Chiffrement à l&#39;aide de la clé publique : `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* Déchiffrement à l’aide d’une clé privée : `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


Exemple :

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

**Ressources supplémentaires**

* [Prise en main  [!DNL Campaign]  API](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [Documentation JSAPI Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=fr){target="_blank"}
