---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01 Analyse de la documentation

## Contenu de la prochaine version

Ce document analyse les JIRA de produit pour les versions mensuelles AC-UI-26-01 et AC-UI-25-11 afin de planifier les actions de documentation.

### Filtres JIRA

1. **[AC-UI-26-01-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Principales nouvelles
2. **[Améliorations de NEO-92400 &#x200B;](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** - Améliorations des versions liées aux problèmes
3. **[AC-UI-25-11-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Report des versions précédentes
4. **[AC-UI-25-11 À l’exclusion de la version 8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)** - Version précédente filtrée

&#x200B;---

## 🟢 Créer un DOCAC

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) - Ajouter la prise en charge des champs de personnalisation (intégration avancée d’AEM)**Statut:** Résolu\**Document requis :** Oui\**Existing DOCAC:** None\**Action :** Créer un DOCAC

**Portée :**
- Prise en charge documentaire des champs de personnalisation dans l’intégration avancée d’AEM
- Workflow de l’interface utilisateur et étapes de configuration
- Fonctionnalités d’intégration multilingue d’AEM

**Description des fonctionnalités :**
Prise en charge de l’ajout de champs de personnalisation dans les diffusions à l’aide de l’intégration avancée d’AEM, permettant l’insertion de contenu dynamique à partir des données Campaign dans des modèles d’email créés par AEM.

**Contexte :** ACS à la parité ACC, exigence spécifique à MSFT

**Références :** [wiki multilingue AEM](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

&#x200B;---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) - Processus de calcul de la planification des diffusions (parité ACS)**Statut :** Nouveau\**Document requis :** Oui\**Existing DOCAC:** None\**Action :** Créer un DOCAC

**Portée :**
- Processus de calcul de planification de diffusion de documents pour les notifications push
- Formules de planification basées sur le fuseau horaire
- Chargement de fichier pour le ciblage multifuseau horaire

**Description des fonctionnalités :**
Activez la planification de diffusion basée sur des fichiers prêts à l’emploi avec des heures d’envoi calculées en fonction du fuseau horaire du destinataire, ce qui permet un ciblage de diffusion unique sur plusieurs fuseaux horaires avec des heures d’envoi optimisées par région.

**Contexte :** piloté par le client (H&amp;M), exigence de parité ACS vers ACC

**Références :** [Documentation ACS](https://experienceleague.adobe.com/fr/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

&#x200B;---

## 🔄 Update DOCAC

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973) - Disponibilité des rapports dynamiques pour tous les utilisateurs de l’interface utilisateur web&#x200B;**Statut :** En Cours\**Document requis :** Oui\**Existant DOCAC:** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070) (Fermé), [DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432) (Résolu)\**Action :** vérifier le DOCAC

**Portée :**
- Mettre à jour les informations de disponibilité (désormais pour tous les utilisateurs et utilisatrices de l’interface utilisateur web, et pas seulement pour la version 8.7)
- Limites de la langue du document
- Clarifier l’affichage des mesures en conflit avec les rapports hérités

**Description des fonctionnalités :**
Le reporting dynamique est désormais disponible pour tous les utilisateurs de l’interface utilisateur web de Campaign (auparavant limitée à 8,7 ACS pour les clients ACC). Il fournit des fonctionnalités d’analyse avancées et de reporting personnalisé avec une interface de style ACS.

**Context:** Extension de fonctionnalités, dépendance de création du serveur principal (8.8.1)

**Références:** [Wiki - Comparaison des rapports](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

&#x200B;---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - Test A/B&#x200B;**Statut :** En Cours\**Document requis :** Oui\**Existant DOCAC:** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104) (Nouveau)\**Action :** mettre à jour DOCAC

**Portée :**
- Documentation complète sur les workflows de test A/B
- Configuration de l’expérimentation de contenu et configuration des variantes
- Définition de la proportion d’échantillon et critères de sélection du gagnant
- Collecte et évaluation de statistiques

**Description des fonctionnalités :**
L’expérimentation de contenu et les tests A/B pour les diffusions par e-mail, ce qui permet aux spécialistes marketing de tester différentes variantes de contenu, de définir des tailles d’échantillon, de collecter des statistiques de performances et d’envoyer automatiquement la variante gagnante aux destinataires restants.

**Contexte : projet Europa**, exigence de Microsoft, indicateur de fonctionnalité activé

**Références :** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [Figma se moque de lui](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

&#x200B;---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126) - Création de schémas (création d&#39;une table, extension de schémas, accès à une base de données externe)**Statut :** En Cours\**Document requis :** Oui\**Existant DOCAC:** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826) (Nouveau)\**Action :** mettre à jour DOCAC

**Portée :**
- Workflow de création de schéma de document (3 options uniquement : créer une table, étendre le schéma, accéder à une base de données externe)
- Définition du formulaire pour les entités personnalisées
- Navigation et opérations CRUD sur les schémas personnalisés
- Fonctionnalités des phases 2 et 3

**Description des fonctionnalités :**
Les fonctionnalités de création de schémas de l’interface utilisateur web permettent aux administrateurs de créer des tables de base de données, d’étendre les schémas existants avec des champs personnalisés et de se connecter à des bases de données externes, ce qui est essentiel pour la personnalisation des modèles de données.

**Contexte :** des exigences de Microsoft, projet Europa, diffusion échelonnée (Phase 2 active, Phase 3 fin février)

**Références :** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [Figma](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

&#x200B;---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) - Web Analytics&#x200B;**Statut :** Nouveau\**Document requis :** Oui\**Existing DOCAC:** None\**Action :** Créer un DOCAC

**Portée :**
- Configuration du compte externe Web Analytics
- Configuration et authentification de l’intégration
- Utilisation des données Analytics dans les campagnes

**Description des fonctionnalités :**
Intégration de Web Analytics permettant la connexion aux plateformes de Web Analytics pour le suivi et le compte rendu des performances des campagnes et du comportement des visiteurs du site Web.

**Contexte :** demande du client (P2E-RSC), disponibilité de l’environnement en attente

**Références:** Aucune donnée fournie

&#x200B;---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753) - Intégration d’AEM pour les Live Copies/copies de langue&#x200B;**Statut :** Nouveau\**Document requis :** Oui\**Existing DOCAC:** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829) (Résolu)\**Action :** vérifier le DOCAC

**Portée :**
- Parcourir les modèles de diffusion AEM
- Création de Live Copies et de copies de langue en un seul clic
- Workflow de création de variantes de contenu multilingue

**Description des fonctionnalités :**
Intégration rationalisée d’AEM permettant la création en un clic de Live Copies et de copies de langue à partir de modèles de diffusion AEM, ce qui simplifie la création de campagnes multilingues pour les utilisateurs d’AEM.

**Contexte :** exigence de Microsoft, travail transféré à l&#39;équipe de Himanshu

**Références :** [Documentation ACS](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html?lang=fr)

&#x200B;---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) - Éditeur de contenu : utilisez des variables de thème dans le fragment&#x200B;**Statut :** Nouveau\**Document requis :** Oui\**Existant DOCAC:** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941) (Nouveau)\**Action :** mettre à jour DOCAC

**Portée :**
- Variables de thème dans le concepteur d’e-mail (Beta)
- Utilisation des thèmes dans les fragments
- Activation de la fonctionnalité Acrite

**Description des fonctionnalités :**
Prise en charge de l’utilisation de variables de thème dans les fragments de contenu, permettant une application système de marque et de conception cohérente sur les composants d’e-mail avec une gestion centralisée des thèmes.

**Context:** En attente, Fonction Acrite à revoir

**Références:** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

&#x200B;---

## ➕ Créer un DOCAC (améliorations)

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) - Filtres prédéfinis - Option partagée&#x200B;**Statut:** Résolu\**Document requis :** Oui\**DOCAC existant :** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697) (Révision du code), [DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522) (Fermé - Assistant)\**Action :** vérifier le DOCAC

**Portée :**
- Option partagée pour les filtres prédéfinis
- Filtrer la visibilité avec les autres opérateurs (ACC vs comportement de Parcours de la marque)
- Gestion des utilisateurs des filtres partagés

**Description des fonctionnalités :**
Les filtres prédéfinis peuvent désormais être marqués comme « partagés » pour les rendre visibles par les autres opérateurs, avec un comportement différent pour ACC (par défaut) et Brand Parcours (filtrage spécifique à l’utilisateur).

**Contexte :** amélioration du créateur de règles, indicateur de fonctionnalité : enable-query-filter-shared

**Références :** liées à [NEO-88441](https://jira.corp.adobe.com/browse/NEO-88441)

&#x200B;---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) - Activité de diffusion au fil de l&#39;eau&#x200B;**Statut :** Résolu\**Document requis :** Oui\**DOCAC existant :** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586) (nouveau), [DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808) (fermé - aide contextuelle)\**Action :** mettre à jour DOCAC

**Portée :**
- Activité de workflow de diffusion au fil de l’eau
- Configuration du sélecteur de modèle de diffusion
- Génération automatique de la transition sortante
- Options de ciblage (pas d&#39;accès au contenu)

**Description des fonctionnalités :**
L’activité de diffusion continue pour les workflows permet l’exécution récurrente de diffusions à partir de modèles, générant automatiquement des transitions sortantes pour l’orchestration des workflows sans modification de contenu.

**Context:** Indicateur de fonctionnalité : activer-la-diffusion-continue

**Références :** épique connexe [NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

&#x200B;---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130) - Activer le chargement de fichier prêt à l’emploi pour les notifications push multilingues&#x200B;**Statut :** Résolu\**Document requis :** Oui\**Existant DOCAC:** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606) (Nouveau)\**Action :** mettre à jour DOCAC

**Portée :**
- Chargement de fichier pour les notifications push multilingues (iOS et Android)
- Format CSV et mappage des champs
- Prise en charge complète des notifications push avec des fonctionnalités multilingues

**Description des fonctionnalités :**
Fonctionnalité de chargement de fichiers prête à l’emploi pour créer des diffusions de notifications push multilingues via l’importation de fichiers CSV, les fonctionnalités ACS correspondantes et la configuration efficace de campagnes multilingues.

**Contexte :** piloté par le client (H&amp;M), parité ACS vers ACC, critique pour la migration

**Références :** [Documentation ACS](https://experienceleague.adobe.com/fr/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

&#x200B;---

## ❌ Annulée / Ne S&#39;Applique Plus

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566) - Prise en charge du suivi CTA dans l’interface utilisateur web&#x200B;**Statut :** Fermé (Ne S’Applique Plus)\**Document requis :** Non\**Existant DOCAC:** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821) (Nouveau)\**Action :** Fermer DOCAC

**Raison :** nouvelle fonctionnalité ACS pour la prise en charge de MSFT - non démarrée, informations en attente de MSFT, aucun travail d’interface utilisateur attendu

**Context :** spécifique à Microsoft, exigence de suivi de CTA

&#x200B;---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564) - Prise en charge de l’interface utilisateur multilingue d’AEM&#x200B;**Statut :** Fermé (Ne S’Applique Plus)\**Document requis :** Non\**Existant DOCAC:** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822) (Nouveau)\**Action :** Fermer DOCAC

**Raison :** travail de l&#39;interface utilisateur géré par l&#39;équipe d&#39;Himanshu (autre histoire)

**Contexte : exigence de Microsoft**, travail transféré

&#x200B;---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) - Ajout de la prise en charge de la fonctionnalité NRT&#x200B;**Statut :** Résolu (Ne S’Applique Plus)\**Document requis :** Non\**Existant DOCAC:** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824) (Nouveau)\**Action :** Fermer DOCAC

**Raison :** nouvelle fonctionnalité ACS spécifique à MSFT - spécification disponible, mais aucun impact sur l’interface utilisateur web

**Context:** exigences de Microsoft, messagerie transactionnelle

&#x200B;---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563) - API Rest transactionnel pour l’enrichissement basé sur les profils&#x200B;**Statut :** Résolu (Ne S’Applique Plus)\**Document requis :** Non\**Existant DOCAC:** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825) (Nouveau)\**Action :** Fermer DOCAC

**Raison :**’interface utilisateur web ne fonctionne pas, instance mise à niveau en attente, mise à niveau de build obligatoire pour la publication

Fonction de point d’entrée de l’API REST **Context:**

&#x200B;---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) - Messagerie Transactionnelle D&#39;Enrichissement Basée Sur Profil - Phase 2&#x200B;**Statut :** Résolu (Ne S’Applique Plus)\**Document requis :** Non\**Existant DOCAC:** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823) (Nouveau)\**Action :** Fermer DOCAC

**Raison :** l&#39;histoire ne comporte aucune tâche, marquée comme « ne s&#39;applique plus »

**Contexte :** Microsoft requise, projet Europa

&#x200B;---

## 🟢 Documentation prête (à partir de AC-UI-25-11)

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) - Envoi enrichi multilingue - Interface utilisateur&#x200B;**Statut :** Résolu\**Document requis :** Oui\**Existant DOCAC:** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565) (Nouveau)\**Action :** vérifier le DOCAC

**Portée :**
- Champs push riches pour les diffusions multilingues
- Prise en charge des plateformes iOS et Android
- Configuration des modèles et du contenu

**Description des fonctionnalités :**
Prise en charge des notifications push enrichies avec des fonctionnalités multilingues, ce qui permet aux spécialistes marketing de créer des notifications push améliorées avec des images, des boutons et des médias riches pour iOS et Android dans plusieurs langues.

**Contexte :** axé sur le client (H&amp;M), fourni dans la version 25-11, travail principal terminé

**Références:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

&#x200B;---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916) - Configurer et gérer le processus de validation&#x200B;**Statut:** Résolu\**Document requis :** Oui\**Existant DOCAC:** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827) (Nouveau)\**Action :** mettre à jour DOCAC

**Portée :**
- Configuration des opérateurs de validation dans les diffusions/campagnes
- Paramétrage du workflow d&#39;approbation
- Processus de validation du contenu et de la cible
- Prise en charge multicanal (e-mail, SMS, notification push, courrier, centre d’appel, personnalisé)

**Description des fonctionnalités :**
Gestion des processus de validation permettant les workflows de validation du contenu et du ciblage des diffusions, avec affectation des opérateurs et suivi des validations sur tous les canaux de diffusion.

**Contexte :** piloté par le client (Pierre Fabre), exigence de Microsoft, développement terminé et en test

**Références :** [Documentation classique](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [Simulations Figma](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

&#x200B;---

## Résumé 📊 par action

| Action | Count |
|--------|-------|
| 🟢 Créer un DOCAC | 3 |
| 🔄 Update DOCAC | 6 |
| ✅ Revue DOCAC | 3 |
| ❌ Fermer DOCAC | 5 |
| **Total** | **17** |

&#x200B;---

## ⚠️ questions ouvertes

1. NEO-93487 - Escalade H&amp;M - nécessite une attention urgente pour la planification du processus de calcul
2. NEO-92668 - Web Analytics - en attente de disponibilité de l’environnement avant de pouvoir terminer la documentation
3. NEO-76126 - Schémas Phase 3 - ETA Fin février, une histoire de documentation distincte est nécessaire
4. NEO-88838 - Variables du thème - En attente de la révision de la fonctionnalité Acrite
5. Rapports dynamiques : clarifiez les mesures en conflit et donnez des conseils sur les rapports hérités

&#x200B;---

## 🔗 Epics connexes

- NEO-85263 - Épique parent ACS to ACC (EUROPA)
- NEO-67972 - Améliorations apportées aux workflows
- NEO-87980 - Intégration avancée d’AEM
- NEO-90199 - Préparation à la publication de rapports dynamiques
- NEO-63067 - UX/UI d’expérimentation de contenu
- NEO-67726 - Tests A/B et expérimentation de contenu
- NEO-85274 - Schéma et formulaire (Phase 2)
- NEO-87993 - Schéma et formulaire (Phase 3)
