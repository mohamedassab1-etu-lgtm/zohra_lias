# 🎓 Guide de Présentation Orale du Projet LIAS (10 à 15 minutes)
### Application Web de Gestion Intégrée et Gouvernance Institutionnelle
**Laboratoire d’Intelligence Artificielle et Systèmes (LIAS) — Faculté des Sciences Ben M’Sik (Casablanca)**
*Master Data Science & Big Data — Projet d'Ingénierie JEE*

---

## ⏱️ Chronogramme de la Présentation (Total : ~12 à 14 minutes)

| Temps | Phase | Rôle / Compte utilisé | Pages & Démonstration | Objectif clé |
| :---: | :--- | :--- | :--- | :--- |
| **00:00 - 01:30** | **1. Introduction & Architecture** | *Diapositive / Page d'accueil* | Présentation globale | Poser le cadre métier et l'architecture technique |
| **01:30 - 03:00** | **2. Vitrine Publique & Adhésion** | *Visiteur (Non connecté)* | `/`, `/equipes`, `/publications`, `/adhesion` | Respect de la vie privée + Candidature externe |
| **03:00 - 05:30** | **3. Espace Chercheur & Sécurité** | `dr.benjelloun@lias.ma` puis `doctorant.karimi@lias.ma` | `/dashboard`, `/publications-gestion`, `/mes-demandes-materiel` | Gestion de recherche + Cloisonnement strict Doctorant |
| **05:30 - 08:30** | **4. Gouvernance & Décisions Direction** | `directeur@lias.ma` | `/gouvernance/adhesions`, `/gouvernance/materiel`, `/gouvernance/equipes`, `/gouvernance/mandats` | Validation adhésion, attribution matériel, mutation équipe, règle d'unicité |
| **08:30 - 10:30** | **5. Logistique, GED & Rapport Annuel** | `directeur@lias.ma` | `/materiel`, `/reunions`, `/documents`, `/gouvernance/rapport-annuel` | Cycle de vie PV, Versioning GED, Génération & PDF Rapport |
| **10:30 - 12:00** | **6. Notifications, Admin & Audit** | `admin@lias.ma` | `/notifications`, `/admin/audit`, `/admin/comptes` | WebSocket, Emails asynchrones, Traçabilité infalsifiable |
| **12:00 - 14:00** | **7. Conclusion & Questions** | *Tous* | Échange avec le professeur | Valorisation des exigences du cahier des charges |

---

## 🔑 Aide-Mémoire Rapide des Comptes de Démonstration

> **Mot de passe unique pour tous les comptes :** `Password123!`

* **Directeur du Laboratoire :** `directeur@lias.ma` (Pr. Karim Bennani)
* **Membre Permanent :** `dr.benjelloun@lias.ma` (Dr. Fatima-Zahra Benjelloun)
* **Doctorant (Accès restreint) :** `doctorant.karimi@lias.ma` (Yassine Karimi)
* **Chef d'Équipe :** `prof.alami@lias.ma` (Pr. Mohamed Alami)
* **Membre Associé :** `associe.dupont@univ-paris.fr` (Pr. Jean-Pierre Dupont)
* **Administrateur Système :** `admin@lias.ma` (Compte technique)

---

## 🎬 Déroulé Pas à Pas de la Présentation

---

### PHASE 1 : Introduction & Enjeux du Système (1 min 30)
**Où se positionner :** Sur la page d'accueil `http://localhost:5173/`.

#### Ce que vous dites au professeur :
> *"Monsieur le Professeur, nous avons l'honneur de vous présenter la plateforme officielle de gestion et de gouvernance du **Laboratoire d’Intelligence Artificielle et Systèmes (LIAS)** de notre Faculté des Sciences Ben M’Sik.*
>
> *Le laboratoire faisait face à trois défis majeurs :*
> 1. *L'absence de centralisation de la production scientifique et des équipements.*
> 2. *La nécessité absolue de conserver la **mémoire institutionnelle** : conformément au cahier des charges, **aucune donnée n'est jamais supprimée** ; tout est historisé (affiliations, rôles, mandats).*
> 3. *La production automatisée du **Rapport Annuel d'Activité**, condition indispensable pour l'obtention des dotations budgétaires ministérielles.*
>
> *Côté technique, l'application repose sur une architecture robuste : **Spring Boot 3** en backend avec Spring Security (JWT sans état), JPA/Hibernate, messagerie temps réel **WebSocket STOMP**, notifications emails asynchrones (`@Async`), et un frontend moderne et réactif en **React 18 / TypeScript** stylisé avec TailwindCSS."*

---

### PHASE 2 : Portail Public & Soumission d'Adhésion (1 min 30)
**Acteur :** Visiteur externe (aucun compte connecté).

#### Actions à réaliser :
1. **Montrer la page d'accueil (`/`) :**
   * Pointer du curseur le nom complet officiel : *"Laboratoire d’Intelligence Artificielle et Systèmes"*.
   * Montrer les compteurs dynamiques (Membres, Équipes, Publications).
2. **Cliquer sur "Équipes" (`/equipes`) puis "Publications" (`/publications`) :**
   * *Ce que vous dites :* *"Le grand public et les partenaires peuvent consulter les axes de recherche et les travaux publiés sans authentification. Toutefois, pour respecter la vie privée des chercheurs, aucune donnée personnelle sensible (comme la date de naissance ou l'annuaire interne) n'est divulguée."*
3. **Cliquer sur "Adhésion" (`/adhesion`) :**
   * Montrer le formulaire de candidature externe.
   * Remplir rapidement les champs :
     * Nom : `El Mansouri` / Prénom : `Tariq`
     * Email : `tariq.candidat@gmail.com`
     * Statut souhaité : `Membre permanent`
     * Établissement : `Faculté des Sciences Ben M'Sik`
     * Motivation : `Projet de recherche sur les modèles génératifs de vision.`
     * Téléverser un CV (fichier PDF).
   * Cliquer sur **"Soumettre ma candidature"**.
   * *Ce que vous dites :* *"Le candidat externe postule directement en ligne. La demande est persistée à l'état EN_ATTENTE et déclenche une notification instantanée pour la Direction. Le compte n'est pas encore créé."*

---

### PHASE 3 : Espace Chercheur & Cloisonnement Strict des Rôles (2 min 30)

#### A. Connexion Chercheur Permanent
**Acteur :** `dr.benjelloun@lias.ma` / `Password123!`

1. Aller sur `/login`, se connecter avec `dr.benjelloun@lias.ma`.
2. L'application redirige automatiquement vers le **Tableau de Bord Membre** (`/dashboard`).
3. **Déclarer une publication (`/publications-gestion`) :**
   * Cliquer sur **"Ajouter une publication"**.
   * Expliquer au professeur la gestion fine des co-auteurs internes (sélectionnés parmi les membres) et externes (saisie libre), ainsi que le rattachement optionnel à une convention.
   * Saisir un DOI déjà existant pour montrer au professeur la **détection immédiate des doublons par DOI**.
4. **Soumettre un besoin de matériel (`/mes-demandes-materiel`) :**
   * Cliquer sur **"Nouvelle demande"**.
   * Description : `Station GPU pour entraînement de modèles de segmentation médicale.`
   * Quantité : `1` -> Cliquer sur **"Envoyer"**.
   * Montrer la demande qui apparaît avec le badge jaune `EN_ATTENTE`.

#### B. La Preuve du Cloisonnement de Sécurité (Doctorant)
**Acteur :** Se déconnecter et se connecter avec `doctorant.karimi@lias.ma` / `Password123!`

1. Observer immédiatement la barre latérale :
   * *Ce que vous dites au professeur :* *"Regardez, Monsieur : le cahier des charges impose que le doctorant ne doit avoir accès à aucun module interne (ni réunions, ni matériel, ni documents, ni messagerie). Son menu est strictement isolé : uniquement ses Publications et son Profil."*
2. Taper manuellement dans l'URL du navigateur : `http://localhost:5173/materiel` ou `http://localhost:5173/gouvernance/adhesions`.
3. Appuyer sur `Entrée` :
   * Montrer la page **`403 - Accès Refusé`** gérée par le composant `ProtectedRoute`.
   * *Ce que vous dites :* *"Même en forçant l'URL, le système intercepte la requête côté frontend et côté Spring Security via les annotations `@PreAuthorize`."*

---

### PHASE 4 : Gouvernance, Décisions & Pilotage de la Direction (3 min)
**Acteur :** Se déconnecter et se connecter avec le **Directeur** : `directeur@lias.ma` / `Password123!`

1. **Tableau de Bord de Direction (`/dashboard`) :**
   * Montrer les alertes dynamiques : *Adhésions en attente*, *Besoins matériel à valider*, *Événements à valider*.
2. **Valider la Candidature d'Adhésion (`/gouvernance/adhesions`) :**
   * Ouvrir l'onglet *En attente*. Repérer la candidature de `Tariq El Mansouri` soumise à l'étape 2.
   * Cliquer sur **"Consulter le dossier"**, montrer le téléchargement immédiat du CV PDF.
   * Cliquer sur le bouton vert **"Accepter"**.
   * *Ce que vous dites :* *"En acceptant, le système crée le compte utilisateur, initialise son statut, génère un mot de passe temporaire et ouvre officiellement sa première période d'affiliation avec la date du jour."*
3. **Valider la Demande de Matériel (`/gouvernance/materiel`) :**
   * Repérer la demande de station GPU soumise par Dr. Benjelloun.
   * Cliquer sur **"Valider la demande"**.
   * Sélectionner dans la liste déroulante la station en stock à lui allouer.
   * Valider : montrer que le stock disponible diminue automatiquement et que l'attribution est inscrite à l'historique du matériel.
4. **Gestion des Équipes & Mutations (`/gouvernance/equipes`) :**
   * *Ce que vous dites :* *"Voici notre module de gestion des équipes de recherche :"*
   * **Changer de chef d'équipe :** Cliquer sur *"Changer le chef"* sur une équipe. Montrer au professeur que la liste déroulante **ne propose que des membres appartenant déjà à cette équipe**.
   * **Affectation directe d'un membre :** Cliquer sur *"Affecter un membre directement"*. Montrer qu'on peut déplacer un membre d'une équipe vers une autre, ou l'assigner s'il n'avait aucune équipe.
   * **Traitement des demandes de mutation :** Ouvrir l'onglet *"Demandes de changement"* pour montrer les demandes soumises par les membres et leur acceptation/refus avec motif.
5. **Gestion des Mandats (`/gouvernance/mandats`) :**
   * Montrer la frise chronologique de gouvernance.
   * *Ce que vous dites :* *"Le système applique la règle d'unicité : un seul Directeur en mandat actif. De plus, nous avons implémenté la délégation pour le **Vice-Directeur** : il possède tous les pouvoirs opérationnels de direction, mais le système lui interdit d'attribuer de nouveaux mandats pour protéger la gouvernance."*

---

### PHASE 5 : Logistique, Réunions & Rapport Annuel d'Activité (2 min)

1. **Inventaire du Matériel & Équité (`/materiel`) :**
   * Montrer la vue croisée *"Qui a reçu quoi"* et surtout le filtre d'équité **"Qui n'a pas reçu"** exigé par le cahier des charges pour éviter les déséquilibres d'attribution entre chercheurs.
2. **Réunions & Procès-Verbaux (`/reunions`) :**
   * Expliquer le cycle de vie : `PLANIFIEE` (ordre du jour modifiable) -> `EN_ATTENTE_PV` -> dépôt du fichier PDF -> bascule irréversible à l'état `ARCHIVEE` en lecture seule.
3. **Le Rapport Annuel d'Activité (`/gouvernance/rapport-annuel`) — LE CLIMAX DE LA DÉMO :**
   * Choisir l'année `2026`.
   * **Montrer la logique conditionnelle :**
     * Si le rapport n'était pas généré : seul le bouton bleu *"Générer le rapport"* est visible.
     * Une fois généré : un bouton unique *"Régénérer le rapport"* et un bouton unique *"Télécharger le PDF"* apparaissent.
   * Faire défiler le rapport à l'écran :
     * Pointer le **nom officiel complet** : *"Laboratoire d’Intelligence Artificielle et Systèmes"*.
     * Montrer la **composition détaillée des équipes** : chaque équipe liste ses membres, leurs rôles et leurs dates d'affiliation.
     * Montrer les **statuts en français lisible** (*En préparation*, *Validé*, *Planifiée*) : **aucun code enum brut de base de données**.
   * Cliquer sur **"Télécharger le PDF"** :
     * Ouvrir le fichier PDF téléchargé devant le professeur.
     * Montrer le **logo officiel du LIAS**, l'en-tête académique de la Faculté des Sciences Ben M'Sik et la mise en page fidèle au design de l'application.
     * *Ce que vous dites :* *"Ce document officiel est conforme aux exigences de l'Université pour le déblocage du budget annuel du laboratoire."*

---

### PHASE 6 : Notifications Temps Réel, Admin & Traçabilité (1 min 30)

1. **Système de Notifications Avancé :**
   * Cliquer sur la **cloche** dans la barre de navigation :
     * Montrer le compteur dynamique d'alertes non lues.
     * Montrer qu'**un clic sur n'importe quelle notification redirige instantanément vers la ressource associée** (dossier matériel, événement, équipe) et la marque immédiatement comme lue.
   * Ouvrir le Centre de notifications (`/notifications`) : montrer les onglets de filtrage par catégorie (*Événements, Matériel, Mandats, Réunions...*).
   * Préciser que chaque notification interne est doublée d'un **email officiel HTML** expédié de manière asynchrone (`@Async`) avec bouton d'accès direct.
2. **Administration & Journal d'Audit (`/admin/audit`) :**
   * Se connecter en tant qu'administrateur (`admin@lias.ma`).
   * Ouvrir le **Journal d'Audit Système** :
     * Montrer que l'acceptation de la candidature, l'attribution du matériel et le changement de chef effectués pendant votre démo sont tracés chronologiquement avec l'email de l'auteur, l'adresse IP et l'action exacte.
   * Montrer dans `/gouvernance/departs` la gestion du cycle de vie :
     * La différence entre un membre **Retraité** (compte `GELE` définitivement) et un **Ancien membre** (compte `DESACTIVE`, réactivable lors d'un retour au laboratoire avec ouverture d'une nouvelle période).

---

### PHASE 7 : Conclusion & Synthèse (1 minute)

#### Ce que vous dites pour conclure :
> *"Pour conclure, ce projet ne se limite pas à un simple CRUD. Il matérialise fidèlement toutes les exigences académiques et réglementaires du laboratoire LIAS :*
> * Une **sécurité applicative sans faille** basée sur les rôles et mandats.
> * Une **mémoire institutionnelle préservée** grâce à l'interdiction de suppression physique et à l'historisation temporelle.
> * Une **automatisation complète du rapport annuel d'activité** au format PDF.
> * Une **ergonomie moderne** avec mises à jour temps réel par WebSocket et alertes par emails.
>
> *Nous vous remercions pour votre attention et sommes à votre entière disposition pour vos questions."*

---

## 🎯 Réponses aux Questions Probables du Professeur

### Q1 : *"Pourquoi avoir séparé Statut et Mandat/Rôle ?"*
> **Réponse :** *"Parce qu'un enseignant-chercheur a un **Statut** permanent qui ne change pas (Permanent, Associé, Doctorant), tandis qu'un **Mandat** (Directeur, Chef d'équipe) est une responsabilité temporaire limitée dans le temps. Séparer les deux entités permet de nommer un nouveau chef d'équipe ou de changer de directeur sans altérer le statut contractuel du membre ni perdre l'historique de ses mandats passés."*

### Q2 : *"Comment avez-vous géré la non-suppression des données (Soft Delete) ?"*
> **Réponse :** *"Toutes nos entités héritent de `EntiteAuditable`. Les comptes passent par des états (`ACTIF`, `GELE`, `DESACTIVE`), les équipes et réunions basculent à l'état `ARCHIVE`, et les périodes d'affiliation ou de mandats se voient attribuer une `dateFin`. Hibernate applique des filtres `@SQLRestriction("archive = false")` pour l'affichage courant, tout en permettant aux modules d'historique d'accéder à l'intégralité des données passées."*

### Q3 : *"Comment fonctionne la génération du Rapport Annuel ?"*
> **Réponse :** *"Notre service `RapportService` agrège en une seule transaction toutes les données de l'année sélectionnée : composition des équipes, publications enregistrées, événements et réunions clôturées, arrivages de matériel et conventions actives. Les données sont formatées avec des libellés humains (sans enums), puis converties en un document PDF professionnel grâce à iText / OpenPDF intégrant le logo officiel du laboratoire."*

### Q4 : *"Comment sont gérées les performances pour les emails et les notifications ?"*
> **Réponse :** *"Les notifications sont diffusées instantanément aux clients connectés via **WebSocket STOMP**. En parallèle, l'envoi d'emails vers le serveur SMTP s'exécute dans un thread séparé grâce à l'annotation Spring `@Async`, ce qui garantit un temps de réponse inférieur à 50ms pour l'utilisateur sur le frontend."*

---

## 💡 Conseils Pratiques pour le Jour J
1. **Lancer les serveurs à l'avance :**
   * Backend : `./mvnw spring-boot:run` (port 8080).
   * Frontend : `npm run dev` (port 5173).
2. **Ouvrir 2 navigateurs différents :**
   * Un navigateur principal (ex: Chrome) pour le Directeur / Admin.
   * Une fenêtre en navigation privée (ou Firefox) pour le Doctorant ou le Candidat externe. Cela évite de devoir se reconnecter constamment et permet de montrer les interactions en temps réel !
3. **Rester calme et confiant :** Tout le code a été vérifié et compilé avec succès (`BUILD SUCCESS`, 0 erreur frontend et backend). Suivez simplement le script !
