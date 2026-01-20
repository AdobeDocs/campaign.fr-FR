---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '2430'
ht-degree: 3%

---
# Analyse des billets AC-UI Jira - Résumé de travail&#x200B;**Date :** 12 Janvier 2026&#x200B;**Type De Document :** Document De Travail / Analyse Interne

&#x200B;---

## Synthèse

Ce document analyse les tickets Jira du produit provenant de plusieurs requêtes liées aux versions d’AC-UI (janvier 2026 et novembre 2025). L’analyse se concentre sur l’identification des exigences en matière de documentation, la proposition de billets DOCAC et la mise en évidence des questions ouvertes.

**Nombre total de billets uniques analysés :** 19
**Tickets Nécessitant Une Documentation :** 14
**Tickets Déjà Documentés :** 5
**Billets sans document nécessaire :** 5

&#x200B;---

## &#x200B;1. Liste des billets analysés

### 1.1 Version mensuelle de AC-UI-26-01 (janvier 2026)

| ID de ticket | Title | Statut | Priorité | Composants |
|-----------|-------|--------|----------|------------|
| NEO-91565 | [Interface utilisateur web] Ajouter la prise en charge des champs de personnalisation (intégration avancée d’AEM) | Résolu | Normal | ACS vers ACC, PIX UI/UX |
| NEO-80973 | Disponibilité des rapports dynamiques pour tous les utilisateurs de l’interface utilisateur web | En cours | Normal | ACS vers ACC, PIX UI/UX |
| NEO-86754 | Test A/B [UX/UI] | En cours | Bloqueur | UI/UX PIX |
| NEO-76126 | Création de schémas : créez une table, étendez les schémas et accédez à une base de données externe. | En cours | Critique | UI/UX PIX |
| NEO-93487 | [Interface utilisateur web] Processus de calcul de la planification des diffusions similaire à celui d’ACS | Nouveau | Critique | UI/UX PIX |
| NEO-92400 | Améliorations des versions - 26 janvier | Nouveau | Normal | UI/UX PIX |
| NEO-88838 | Éditeur de contenu : utiliser des variables de thème dans un fragment | Nouveau | Normal | UI/UX PIX |
| NEO-92668 | [ UX/UI ] Web Analytics | Nouveau | Normal | UI/UX PIX |
| NEO-86753 | Intégration [UX/UI] AEM pour les Live Copies et les copies de langue | Nouveau | Bloqueur | ACS vers ACC, PIX UI/UX |

### Billets liés aux améliorations de version 1.2 (NEO-92400)

| ID de ticket | Title | Statut | Priorité | Composants |
|-----------|-------|--------|----------|------------|
| NEO-92942 | [Créateur de règles] Filtres prédéfinis - Option partagée | Résolu | Normal | UI/UX PIX |
| NEO-91299 | Interface utilisateur web - Activité de diffusion au fil de l’eau | Fermée | Majeur | UI/UX PIX |
| NEO-90130 | Activer le chargement de fichier prêt à l’emploi pour les diffusions de notifications push multilingues | Fermée | Critique | ACS vers ACC, PIX UI/UX |

### 1.3 AC-UI-25-11-Monthly Release (Novembre 2025)

| ID de ticket | Title | Statut | Priorité | Composants |
|-----------|-------|--------|----------|------------|
| NEO-91566 | [Interface utilisateur web] prise en charge du suivi CTA dans l’interface utilisateur web | Fermée | Normal | ACS vers ACC, PIX UI/UX |
| NEO-91564 | [Interface utilisateur web] [AEM multilingue dans ACC] prise en charge de l’interface utilisateur pour AEM multilingue | Fermée | Normal | ACS vers ACC, PIX UI/UX |
| NEO-90183 | [UX/UI] Envoi enrichi multilingue - IU | Fermée | Bloqueur | UI/UX PIX |
| NEO-91567 | [Interface utilisateur web] Ajouter la prise en charge de la fonctionnalité NRT | Résolu | Normal | ACS vers ACC, PIX UI/UX |
| NEO-91563 | API REST transactionnel pour l’enrichissement basé sur les profils - interface utilisateur web | Résolu | Normal | ACS vers ACC, PIX UI/UX |
| NEO-92151 | Messagerie transactionnelle d’enrichissement basée sur les profils [UI/UX] - Phase 2 | Résolu | Majeur | ACS vers ACC, PIX UI/UX |
| NEO-84916 | [UX/UI] Configurer et gérer le processus de validation | Résolu | Critique | UI/UX PIX |

&#x200B;---

## &#x200B;2. Tickets Nécessitant Une Documentation

### 2.1 PRIORITÉ ÉLEVÉE - Développement actif (AC-UI-26-01)

#### **NEO-86754 : Test A/B**- **Statut :** En Cours (En Cours)- **Pourquoi une documentation est-elle nécessaire** nouvelle fonctionnalité majeure pour l’expérimentation de contenu d’e-mail avec des fonctionnalités de test A/B ?- **Existant DOCAC:** DOCAC-13104 (nouveau statut)- **Portée de la documentation :**   - Création d’expériences de test A/B dans les diffusions   - Définir les variantes de contenu et de diffusion   - Définition des proportions d’échantillon et envoi des variantes de test   - Définir les critères d&#39;évaluation   - Analyse des résultats de l’expérience et sélection des expériences gagnantes   - Bonnes pratiques et limites- **Public cible : utilisateurs marketing** responsables de campagne- **Version :** 8.9.1, AC-UI-26-01-Monthly- **Questions ouvertes :**   - Statut de validation de l’interface utilisateur/expérience utilisateur final ?   - Existe-t-il des limitations pour les messages transactionnels ?   - Intégration avec l’aperçu du contenu Acrite ?

#### **NEO-80973 : Disponibilité Des Rapports Dynamiques**- **Statut :** en cours (prêt pour la révision)- **Pourquoi une documentation est-elle nécessaire** étendre les rapports dynamiques à tous les utilisateurs de l’interface utilisateur web (et pas seulement aux clients ACC 8.7 ACS) ?- **DOCAC existant :** DOCAC-11070 (fermé), DOCAC-13432 (résolu - limitations de langue)- **Portée de la documentation :**   - Exigences en matière de disponibilité et d’accès   - Documentation sur les langues prises en charge   - Limites connues par rapport aux rapports hérités   - Affichage de mesures en conflit avec les rapports hérités   - Configuration de l’environnement de démonstration- **Public cible :** tous les utilisateurs et utilisatrices de l’interface utilisateur web, analystes- **Version :** 8.8.1, AC-UI-26-01-Monthly- **Questions ouvertes :**   - Statut de disponibilité de l’environnement de démonstration ?   - Liste complète des mesures en conflit avec les rapports hérités ?   - Matrice de prise en charge linguistique ?

#### **NEO-76126 : Création De Schémas**- **Statut :** En Cours (En Cours)- **Pourquoi une documentation est-elle nécessaire** fonctionnalité d’administration importante pour la gestion des modèles de données ?- **Existant DOCAC:** DOCAC-13826 (nouveau statut)- **Portée de la documentation :**   - Créer des tables   - Extension des schémas existants   - Accès aux bases de données externes   - Définition du formulaire pour les entités personnalisées   - Navigation et opérations CRUD   - Fonctionnalités de la phase 3 (création et extension de schémas) - Fin février ETA- **Public cible : utilisateurs administrateurs** administrateurs techniques- **Version :** AC-UI-26-01-Monthly- **Date d’échéance** 28 février 2026- **Questions ouvertes :**   - Quand la phase 2 sera-t-elle terminée pour l&#39;activation de FF ?   - Confirmation du calendrier de livraison de la phase 3 ?   - Exigences de configuration de l’environnement ?

#### **NEO-93487 : Processus De Calcul De La Planification Des Diffusions (H&amp;M)**- **Statut :** Nouveau- **Pourquoi une documentation est-elle nécessaire** remontée d’informations critiques auprès du client - planification de diffusion basée sur le fuseau horaire- **DOCAC existant :** non identifié- **Portée de la documentation :**   - Planification des diffusions en fonction du fuseau horaire de l’utilisateur   - Utilisation de formules calculées pour les régions à plusieurs fuseaux horaires   - Exemples de configuration (par exemple, États-Unis avec plusieurs fuseaux horaires)   - Bonnes pratiques pour les campagnes globales   - Comparaison des fonctionnalités avec ACS- **Audience cible :** des responsables de campagne, des utilisateurs marketing- **Impact sur le client :** H&amp;M (plus de 50 marchés)- **Version :** 8.9.1, AC-UI-26-01-Monthly, 8.8.2.NEO-90300- **Questions ouvertes :**   - Démonstration des fonctionnalités programmée avec PM ?   - Des spécifications fonctionnelles complètes sont-elles disponibles ?   - Les maquettes de l’interface utilisateur ont-elles été finalisées ?

#### **NEO-86753 : intégration d’AEM pour les Live Copies et les copies de langue**- **Statut :** Nouveau- **Pourquoi une documentation est-elle nécessaire** fonctionnalité spécifique à Microsoft pour la gestion de contenu multilingue ?- **Existing DOCAC:** DOCAC-13829 (Résolu)- **Portée de la documentation :**   - Parcourir les modèles de diffusion AEM   - Création de Live Copies   - Créer une langue copie des variantes de contenu   - Workflow et bonnes pratiques   - Exigences de configuration de l’intégration- **Public cible : utilisateurs marketing** travaillant avec AEM, équipes Microsoft- **Version :** AC-UI-26-01-Monthly- **Priorité:** Bloqueur- **Questions ouvertes :**   - Travail transféré à l&#39;équipe de Himanshu - statut actuel ?   - Planning d&#39;achèvement ?

#### **NEO-92668 : Web Analytics**- **Statut :** Nouveau (Sur La Bonne Voie)- **Pourquoi une documentation est-elle nécessaire** configuration de compte externe pour l’intégration de Web Analytics ?- **DOCAC existant :** non identifié- **Portée de la documentation :**   - Création de compte externe Web Analytics   - Paramètres de configuration   - Intégration au tracking des diffusions   - Fonctionnalités de reporting- **Public cible : utilisateurs administrateurs** analystes marketing- **Version :** AC-UI-26-01-Monthly- **Questions ouvertes :**   - Statut de disponibilité de l’environnement ?   - Étapes de configuration requises ?

### 2.2 PRIORITÉ DE MEDIUM - Livré récemment (AC-UI-25-11)

#### **NEO-90183 : notifications push riches multilingues**- **Statut :** Résolu- **Pourquoi une documentation est-elle nécessaire** nouvelle fonctionnalité de notification push riche iOS/Android avec prise en charge multilingue- **Existant DOCAC:** DOCAC-13565 (nouveau statut)- **Portée de la documentation :**   - Configuration des notifications push enrichies pour iOS et Android   - Variantes de contenu multilingue   - Sélection de modèles   - Champs supplémentaires pour le contenu enrichi   - Fonctionnalités de chargement de fichier   - Bonnes pratiques et limites- **Public cible : utilisateurs marketing** gestionnaires de canaux mobiles- **Version :** AC-UI-25-11-Monthly, 8.8.2- **Client :** H&amp;M

#### **NEO-84916 : Gestion du processus d&#39;approbation**- **Statut:** Résolu- **Pourquoi une documentation est-elle nécessaire** principale fonctionnalité de workflow pour la validation de la diffusion- **Existant DOCAC:** DOCAC-13827 (nouveau statut)- **Portée de la documentation :**   - Configuration des opérateurs de validation dans les diffusions/campagnes   - Configuration de la validation du contenu   - Configuration de la validation de la cible   - Gestion des workflows d’approbation sur plusieurs canaux (e-mail, SMS, Push iOS/Android, publipostage direct, centre d’appels)   - Processus d’acceptation/de rejet   - Rapports et suivi d’approbation- **Audience cible :** des responsables de campagne, utilisateurs administrateurs- **Version :** AC-UI-25-11-Monthly- **Priorité :** critique- **Client :** Pierre Fabre

#### **NEO-91299 : Activité De Diffusion Continue**- **Statut :** Résolu- **Pourquoi une documentation est-elle nécessaire** nouvelle activité de workflow pour les scénarios de diffusion récurrents ?- **DOCAC existant :** DOCAC-13586 (nouveau statut), DOCAC-13808 (fermé - aide contextuelle)- **Portée de la documentation :**   - Configuration de l’activité de diffusion au fil de l’eau   - Exigences du sélecteur de modèle de diffusion   - Traiter les erreurs   - Intégration des workflows   - Cas d’utilisation et exemples- **Public cible : utilisateurs techniques** concepteurs de workflows- **Version :** AC-UI-26.01.06

#### **NEO-90130 : Chargement de fichier push multilingue (H&amp;M)**- **Statut :** Résolu- **Pourquoi une documentation est-elle nécessaire** la parité des fonctionnalités prêtes à l’emploi avec ACS pour les notifications push multilingues basées sur des fichiers ?- **Existant DOCAC:** DOCAC-13606 (nouveau statut)- **Portée de la documentation :**   - Chargement de fichier CSV pour les notifications push multilingues   - Spécifications du format du fichier   - Mapping des champs   - Configurations spécifiques à iOS et Android   - Gestion du type de message de données   - Dépannage et problèmes connus- **Public cible : utilisateurs marketing** responsables de campagne- **Version :** AC-UI-25-10-Monthly, AC-UI-25.11.03- **Priorité :** critique- **Client :** H&amp;M (migration d’ACS vers ACC)

#### **NEO-92942 : Filtres Prédéfinis - Option Partagée**- **Statut:** Résolu- **Pourquoi une documentation est nécessaire** amélioration de la fonctionnalité du créateur de règles- **DOCAC existant :** DOCAC-13697 (statut de révision du code), DOCAC-13522 (fermé - assistant)- **Portée de la documentation :**   - Option partagée pour les filtres prédéfinis   - Gestion de la visibilité des filtres avec d&#39;autres opérateurs   - Comportements ACC par rapport aux comportements de Parcours de marque   - Gestion des listes de filtres- **Audience cible :** tous les utilisateurs, concepteurs de requêtes- **Version :** Version Principale- **FF:** enable-query-filter-shared

### 2.3 PRIORITÉ FAIBLE - Amélioration de l’éditeur de contenu

#### **NEO-88838 : variables de thème dans les fragments**- **Statut :** Nouveau (En Attente)- **Pourquoi une documentation est nécessaire :** fonctionnalité de thème Designer d’e-mail- **Existant DOCAC:** DOCAC-12941 (nouveau statut)- **Portée de la documentation :**   - Utilisation de variables de thème dans des fragments d’e-mail   - Configuration du thème   - Gestion des variables   - Bonnes pratiques- **Public cible : concepteurs d’e-mails** utilisateurs marketing- **Version :** AC-UI-26-01-Monthly- **Remarque :** fonctionnalité est en attente de révision côté acrite

&#x200B;---

## &#x200B;3. Tickets NE NÉCESSITANT PAS de documentation

### 3.1 Annulé/Non Applicable

| ID de ticket | Title | Raison |
|-----------|-------|--------|
| NEO-91566 | suivi de CTA dans l’interface utilisateur web | Aucun travail d&#39;interface utilisateur attendu ; informations en attente de MSFT |
| NEO-91564 | Prise en charge de l’interface utilisateur multilingue d’AEM | Travail de l’interface utilisateur géré par différentes équipes |
| NEO-91567 | Prise en charge des fonctionnalités NRT | Aucun impact sur l’interface utilisateur web ; spécification disponible |
| NEO-91563 | API REST transactionnel | Aucune interface utilisateur web active ; mise à niveau de l’instance en attente |
| NEO-92151 | Enrichissement du profil - Phase 2 | L&#39;histoire n&#39;a pas de tâches ; marquée comme n&#39;étant plus applicable |

### 3.2 Espace réservé/billets de suivi

| ID de ticket | Title | Raison |
|-----------|-------|--------|
| NEO-92400 | Améliorations des versions - 26 janvier | Espace réservé pour suivre l’achèvement des améliorations |

&#x200B;---

## &#x200B;4. Billets DOCAC proposés

### 4.1 Nouveaux billets DOCAC nécessaires

#### **DOCAC-XXXX : planification des diffusions avec prise en charge des fuseaux horaires**&#x200B;**Ticket parent :** NEO-93487&#x200B;**Priorité :** critique&#x200B;**Version cible :** AC-UI-26-01-Monthly&#x200B;**Description:**&#x200B;Documentez le nouveau processus de calcul de planification des diffusions qui active la planification des diffusions basée sur le fuseau horaire similaire à la fonctionnalité ACS. Cette fonctionnalité permet aux spécialistes marketing d’envoyer des communications en fonction des fuseaux horaires des destinataires à l’aide de formules calculées, ce qui est particulièrement important pour les marchés comportant plusieurs fuseaux horaires, comme les États-Unis.

**Portée :**
- Guide de configuration de la planification basée sur le fuseau horaire
- Exemples de formules calculées
- Scénarios de marché avec plusieurs fuseaux horaires
- Guide de migration depuis ACS
- Bonnes pratiques et limites

**Client :** H&amp;M (essentiel pour la migration d’ACS vers ACC)

#### **DOCAC-XXXX : configuration du compte externe Web Analytics**&#x200B;**Ticket parent :** NEO-92668&#x200B;**Priorité :** normale&#x200B;**Version cible :** AC-UI-26-01-Monthly&#x200B;**Description:**&#x200B;Documentez la configuration et l’utilisation du type de compte externe Web Analytics dans l’interface utilisateur Web.

**Portée :**
- Étapes de création du compte externe
- Paramètres de configuration
- Intégration au tracking des diffusions
- Fonctionnalités de reporting
- Résolution des problèmes

&#x200B;---

### 4.2 Billets DOCAC existants à mettre à jour

#### **DOCAC-13104 : Test A/B**&#x200B;**Statut :** Nouveau&#x200B;**Ticket parent :** NEO-86754&#x200B;**Action nécessaire :** démarrer la documentation - fonctionnalité dans le développement actif&#x200B;**Diffusion estimée :** février 2026 (en attente d’achèvement du développement)

#### **DOCAC-11070 et DOCAC-13432 : rapports dynamiques**&#x200B;**Statut :** Fermé/Résolu&#x200B;**Ticket parent :** NEO-80973&#x200B;**Action nécessaire :**- Mise à jour pour la disponibilité générale (pas seulement 8.7)- Documenter les mesures en conflit avec les rapports hérités- Vérification de la documentation de prise en charge linguistique

#### **DOCAC-13826 : création de schémas**&#x200B;**Statut :** Nouveau&#x200B;**Ticket parent :** NEO-76126&#x200B;**Action nécessaire :**- Documentation de la phase 2 (navigation + CRUD + définition du formulaire)- Préparation de la phase 3 (création/extension de schémas) - Fin février ETA

#### **DOCAC-13829 : Live Copies/copies de langue AEM**&#x200B;**Statut:** Résolu&#x200B;**Ticket parent :** NEO-86753&#x200B;**Action nécessaire :** vérifier le statut actuel et effectuer la mise à jour selon les besoins

#### **DOCAC-13565 : notifications push riches et multilingues**&#x200B;**Statut :** Nouveau&#x200B;**Ticket parent :** NEO-90183&#x200B;**Action nécessaire :** documentation complète - fonctionnalité fournie en novembre 2025

#### **DOCAC-13827 : processus d’approbation**&#x200B;**Statut :** Nouveau&#x200B;**Ticket parent :** NEO-84916&#x200B;**Action nécessaire :** documentation complète - fonctionnalité fournie en novembre 2025

#### **DOCAC-13586 et DOCAC-13808 : diffusion en continu**&#x200B;**Statut :** Nouveau/Fermé&#x200B;**Ticket parent :** NEO-91299&#x200B;**Action nécessaire :** documentation principale complète (13586) - fonctionnalité fournie

#### **DOCAC-13606 : téléchargement de fichier push multilingue**&#x200B;**Statut :** Nouveau&#x200B;**Ticket parent :** NEO-90130&#x200B;**Action nécessaire :** documentation complète - fonctionnalité fournie

#### **DOCAC-13697 et DOCAC-13522 : filtres prédéfinis partagés**&#x200B;**Statut : Révision** code/Fermé&#x200B;**Ticket parent :** NEO-92942&#x200B;**Action nécessaire :** finaliser la documentation (13697)

#### **DOCAC-12941 : thèmes dans Email Designer**&#x200B;**Statut :** Nouveau&#x200B;**Ticket parent :** NEO-88838&#x200B;**Action nécessaire :** en attente de la revisite de la fonctionnalité

&#x200B;---

## &#x200B;5. Questions ouvertes et informations manquantes

### 5.1 Par caractéristique

#### **Test A/B (NEO-86754)**- [ ] Quel est le statut final de la validation de l’IU/de l’expérience utilisateur ?- [ ] Existe-t-il des limitations spécifiques aux messages transactionnels ?- [ ] Comment cela s’intègre-t-il à l’aperçu de contenu Acrite (blocage NEO-92516) ?- [ ] Quelles sont les fonctionnalités de simulation/prévisualisation de chaque variante ?

#### **Rapports dynamiques (NEO-80973)**- [ ] Quel est l’état de la réactivation de l’environnement de démonstration ?- [ ] Liste complète des mesures en conflit avec les rapports hérités ?- [ ] Matrice détaillée de prise en charge des langues ?- [ ] la comparaison des performances avec les rapports hérités ?

#### **Création de schémas (NEO-76126)**- [ ] Quand la phase 2 du FF sera-t-elle activée ?- [ ] ETA confirmé pour la phase 3 (création/extension de schémas) ?- [ ] Quelles sont les exigences de configuration de l’environnement ?- [ ]-vous des limites par rapport aux fonctionnalités de la console cliente ?

#### **Planification de la diffusion (NEO-93487)**- [ ] La démonstration de la fonctionnalité avec PM est-elle planifiée ?- [ ] Des spécifications fonctionnelles complètes sont-elles disponibles ?- [ ] maquettes de l’interface utilisateur ont-elles été finalisées et examinées ?- [ ] Quelle est la syntaxe/structure exacte de la formule ?

#### **Live Copies/copies de langue AEM (NEO-86753)**- [ ] Quel est le statut actuel de l&#39;équipe d&#39;Himanshu ?- [ ] La chronologie de diffusion a-t-elle été mise à jour ?- [ ]-vous des dépendances de la version d’AEM ?

#### **Web Analytics (NEO-92668)**- [ ] Qu’est-ce que le statut de disponibilité de l’environnement ?- [ ] les exigences de configuration complètes ?- [ ] Plateformes d’analyse prises en charge ?

#### **Variables de thème dans les fragments (NEO-88838)**- [ ] Quand Acrite revisitera-t-il la fonctionnalité ?- [ ] Est-ce toujours prévu pour AC-UI-26-01 ?

### 5.2 Par Version

#### **AC-UI-26-01-Monthly (Janvier 2026)**- [ ] Confirmation de la date de publication officielle ?- [ ] Date de gel des fonctionnalités ?- [ ] le calendrier d’achèvement du test ?- [ ] échéance de diffusion de la documentation ?

#### **Fonctionnalités de la version de novembre 2025**- [ ] Quelles fonctionnalités sont déjà activées en production ?- [ ] des problèmes connus ou des limites découvertes après la publication ?- [ ] de commentaires du client reçus ?

### 5.3 Processus de documentation

- [ ] Qui sont les experts pour chaque fonctionnalité ?
- [ ] Quel est le processus d&#39;examen de la documentation ?
- [ ] langue de documentation de Target (en anglais uniquement ou multilingue) ?
- [ Exigences relatives à la plateforme/au format de la documentation ] ?
- [ ] des captures d’écran et la disponibilité de l’environnement de démonstration ?

&#x200B;---

## &#x200B;6. Impact et remontées sur le client

### 6.1 Tickets clients critiques

| Client ou cliente | Ticket | Fonctionnalité | Impact |
|----------|--------|---------|--------|
| **H&amp;M** | NEO-93487 | Planification des diffusions | Plus de 50 marchés ; exigences de diffusion multi-fuseaux horaires ; bloqueur de migration d’ACS vers ACC |
| **H&amp;M** | NEO-90130 | Chargement de fichier push multilingue | Critique pour la migration d’ACS vers ACC ; réduit les coûts opérationnels |
| **Pierre Fabre** | NEO-84916 | Processus d&#39;approbation | Exigences réglementaires et de workflow |

### 6.2 Fonctionnalités Spécifiques À Microsoft

| Ticket | Fonctionnalité | Statut | Notes |
|--------|---------|--------|-------|
| NEO-86753 | Live Copies/copies de langue AEM | Nouveau | Largement utilisé par Microsoft |
| NEO-91566 | Suivi de CTA | Fermé/Ne S’Applique Plus | Informations en attente de MSFT |
| NEO-91567 | Fonctionnalité NRT | Résolu/Aucun impact sur l’interface utilisateur | Nouvelle fonctionnalité ACS pour MSFT |

&#x200B;---

## &#x200B;7. Priorités et calendrier en matière de documentation

### 7.1 Mesures immédiates requises (janvier 2026)

**PRIORITÉ ÉLEVÉE - Diffusée mais non documentée :**
1. **NEO-90183** - Envoi enrichi multilingue (DOCAC-13565)
2. **NEO-84916** - Processus d’approbation (DOCAC-13827)
3. **NEO-91299** - Diffusion au fil de l&#39;eau (DOCAC-13586)
4. **NEO-90130** - Chargement de fichier push multilingue (DOCAC-13606)

### 7.2 En Cours - Développement En Cours (Février-Mars 2026)

**PRIORITÉ CRITIQUE :**
1. **NEO-86754** - Test A/B (DOCAC-13104) - Échéance : Février 2026
2. **NEO-76126** - Création de schémas (DOCAC-13826) - Phase 2 : février, Phase 3 : fin février
3. **NEO-93487** - Planification de la diffusion (NOUVEAU DOCAC) - Transmission d’informations critiques au client

**PRIORITÉ NORMALE:**
1. **NEO-80973** - Rapports dynamiques (mettre à jour DOCAC-11070)
2. **NEO-92668** - Web Analytics (NOUVEAU DOCAC)
3. **NEO-86753** - Live/copies de langue AEM (DOCAC-13829)

### 7.3 En Attente / Futur

1. **NEO-88838** - Variables de thème (DOCAC-12941) - Révision Acrite en attente

&#x200B;---

## &#x200B;8. Prochaines Étapes

### 8.1 Actions de l’équipe de documentation1. **Hiérarchiser les fonctionnalités diffusées** sans documentation (section 7.1)2. **Créer des tickets DOCAC** pour NEO-93487 et NEO-926683. **Mise à jour des tickets DOCAC** existants avec une portée détaillée (section 4.2)4. **Planifier des entretiens avec les experts** pour les tests A/B, les schémas et la planification des diffusions5. **Collecter des captures d’écran** et préparer les environnements de démonstration6. **Révision et finalisation** limites de langue pour les rapports dynamiques

### 8.2 Collecte d&#39;informations1. **Contactez les ingénieurs principaux** pour connaître les mises à jour de statut sur :   - Validation finale des tests A/B   - Chronologie de la phase 2/3 des schémas   - Spécifications de planification des diffusions2. **Planification de démonstrations de fonctionnalités** avec la gestion des produits3. **Recueillir les commentaires des clients** de H&amp;M et Pierre Fabre4. **Vérifier la disponibilité de l’environnement** pour Web Analytics et les rapports dynamiques

### 8.3 Coordination1. **Synchroniser avec l’équipe d’Himanshu** sur AEM Live/Language Copies2. **Coordination avec l’équipe Acrite** sur le statut des variables de thème3. **Suivi des fonctionnalités spécifiques à Microsoft** avec l’équipe de compte

&#x200B;---

## Historique du document

| Date | Auteur ou autrice | Version | Modifications |
|------|--------|---------|---------|
| 12/01/2026 | Assistant IA | 1,0 | Analyse initiale des requêtes Jira |

&#x200B;---

## Annexe : Requêtes Jira Analysées

1. `project = NEO AND fixVersion = AC-UI-26-01-Monthly and type = story order by status`
2. `issueFunction in linkedIssuesOf('key=NEO-92400', 'is implemented by')`
3. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and type = story order by status`
4. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and fixVersion != 8.8.2 and type = story order by status`

**Total des résultats :** 19 tickets uniques analysés

