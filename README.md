# 🎓 SclayInTouch

![PHP](https://img.shields.io/badge/PHP-8.0%2B-777BB4?style=for-the-badge&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)
![Status](https://img.shields.io/badge/Status-MVP%20Functional-success?style=for-the-badge)

> **SclayInTouch** est un réseau social universitaire conçu pour connecter les étudiants entre eux. Développé en PHP natif, ce projet met l'accent sur une architecture modulaire et une gestion optimisée des ressources.

---

## 🚀 Fonctionnalités Clés

### 👤 Gestion Utilisateur
* **Inscription & Connexion :** Système sécurisé avec vérification des champs et gestion des erreurs.
* **Profils Personnalisables :** Génération d'URL unique (`prenom.nom`) et upload de photo de profil.
* **Sécurité :** Nettoyage des entrées (Anti-XSS) et validation côté serveur.

### 💬 Social & Interaction
* **Fil d'actualité :** Publication de posts (texte + images) et système de commentaires.
* **Galerie Multimédia :** Visualisation des images postées via une modale interactive.
* **Gestion des médias :** Upload d'images avec vérification d'extension et compression visuelle (support `.webp`).

### 🎨 Expérience Utilisateur (UX)
* **Responsive Design :** Interface adaptée aux mobiles et desktops (via Bootstrap).
* **Dark Mode :** Thème sombre natif pour le confort visuel.
* **Robustesse :** Gestion des erreurs d'affichage (images manquantes, liens brisés) via `file_exists()`.

---

## 🛠 Architecture Technique

Ce projet a été construit sans framework PHP pour démontrer une maîtrise des concepts fondamentaux du langage et de la POO (Programmation Orientée Objet).

### Structure du Code
Nous avons opté pour une **factorisation maximale** du code :

* **`BD.php` (Abstraction de données) :** Classe centrale gérant la connexion à la base de données. Elle encapsule les identifiants et propose des méthodes génériques (`read`, `save`) pour simplifier les requêtes dans tout le site.
    
* **`InscriptionDB.php` (Logique Métier) :**
    Sépare la logique de validation (vérification des champs vides, génération d'ID unique) de l'insertion technique en base de données.

* **Gestion des fichiers :**
    Stockage des *chemins d'accès* en base de données (et non des fichiers BLOB) pour garantir la légèreté et la performance des requêtes SQL.

---

## 💻 Installation en local

Pour tester le projet sur votre machine :

1.  **Cloner le dépôt :**
    ```bash
    git clone [https://github.com/ton-username/sclayintouch.git](https://github.com/ton-username/sclayintouch.git)
    ```

2.  **Base de Données :**
    * Importez le fichier `sclayintouch.sql` (situé à la racine) dans votre gestionnaire MySQL (phpMyAdmin, Workbench...).
    * La base de données s'appelle `saclayInTouch_db`.

3.  **Configuration :**
    * Ouvrez le fichier `classes/BD.php` (ou l'emplacement de ta classe).
    * Modifiez les identifiants si nécessaire :
    ```php
    private $host = "localhost";
    private $username = "root";
    private $password = ""; // Votre mot de passe
    ```

4.  **Lancement :**
    * Placez le dossier dans votre répertoire serveur (ex: `htdocs` pour XAMPP ou `www` pour WAMP).
    * Accédez à `http://localhost/sclayintouch/login.php`.

---

## 🤝 Auteurs

Projet réalisé dans le cadre académique par :
* **SKALI Hamza**
* **SERRAJ Mehdi**

---


Fait avec ❤️ et beaucoup de café.
