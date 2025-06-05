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
⚠️Le certificat à besoin d'être installer une seule fois par machine !
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

Commande pour lancer le serveur :
```bash
symfony server:start -d
```


![image test]("C:\Users\CFITECH\Desktop\CFITECH\symfony\Capture d'écran 2025-06-06 000654.png")
