---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 74%
---
# séance

Sessions vers le serveur applicatif

## Méthodes

| Méthode | Description |
| --- | --- |
| [ApplyDuplicateRules](sm-session-applyduplicaterules.md) | Applique les règles de duplication (valeurs par défaut entre autres) au document passé en paramètre |
| [BearerTokenLogon](sm-session-bearertokenlogon.md) | jeton de connexion |
| [Modifier le mot de passe](sm-session-changepassword.md) | Change le mot de passe du compte courant |
| [DeleteCollection](sm-session-deletecollection.md) | Supprimer une liste d&#39;entités en fonction d&#39;une condition |
| [Diff](sm-session-diff.md) | Retourne la version actuelle et la version d&#39;origine d&#39;un document. |
| [Doublon](sm-session-duplicate.md) | Duplique un nouveau document à partir d&#39;un document source |
| [DupliquerVers](sm-session-duplicateto.md) | Duplique un nouveau document à partir d&#39;un document source vers un dossier particulier |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | Duplique un nouveau document à partir d&#39;un document source avec le mapping des identifiants |
| [Chiffrer](sm-session-encrypt.md) | Chiffre la chaîne de caractère avec la clé de l&#39;instance. |
| [EncryptServerPassword](sm-session-encryptserverpassword.md) | Chiffre la chaîne de caractères avec la clé du serveur. |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | Applique une transformation à la chaîne de caractères selon la politique de données passée en paramètre. Rend la chaîne inchangée en cas d&#39;échec. |
| [GetActiveApplicationMenus](sm-session-getactiveapplicationmenus.md) | Retourne un document contenant les menus des applications actives sur le login courant |
| [GetCnxInfo](sm-session-getcnxinfo.md) | Récupère les informations des connexions courantes. |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | Retourne un document contenant une entité vide avec ses valeurs par défaut |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | Renvoie les entités en cache pas à jour |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | Charge une entité si sa clé MD5 est différente de celle passée en paramètre |
| [GetImages](sm-session-getimages.md) | Charger une liste d&#39;images |
| [GetNewIds](sm-session-getnewids.md) | Récupère une liste d&#39;identifiant de clés internes de la base de données. |
| [GetNewIdsEx](sm-session-getnewidsex.md) | Récupère une liste d&#39;identifiants uniques de la base de données en spécifiant un nom de séquence. |
| [GetOption](sm-session-getoption.md) | Récupère la valeur d&#39;une option base de donnée. |
| [GetPkList](sm-session-getpklist.md) | Récupère la liste des identifiants des instances |
| [GetServerTime](sm-session-getservertime.md) | Renvoie l&#39;heure du serveur |
| [GetUserInfo](sm-session-getuserinfo.md) | Accès aux informations concernant l&#39;opérateur courant |
| [HashPassword](sm-session-hashpassword.md) | Hash un mot de passe avec la clé du serveur. |
| [ImportCollection](sm-session-importcollection.md) | Met à jour une liste d&#39;entités en import |
| [Interrompre la session](sm-session-killsession.md) | Ferme la session indiquée en paramètre |
| [Charger](sm-session-load.md) | Chargement de l&#39;entité |
| [LoadAsText](sm-session-loadastext.md) | Récupère le contenu de l&#39;entité comme texte |
| [LoadIfExists](sm-session-loadifexists.md) | Charge l&#39;entité si elle existe |
| [Déconnexion](sm-session-logoff.md) | Ferme la session courante |
| [Connexion](sm-session-logon.md) | Ouvre une session |
| [NouvelleInstance](sm-session-newinstance.md) | Création d&#39;un nouveau document, pré-initialisé mais non sauvé |
| [Supprimer](sm-session-remove.md) | Suppression de l&#39;entité |
| [ServerShutdown](sm-session-servershutdown.md) | Demande d&#39;arrêt du serveur |
| [DéfinirValeursParDéfaut](sm-session-setdefaultvalues.md) | Fixer les valeurs par défaut à partir du XPath |
| [Définir les valeurs par défaut](sm-session-setdefaults.md) | Fixer les valeurs par défaut |
| [TestCnx](sm-session-testcnx.md) | Tester la connexion. |
| [Write](sm-session-write.md) | Met à jour une entité |
| [WriteCollection](sm-session-writecollection.md) | Met à jour une liste d&#39;entités |

## Méthodes génériques

| Méthode | Description |
| --- | --- |
| [créer](f-create.md) | Crée une nouvelle entité correspondant à un schéma donné. |
| [charger](f-load.md) | Charge et retourne une entité correspondant à un schéma et une clé donnés. |
| [enregistrer](m-entity-save.md) | Enregistre une entité dans la base de données. |
