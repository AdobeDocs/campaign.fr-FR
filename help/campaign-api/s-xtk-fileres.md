---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 56%
---
# fileRes

Ressource fichiers stockée sur le serveur ou dans la base de données

## Méthodes

| Méthode | Description |
| --- | --- |
| [Publication de fichier](sm-fileres-filepublishing.md) | Effectue la publication des ressources publiques sur les serveurs frontaux. |
| [GetPublicFileResURL](sm-fileres-getpublicfileresurl.md) | Récupère l&#39;URL d&#39;accès au dossier |
| [GetServerFileName](sm-fileres-getserverfilename.md) | Renvoie le nom du fichier sur le serveur l&#39;ayant préalablement copié dans le répertoire de chargement si nécessaire. |
| [GetURL](sm-fileres-geturl.md) | Récupère l&#39;URL d&#39;accès au fichier |
| [PostUpload](sm-fileres-postupload.md) | Finalise l&#39;enregistrement de la ressource suite au chargement sur le serveur en fonction du type de stockage défini. |
| [PréTéléchargement](sm-fileres-predownload.md) | Prépare le téléchargement de la ressource en fonction du type de stockage défini. |
| [PublierSiNécessaire](sm-fileres-publishifneeded.md) | Copie le fichier sur les serveurs de média si besoin |
| [PublishIfNeededFromId](sm-fileres-publishifneededfromid.md) | Copie le fichier sur les serveurs de media si besoin depuis l&#39;identifiant de la ressource |
| [WebPostUpload](sm-fileres-webpostupload.md) | Finalise l’enregistrement de la ressource suite au chargement (à partir d’une page web) sur le serveur en fonction du type de stockage défini. Récupère la page de codes et le type de contenu. |

## Méthodes génériques

| Méthode | Description |
| --- | --- |
| [créer](f-create.md) | Crée une nouvelle entité correspondant à un schéma donné. |
| [charger](f-load.md) | Charge et retourne une entité correspondant à un schéma et une clé donnés. |
| [enregistrer](m-entity-save.md) | Enregistre une entité dans la base de données. |
