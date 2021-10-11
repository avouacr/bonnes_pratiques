# Bonnes pratiques pour projets de données

### 0. Introduction à la notion de bonnes pratiques

- Les bonnes pratiques : pour qui ? pour quoi ?
  - Le code comme outil de communication
    - pour soi dans le futur
    - pour les autres
  - L'enjeu de la reproductibilité
  - Pérennité
  - Evolutivité
- Un continuum de bonnes pratiques
  - Comment fixer le bon niveau ?
    - Ambitions du projet (état de l'existant, potentiel évolutif, potentiel collaboratif)
    - Ressources (moyens humain, temps, existence d'une communauté de contributeurs)
    - Contraintes (échéance, niveau de qualité attendu, mise en production, environnement d'exécution, enjeux de sécurité)
    - Socle minimal pour tout projet de données ?
  - Le bon curseur peut changer en fonction de l'évolution du projet

### 1. Qualité du code

- Principes généraux
  - Lisibilité (expressivité des nommages, simplicité,..)
  - Cohérence (consistency) et importance des conventions
  - Limiter la redondance => utilisation de fonctions
  - Documentation (commentaires, docstrings...)
- Standards communautaires de code
  - R : tidyverse / Google style guides
  - Python : PEP
- Utilisation d'analyseurs de code (formatters, linters)
- Relecture par un tiers / pair-programming

### 2. Structure des projets 

- Modularité
  - Découpage des scripts en fonctions 
  - Découpage des blocs du projet en modules
- Architectures de projets
  - Séparer stockage des données, stockage du code, environnement d'exécution
  - Plusieurs modèles possibles selon la taille du projet
    - input / traitement / output
    - Domain-driven design (data, domain, application, presentation)
    - etc..
  - Templates
    - R : RProjects
    - Python : cookiescutter
- Packages
  - Gestion des dépendances
  - Documentation
  - Logging
  - Tests unitaires
  - Publication
  - Maintenance

### 3. Contrôle de version

- Usage individuel
  - Pourquoi ?
    - Stockage du code sur un serveur distant => perte impossible
    - Historique complet des choix effectués tout au long du projet
    - Possibilité de revenir à n'importe quelle version du projet
    - Pratique du contrôle de version en vue d'un usage collaboratif
    - Vitrine des projets effectués
  - Principes
    - git repository
    - origin
    - git workflow
    - .gitignore
  - Outils graphiques
    - Intégration R Studio
    - Plugin Jupyter-git
    - Intégration VSCode
  - Utilisation en ligne de commandes
- Usage collaboratif
  - Pourquoi ?
    - Tous les avantages de l'usage individuel dans un cadre collaboratif
    - Git est distribué => multiple backups d'un projet
    - Travail simultané sur les mêmes fichiers sans risque de perte
    - Outil de référence dans l'environnement open-source
  - Collaboration en équipe
    - Branches
    - Différents workflows possibles selon les spécificités du projet
  - Ouverture à des contributions externes
    - CONTRIBUTING file
    - Issues
    - Forks / Pull Requests

### 4. Environnements d'exécution 

- Principes du développement logiciel pour favoriser la reproductibilité
  - Isolation
  - Portabilité
- Gestion des dépendances avancée
  - Dépendances dans le langage du projet
  - Dépendances dans d'autres langage
  - Adhérence à l'OS d'exécution (librairies, package manager...)
  - Conflits de version (interpréteur, dépendances, librairies)
- Environnements virtuels
  - Avantages
    - Isolation du projet
    - Relative simplicité d'utilisation
  - Limites
    - Gestion des dépendances *spécifiques* au langage du projet => portabilité limitée
  - Implémentations
    - R : renv
    - Python : venv, conda
- Conteneurisation
  - Avantages
    - Isolation complète du projet (toutes dépendances, librairies externes, OS d'exécution...)
    - Portabilité totale
  - Limites
    - Rend la phase de développement un peu lourde
  - Implémentations
    - Docker

### 5. Mise en production

- Mise en prod grandement facilitée si toutes les étapes précédentes ont été appliquées
- Déploiement
  - Environnement de production
  - Pipeline de transformations : DAG
- CI/CD

### 6. Notions avancées

- Tests avancés
- Versioning avancé : data version control, MLFlow...
- Optimisation de performance
  - *Sin of early optimisation*
  - Profiling
  - Ressources
    - R : Advanced R, R inferno
    - Python : High Performance Python
- Enjeux de sécurité
