# Systeme de Surveillance de Fichiers (File Change Tracker)-FCT
Ce projet est un système de surveillance de fichiers en C qui permet de suivre les modifications effectuées dans un répertoire spécifique. Il scanne périodiquement les fichiers et génère un rapport des modifications détectées (ajout, suppression ou changement de contenu).


⚙️ Fonctionnalités

    📂 Surveillance des fichiers : Scanne un dossier cible pour vérifier les changements des fichiers.

    🔍 Comparaison des fichiers : Vérifie le nom, la taille, la date de modification et génère un hash du contenu de chaque fichier.

    ⏰ Intervalle de surveillance : Le programme vérifie périodiquement (ex : toutes les 10 secondes).

    📊 Génération de rapport : En cas de modification, un rapport détaillé est écrit dans un fichier report.log.

    🛠️ Mode background : Le programme peut tourner en background comme un daemon.

    🔒 Sécurité : Détecte les changements non autorisés de fichiers importants.

🔑 Technologies utilisées

    Langage : C

    Bibliothèques :

        stdio.h : Pour la gestion des fichiers

        stdlib.h : Pour la gestion de la mémoire

        string.h : Pour les manipulations de chaînes de caractères

        time.h : Pour la gestion du temps

        openssl (ou autre lib de hachage) : Pour calculer les hash des fichiers

📑 Structure du projet

/FileChangeTracker
├── src/
│   ├── main.c              # Fonction principale
│   ├── file_utils.c        # Fonctions utilitaires pour la gestion des fichiers
│   ├── hashing.c           # Gestion des hash des fichiers
│   ├── log.c               # Gestion des logs
│   └── monitor.c           # Logique de surveillance des fichiers
├── include/
│   ├── file_utils.h        # Déclarations des fonctions de gestion des fichiers
│   ├── hashing.h           # Déclarations des fonctions de hachage
│   ├── log.h               # Déclarations des fonctions de log
│   └── monitor.h           # Déclarations des fonctions de surveillance
├── report.log              # Rapport des changements détectés
├── Makefile                # Fichier pour la compilation
└── README.md               # Ce fichier

🚀 Installation
Prérequis

    Un compilateur C (comme gcc)

    La bibliothèque OpenSSL (pour calculer les hash MD5/SHA1)

        Sur Linux : sudo apt-get install libssl-dev

Compilation

    Clonez ce dépôt :

git clone https://github.com/ton_nom_utilisateur/FileChangeTracker.git
cd FileChangeTracker

Compilez le projet avec Make :

    make

Utilisation

    Lancez le programme en ligne de commande :

./file_change_tracker /chemin/vers/dossier

Par exemple :

    ./file_change_tracker /var/log

    Le programme commence alors à surveiller les fichiers du dossier spécifié. En cas de modification, un rapport est généré dans le fichier report.log.

Exemple de rapport (report.log)

[2025-04-11 14:35:12] Modification détectée : fichier "test.txt"
  - Taille modifiée : 1024 octets
  - Hash avant modification : 123abc456def7890
  - Hash après modification : 0987abc654def3210

🎯 Objectifs futurs

    Ajouter une fonctionnalité d'envoi d'alertes par e-mail en cas de modification.

    Optimiser la gestion des erreurs et des cas particuliers.

    Ajouter une interface graphique (GUI) pour rendre l'outil plus interactif.

🤖 Contribuer

    Fork ce projet

    Crée une nouvelle branche (git checkout -b feature/ma-nouvelle-fonctionnalité)

    Fais tes modifications et commite (git commit -am 'Ajout d\'une fonctionnalité')

    Pousse la branche (git push origin feature/ma-nouvelle-fonctionnalité)

    Ouvre une pull request
