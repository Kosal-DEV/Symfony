# Symfony

Symfony est un framework PHP open-source très populaire pour le développement d'applications web. Symfony offre une série d'outils et de bibliothèques réutilisables qui permettent de créer des applications web robustes et évolutives. Il est très utilisé par les développeurs PHP, surtout pour des projets complexes ou de grande envergure.

## Prérequis :

Avant de commencer l'installation de Symfony, assurez-vous que vous avez les éléments suivants installés sur votre machine :

- **PHP** (version 8.1 ou supérieure recommandée)
- **Composer** (outil de gestion des dépendances PHP)
- **Base de données** (comme MySQL ou PostgreSQL si vous prévoyez de l'utiliser)

## Étapes d'installation

### 1. Installer Composer
Composer est un gestionnaire de dépendances pour PHP. Si vous ne l'avez pas encore installé, suivez ces étapes :

#### Installer Composer globalement
1. Télécharger le programme d'installation de Composer : 
   ```url
   https://getcomposer.org/download/
   ```

### Création d'un projet symfony :
```symfony
symfony new NomProjet --webapp
```
Le `--webapp` permet d'installer toute les dépendances requise dans un projet web.

Une fois la commande executer, le CMD vous demandera si on veux inclure une configuration docker. A vous de voir ;)

### Pour changer la version de php dans votre projet symfony :
```symfony
echo 8.*.* > .php-version
```
