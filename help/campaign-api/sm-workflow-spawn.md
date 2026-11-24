---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 4%
---
# Frayer

Crée une instance de workflow à partir d’un modèle, applique un patch puis démarre ce workflow.

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## Paramètres

**workflowId** Identifiant ou nom interne du modèle de workflow.

**patch** Élément XML qui doit être fusionné avec le modèle pour obtenir l’instance avant de l’exécuter. Exemple:

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

Cet exemple remplace les arguments de l&#39;activité &#39;notepad&#39;. Si vous ne souhaitez pas appliquer ce correctif, utilisez un élément &lt;workflow/> vide ou une chaîne vide.

## Valeur(s) renvoyée(s)

**instanceId** Identifiant de l’instance créée à partir du modèle.

## Remarques

La commande est exécutée en mode asynchrone et n’a pas d’effet immédiat après le retour de la méthode. Le workflow est démarré avec le compte de l’opérateur appelant.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
