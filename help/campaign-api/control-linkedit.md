---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 1%
---
# LinkEdit

Contrôle pour la modification des liens.

![Contrôle LinkEdit](assets/linkedit.7cb7bf14.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style du contour de contrôle (uni, double, incrustation, départ, aucun).

**choiceButton - booléen** : masque ou affiche le bouton de choix (masqué par défaut).

**computeStringExpr - chaîne** Expression du champ calculé.

**computestringKey - string** Met à jour la chaîne calculée plutôt que la clé étrangère.

**computeStringAlias - chaîne** Alias de chaîne calculé.

**createMode - string** Crée le lien s&#39;il n&#39;existe pas (aucun, inline), avec le mode de modification par défaut.

**externalKey - boolean** Utilise la clé externe.

**font-size - integer** Modifie la taille de la police.

**form - string** Force le formulaire de modification du lien.

**libellé - chaîne** libellé associé.

**loadEntityOnChange - boolean** Recharge l&#39;entité lorsque le lien change.

**mandatory - boolean** Interdit les valeurs vides.

**noAutoComplete - boolean** Désactive le mode de saisie semi-automatique.

**noEdition - booléen** Impossible de modifier le lien.

**nolabel - boolean** Masque le libellé associé.

**notifyPathList - chaîne** Liste de XPaths séparés des éléments liés par des virgules, à charger dans le contexte.

**noTransaction - boolean** Désactive le mode transactionnel.

**noZoom - booléen** Aucun formulaire d’édition de lien.

**orderBy - élément** Planification des choix.

**readOnly - boolean** Force le contrôle en lecture seule.

**obligatoire - booléen** Le champ est obligatoire.

**schéma - chaîne** Schéma du lien.

**serialize - boolean** Enregistre la dernière sélection dans la configuration utilisateur.

**sysFilter - élément** Limitation des choix.

**xpathMandatory - string** Chemin d&#39;accès à une propriété booléenne qui indique si le lien peut être vide ou non.

## Remarques

Exemples:

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
