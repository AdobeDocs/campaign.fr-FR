---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 37%
---
# RegisterGroup

Ajoute les destinataires sélectionnés à une liste

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## Paramètres

**groupList** Listes

**liste des destinataires** Liste des destinataires

**inscrire** Abonner/désabonner les destinataires

## Valeur(s) renvoyée(s)

Aucune.

## Exemple

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## Fonctionnalités

**Schéma :** [nms:recipient](s-nms-recipient.md)

**Statique :**

Oui
