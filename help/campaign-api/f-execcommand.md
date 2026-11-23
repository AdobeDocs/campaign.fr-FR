---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 7%
---
# execCommand

> Avertissement : cette fonction est disponible pour un environnement On-Premise.

Exécute une commande et capture le code d’erreur et la sortie standard.

```text
execCommand (command [, bNoThrow ])
```

## Paramètres

**command** Commande à exécuter avec ses paramètres.

**bNoThrow** true pour obtenir la sortie et le code d’erreur même si la commande ne renvoie pas zéro (false par défaut).

## Valeur renvoyée

Retourne une table dont le premier élément correspond au code retour de la commande (si le code retour est différent de zéro, il y a une anomalie) et le second élément est une chaîne de caractères contenant la sortie standard produite.

## Remarques

Sans l’option bNothroft, une exception est générée si la commande ne peut pas être exécutée ou si la commande est exécutée avec une erreur. Si bNoThrow est égal à true, une exception est générée uniquement si la commande ne peut pas être exécutée. L’opérateur a besoin des droits « createProcess » pour utiliser cette fonction, sinon une exception est générée. Selon votre installation, certaines commandes peuvent se trouver sur la liste bloquée. Par exemple : ln, dd, openssl, curl, wget, python, python3, perl, ruby, sh, bash, dash, zsh, base64, nlserver, node, phantomjs, java, awk, nc, telnet, ssh, scp, ftp.

## Exemple

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
