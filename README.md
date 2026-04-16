Plan de travail structuré — Application de Gestion de Factures
Voici un plan complet, pensé pour 3 développeurs en DUT Informatique, avec une soutenance en ligne de mire.

🧭 Vue d'ensemble du projet
Avant de coder quoi que ce soit, il faut comprendre et modéliser le projet. C'est ce qui impressionne le plus un jury.
Ce que l'application doit faire (fonctionnalités core)

Créer / modifier / supprimer des factures
Gérer les clients et les produits
Calculer automatiquement les totaux, taxes, remises
Générer des factures en PDF
Tableau de bord avec statistiques (chiffre d'affaires, factures impayées…)
Historique et recherche de factures


👥 Répartition des rôles (3 développeurs)
DéveloppeurRôleResponsabilitésDev 1Chef de projet + BackendArchitecture, base de données, logique métier, algorithmesDev 2Frontend Desktop + WebInterface PyQt6 (PC), interface Web (Flask/FastAPI)Dev 3Frontend Mobile + TestsInterface mobile (Kivy/BeeWare), tests, documentation

Chacun documente son propre code et participe aux revues de code des autres.


🗓️ Plan en 5 phases (planning sur ~6 à 8 semaines)

📌 PHASE 1 — Analyse & Conception (Semaine 1)
"On ne code pas encore — on réfléchit"
Tous ensemble :

Rédiger le cahier des charges (liste précise des fonctionnalités)
Faire les maquettes UI/UX (Figma, gratuit et en ligne) pour les 3 versions
Modéliser la base de données → diagramme Entité-Relation (ER)
Écrire les algorithmes en pseudocode avant de coder (très important pour le prof)
Choisir les outils et la stack technique

Stack recommandée :
🖥️ Desktop   → Python + PyQt6 → PyInstaller (.exe)
🌐 Web       → Python + Flask ou FastAPI + HTML/CSS/JS
📱 Mobile    → Python + Kivy ou BeeWare (Toga)
🗄️ Base de données → SQLite (local) ou PostgreSQL
📄 PDF       → ReportLab ou WeasyPrint
Livrables de la phase :

 Cahier des charges rédigé
 Maquettes validées par le groupe
 Diagramme ER de la BDD
 Pseudocode des algorithmes principaux
 Dépôt Git créé (GitHub/GitLab) avec branches par dev


📌 PHASE 2 — Backend & Base de données (Semaines 2-3)
"Le moteur de l'application" — Dev 1 pilote, les autres contribuent
À construire :

Modèles de données (tables : Client, Produit, Facture, LigneFacture)
CRUD complet avec SQLite + SQLAlchemy (ORM Python)
Algorithmes de calcul : sous-total, TVA, remise, total TTC
Génération de PDF des factures
Module d'export (CSV, PDF)

Structure du projet recommandée :
factures_app/
│
├── core/               ← Logique métier (Backend)
│   ├── models.py       ← Classes & BDD
│   ├── database.py     ← Connexion SQLite
│   ├── factures.py     ← Algorithmes de calcul
│   └── pdf_export.py   ← Génération PDF
│
├── desktop/            ← Interface PC (Dev 2)
├── web/                ← Interface Web (Dev 2)
├── mobile/             ← Interface Mobile (Dev 3)
├── tests/              ← Tests unitaires (Dev 3)
├── docs/               ← Documentation
└── main.py
Livrables :

 Base de données fonctionnelle
 Toutes les fonctions CRUD testées
 Génération PDF opérationnelle


📌 PHASE 3 — Interfaces graphiques (Semaines 3-5)
"Ce que le jury voit en premier"
🖥️ Version Desktop (Dev 2) — PyQt6

Fenêtre principale avec menu latéral (sidebar)
Formulaires de création de facture avec validation
Tableau de bord avec graphiques (PyQtChart ou matplotlib)
Thème sombre/clair, couleurs professionnelles

🌐 Version Web (Dev 2) — Flask + Bootstrap 5

Interface responsive (s'adapte à tous les écrans)
Tableau de factures avec filtres et pagination
Formulaires dynamiques (JavaScript pour les calculs en temps réel)
Dashboard avec Chart.js

📱 Version Mobile (Dev 3) — Kivy

Navigation par onglets (Bottom Navigation)
Liste des factures avec swipe pour actions
Formulaire de création simplifié
Interface tactile (boutons larges, lisible sur petit écran)

Règles UI/UX à respecter :

Palette de couleurs cohérente sur les 3 versions (charte graphique)
Typographie lisible (titres, corps de texte)
Messages d'erreur clairs et feedback utilisateur
Icônes cohérentes (Font Awesome pour le web, icônes intégrées pour desktop)

Livrables :

 Les 3 interfaces connectées au backend
 Navigation complète et fonctionnelle
 Charte graphique appliquée


📌 PHASE 4 — Tests, Documentation & Packaging (Semaine 6)
"Ce qui sépare un projet scolaire d'un vrai produit"
Tests (Dev 3 pilote) :

Tests unitaires avec pytest sur toutes les fonctions du backend
Tests d'interface (vérifier que les boutons font ce qu'ils doivent)
Tests de cas limites (facture vide, montant nul, client inexistant…)

Documentation (tous) :
docs/
├── README.md           ← Présentation du projet, installation
├── algorithmes.md      ← Pseudocode + explication des algos
├── bdd.md              ← Schéma et description de la BDD
├── guide_utilisateur.md ← Manuel d'utilisation avec captures d'écran
└── api.md              ← Documentation des fonctions (si version Web)

Commenter chaque fonction avec des docstrings Python :

pythondef calculer_total(lignes: list, tva: float = 0.18) -> dict:
    """
    Calcule le total d'une facture avec TVA.

    Args:
        lignes (list): Liste des lignes de facture [{qte, prix_unitaire}]
        tva (float): Taux de TVA (défaut: 18%)

    Returns:
        dict: {"sous_total": float, "tva": float, "total_ttc": float}
    """
Packaging :

.exe Desktop → PyInstaller --onefile --windowed main_desktop.py
Web → déploiement sur Render.com ou PythonAnywhere (gratuit)
Mobile → .apk avec Buildozer (pour Kivy)


📌 PHASE 5 — Préparation de la soutenance (Semaine 7-8)
Support de présentation :

Slides de présentation (10-15 slides max) :

Présentation du projet & équipe
Analyse des besoins (cahier des charges)
Architecture technique
Démonstration en direct (les 3 versions)
Algorithmes clés expliqués
Base de données
Tests & qualité du code
Bilan & difficultés rencontrées



Répétition :

Chaque dev présente sa partie
Préparer des réponses aux questions classiques du jury
Faire une démo en conditions réelles (données de test réalistes)


🛠️ Outils de travail collaboratif
OutilUsageGitHubVersioning du code, branches par fonctionnalitéFigmaMaquettes UI/UX (gratuit)Trello ou NotionSuivi des tâches (Kanban)DiscordCommunication d'équipeDraw.ioDiagrammes ER, flowcharts

⚠️ Les erreurs à éviter absolument

❌ Commencer à coder sans maquette ni modèle de BDD
❌ Ne pas utiliser Git → impossibilité de collaborer
❌ Mélanger la logique métier et l'interface dans les mêmes fichiers
❌ Oublier les commentaires et docstrings en cours de route
❌ Faire les tests et la doc à la dernière minute
❌ Avoir 3 chartes graphiques différentes sur les 3 versions


✅ Checklist finale avant soutenance

 Les 3 versions fonctionnent sans bug visible
 La BDD est cohérente et documentée
 Chaque fonction a sa docstring
 Les algorithmes sont expliqués en pseudocode dans la doc
 Les tests passent tous
 La démo utilise des données réalistes
 Chaque membre maîtrise tout le projet, pas seulement sa partie
