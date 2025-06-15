<h1 align="center">🎯 Symfony</h1>

<h2 align="center">Symfony est un framework PHP open-source très populaire pour le développement d'applications web. Il propose une série d'outils et de bibliothèques réutilisables pour créer des applications robustes et évolutives.</h2>

---

### ✅ Prérequis

Avant d'installer Symfony, assurez-vous que votre machine dispose de :

- **PHP** (>= 8.1 recommandé)
- **Composer** (gestionnaire de dépendances PHP)
- **Base de données** (MySQL, PostgreSQL, etc. selon vos besoins)
- **symfony CLI**

---

### 🛠️ Installation

Si PHP n'est pas installé :

👉 Télécharger depuis [wampserver.com](https://www.wampserver.com/)

Si Composer n'est pas installé :

👉 Télécharger depuis [getcomposer.org](https://getcomposer.org/download/)

Si symfony CLI n'est pas installé :

👉 Télécharger depuis [symfony.com](https://symfony.com/download)

---
### 🔒 Certificat HTTPS

Pour générer un certificat local <strong>HTTPS</strong> :
```bash
symfony server:ca:install
```
⚠️ *Le certificat à besoin d'être installer une seule fois par machine !*

---
### 🚀 Création d’un projet Symfony

Créez un nouveau projet Symfony avec le pack web complet :
```bash
symfony new NomProjet --webapp
```
---
### 🔧 Pour changer la version de php dans votre projet symfony
Dans le dossier du projet Symfony :
```bash
echo 8.*.* > .php-version
```
---
### 🧪 Vérifier les serveurs Symfony actifs

Liste les serveurs Symfony actuellement lancés :
```bash
symfony server:list
```
---
### 🟢 Démarrage du serveur symfony

Commande pour lancer le serveur symfony local :
```bash
symfony server:start -d
```
---
### 🌐 Ouvrir la page web 

Commande pour ouvrir votre site via l'invite de commande :
```bash
symfony open:local
```
---
### 🔴 Arrêter le serveur symfony local

Cette commande permet d'arrêter votre serveur symfony. Faites CTRL + C dans votre terminal si la commande ne fonctionne pas :
```bash
symfony server:stop
```
---

<h2 align="center">Création d'une page web</h2>

### ✨ Création d'un controller

Pour en apprendre d'avantages sur les controllers rendez-vous sur [cette page](https://github.com/Kosal-DEV/Symfony/blob/main/controller.md) !
```bash
symfony console make:controller nomController
```

### 💾 Créer une base de donnée

Cette commande permet de créer une base de donnée, pour en apprendre d'avantage sur Doctrine ORM [(cliquez-ici)](https://github.com/Kosal-DEV/Symfony/blob/main/Doctrine_ORM.md)
```bash
symfony console doctrine:database:create
```

### 🗑️ Supprimer une base de donnée

Cette commande permet de supprimer une base de donnée définitivement donc à utiliser avec modération !
```bash
symfony console doctrine:database:drop --force
```

### 📦 Créer une entité

Attention une entité est représentée sous forme de classe PHP. Cette commande va nous permettre de créer une Classe avec les attributs qu’on voudra ainsi que les getters et setters de ces attributs.
```bash
symfony console make:entity 
```

### 📤 Migration de notre entité

Cette commande génère un fichier SQL pour appliquer les changements faits aux entités dans la base de données.
```bash
symfony console make:migration
```

### 🗄️ Applique les changements à la base de données

La commande exécute les fichiers de migration générés avec `make:migration`.
```bash
symfony console doctrine:migrations:migrate
```
