# QuizMaster

QuizMaster est une plateforme de quiz complète et interactive. Elle permet aux utilisateurs de jouer à des quiz, de créer leurs propres quiz, et de défier leurs amis dans des duels en temps réel. Le projet inclut également un panneau d'administration robustre pour une gestion facile du contenu et des utilisateurs.

## 🚀 Fonctionnalités

### Côté Client (Joueur)
* Accès à un large catalogue de quiz par catégories
* Système de jeu interactif avec soumission de réponses
* Création de compte utilisateur, connexion et gestion de profil
* Système de duels 1v1 :
    * Envoyer et recevoir des invitations
    * Jouer des quiz en temps réel contre un adversaire
    * Historique des duels et classement (leaderboard)
* Création de quiz par la communauté
* Système de notifications (invitations de duel, résultats, etc.)
* Suivi de la progression et des scores

### Côté Administration
* Tableau de bord avec vue d'ensemble de l'activité
* Gestion complète des quiz (CRUD, importation)
* Gestion des catégories de quiz (CRUD)
* Gestion des utilisateurs (CRUD, voir les profils)
* Suivi et administration des duels en cours
* Consultation des statistiques de la plateforme

## 💻 Technologies utilisées

* **Backend**: PHP natif
* **Frontend**: HTML, CSS, JavaScript (avec AJAX pour les fonctionnalités dynamiques)
* **Base de données**: MySQL
* **Dépendances (via Composer)**:
    * `mpdf/mpdf`: Pour la génération de documents PDF (potentiellement pour les résultats ou rapports).
    * `setasign/fpdi`: Pour l'importation de templates PDF.

## ⚙️ Prérequis

* PHP 7.4 ou supérieur
* MySQL 5.7 ou supérieur
* Serveur web (Apache, Nginx)
* [Composer](https://getcomposer.org/) pour la gestion des dépendances

## 📋 Installation

### 1. Configuration de la base de données
1.  Créez une base de données MySQL (par exemple `quizmaster`).
2.  Importez le fichier SQL fourni pour créer la structure des tables :
    ```bash
    mysql -u [utilisateur] -p quizmaster < quizmaster.sql
    ```
    *(Utilisez `quizmaster.sql` ou `dump.sql`)*
3.  Configurez vos informations de connexion à la base de données dans le fichier `includes/db.php`.

### 2. Installation des dépendances
Placez-vous à la racine du projet et exécutez Composer :
```bash
composer install
```

Cela installera mpdf et les autres dépendances nécessaires.

3. Configuration du serveur
Assurez-vous que votre serveur web (Apache, etc.) pointe vers le répertoire racine du projet.
4. Lancement de l'application
Accédez au site via votre navigateur à l'adresse configurée (ex: `http://localhost/quizmaster`).
Pour le panneau d'administration, naviguez vers `/admin`.
5. Compte administrateur
Utilisez les identifiants par défaut (s'ils sont définis dans le `.sql`) ou créez un compte administrateur manuellement.

## 📁 Structure du projet

quizmaster/
├── admin/                  # Panneau d'administration
│   ├── categories/         # CRUD pour les catégories
│   ├── creation/           # Outils de création admin
│   ├── duels/              # Gestion des duels
│   ├── includes/           # Header, footer, sidebar admin
│   ├── quiz/               # CRUD pour les quiz
│   ├── stats/              # Page de statistiques
│   ├── users/              # CRUD pour les utilisateurs
│   ├── index.php           # Tableau de bord admin
│   └── login.php           # Connexion admin
│
├── api/                    # API pour les requêtes asynchrones
│   ├── check_duel_status.php
│   ├── complete_duel.php
│   └── submit_duel_answer.php
│
├── assets/                 # Ressources statiques (CSS, JS, Images)
│   ├── css/
│   ├── js/
│   └── images/
│
├── duels/                  # Logique et interface des duels
│   ├── accept_invitation.php
│   ├── challenge.php
│   ├── history.php
│   ├── leaderboard.php
│   ├── play.php
│   ├── results.php
│   └── index.php           # Hub des duels
│
├── includes/               # Fichiers PHP partagés
│   ├── config.php          # Configuration générale
│   ├── db.php              # Connexion à la base de données
│   ├── functions.php       # Fonctions utilitaires
│   ├── header.php          # En-tête du site
│   └── footer.php          # Pied de page du site
│
├── vendor/                 # Dépendances Composer
│   ├── mpdf/
│   ├── setasign/
│   └── autoload.php
│
├── categorie.php           # Page de visualisation des quiz par catégorie
├── community_quiz.php      # Page des quiz créés par les utilisateurs
├── connexion.php           # Page de connexion
├── create_quiz.php         # Formulaire de création de quiz
├── deconnexion.php         # Déconnexion de l'utilisateur
├── index.php               # Page d'accueil
├── inscription.php         # Page d'inscription
├── notifications.php       # Centre de notifications
├── profil.php              # Profil utilisateur
├── quiz.php                # Page de jeu d'un quiz
├── quizmaster.sql          # Fichier de structure de la base de données
├── composer.json           # Définition des dépendances
└── ... (et autres fichiers de la racine)

## 🔒 Sécurité (Bonnes pratiques visées)
Protection contre les injections SQL (utilisation de requêtes préparées)
Hachage sécurisé des mots de passe
Validation des entrées utilisateur côté client et serveur
Gestion des sessions sécurisée

## 📱 Compatibilité
Conçu pour être responsive et s'adapter aux ordinateurs de bureau, tablettes et mobiles.
Testé sur les navigateurs modernes (Chrome, Firefox, Safari, Edge).

## 🛠️ Personnalisation
Thème et apparence
Modifiez les styles globaux dans `assets/css/style.css`.
Modifiez les styles de l'administration dans `admin/assets/css/admin.css`.
Ajout de nouvelles fonctionnalités
Les fonctions globales peuvent être ajoutées dans `includes/functions.php`.
Les fonctions spécifiques à l'administration peuvent être ajoutées dans `admin/includes/functions.php`.

## 📞 Support et contact
Pour toute question ou assistance, veuillez me contacter :
Propriétaire du dépôt : binksterrel
Email : 43020094@parisnanterre.fr
Site web : http://localhost/quizmaster

## 📄 Licence

Ce projet est protégé par des droits d'auteur. Tous droits réservés.

--------

© 2025 QuizMaster. Tous droits réservés.
