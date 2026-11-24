---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%
---
# SubmitNotification

Création et soumission d&#39;une notification depuis un modèle de diffusion

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## Paramètres

**scenarioName** Nom interne du modèle

**target** Cible de la diffusion remplaçant celle du scénario

## Valeur(s) renvoyée(s)

Identifiant de notification **notificationId**

## Remarques

Avertissement : cette API n’est pas conçue pour gérer d’importants volumes de données ou travailler en temps réel. Il est développé pour traiter un maximum de plusieurs appels par minute. SubmitNotification bloque le thread pendant l&#39;analyse de la diffusion. Cela peut prendre quelques secondes. Le paramètre « target » spécifie la cible de la diffusion. Il remplace une cible spécifiée dans le modèle. Pour diffuser vers une cible en base, l&#39;élément cible utilisera la syntaxe suivante :

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

Pour diffuser sur une cible dans un fichier :

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

Il est possible de définir explicitement la cible (en réalité le contenu du fichier utilisé comme cible) :

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

Il est également possible de conserver la cible définie dans le modèle avec l’attribut « \_keepTemplateTarget »

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
