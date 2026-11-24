---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 7%
---
# Fichier (Classe)

Classe du fichier

> Avertissement :
>
> L’accès via les API de fichiers est limité aux dossiers **var**, **sftp** et temporaires d’Adobe Campaign.

Voici un exemple d’utilisation de la classe pour lire et traiter toutes les lignes d’un fichier en séquence.

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## Méthodes

| Méthode | Description |
| --- | --- |
| [Fichier](m-file-file.md) | Crée un nouvel objet associé à un fichier. |
| [fermer](m-file-close.md) | Ferme le fichier. |
| [copyTo](m-file-copyto.md) | Copie un fichier. |
| [disposer](m-file-dispose.md) | Libère les ressources utilisées par l’objet . |
| [vider](m-file-flush.md) | Force l&#39;écriture sur le disque |
| [liste](m-file-list.md) | Répertorie le contenu d’un répertoire. |
| [mkdir](m-file-mkdir.md) | Crée un répertoire avec le chemin d&#39;accès de l&#39;objet [File](c-file.md) actif. |
| [ouvrir](m-file-open.md) | Ouvre le fichier en mode lecture ou écriture. |
| [supprimer](m-file-remove.md) | Supprime le fichier. |
| [renameTo](m-file-renameto.md) | Renomme un fichier. |
| [readln](m-file-readln.md) | Lit une ligne du fichier texte. |
| [rmdir](m-file-rmdir.md) | Supprime le répertoire (non en cascade). |
| [écriture](m-file-writeln.md) | Écrit une ligne de texte dans le fichier. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [canRead](p-file-canread.md) | Renvoie true si le fichier peut être lu. |
| [canWrite](p-file-canwrite.md) | Renvoie vrai si le fichier peut être modifié. |
| [existe](p-file-exists.md) | Renvoie « true » s’il existe un fichier ou un dossier portant ce nom. |
| [fullName](p-file-fullname.md) | Renvoie le nom du fichier en valeur absolue. |
| [isDirectory](p-file-isdirectory.md) | Renvoie vrai si le fichier est un répertoire. |
| [isFile](p-file-isfile.md) | Renvoie true si le fichier existe et s’il s’agit d’un fichier. |
| [isOpen](p-file-isopen.md) | Renvoie true si le fichier est ouvert. |
| [lastModified](p-file-lastmodified.md) | Renvoie la date de dernière modification sous la forme d’un objet Date. |
| [nom](p-file-name.md) | Renvoie le nom du fichier avec l’extension, mais sans le chemin d’accès. |
| [chemin](p-file-path.md) | Renvoie le chemin d’accès complet du fichier terminé par le séparateur. |
| [taille](p-file-size.md) | Renvoie la taille du fichier en octets. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
