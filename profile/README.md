# Node.js Express Template Project

![1347187](https://github.com/user-attachments/assets/5f3f0b5e-009c-4fe7-9201-00e28f83f265)

Ce projet est un modèle de serveur Node.js utilisant Express, conçu pour gérer des sous-domaines sur le domaine `my-monkey.fr`. Il inclut un ORM avec Sequelize et permet l'intégration de modules via des sous-dossiers.  

## Fonctionnalités

- Structure modulaire pour sous-domaines.
- ORM Sequelize avec modules disponibles sur [my-monkeys/models](https://github.com/my-monkeys/models).
- Middleware pour les logs et les ID de requête.
- Gestion des fichiers statiques via le dossier `public`.
- Routes dynamiques définies dans `src/app.js`.

## Prérequis

- Node.js v14 ou supérieur.
- Base de données compatible Sequelize (MySQL, PostgreSQL, etc.).
- `git` pour cloner avec les sous-modules.

## Installation

1. Clonez le projet avec les sous-modules :
   ```bash
   git clone --recurse-submodules git@github.com:my-monkeys/templates.git
   ```

2. Installez les dépendances :
   ```bash
   npm install
   ```

3. Configurez les variables d'environnement dans un fichier `.env` (exemple : connexion DB, port, etc.).

4. Lancer le serveur :
   ```bash
   npm start
   ```

## Structure du projet

```
.
├── package.json
├── server.js
├── public/               # Fichiers statiques (HTML, CSS, JS, images)
│   ├── index.html
│   ├── admin.html
│   ├── assets/
│       ├── css/
│       ├── js/
│       ├── img/
│       └── svg/
├── src/
│   ├── app.js            # Configuration des routes
│   ├── config/           # Configurations (DB, logs)
│   ├── controllers/      # Logique des endpoints
│   ├── middleware/       # Middlewares Express
│   ├── models/           # Modèles Sequelize
│   ├── routes/           # Définition des routes
│   ├── utils/            # Fonctions utilitaires
│   └── validators/       # Validation des données
```

## Exemple d'utilisation

### Exemple de fichier `.env`
```env
DB_HOST=127.0.0.1
DB_PORT=3306
DB_USER=my_user
DB_PASSWORD=my_password
DB_DATABASE=my-monkey

# Variables spécifiques aux modules
<MODULE_NAME>_<CLE>=valeur
```

### Instructions pour les nouvelles variables

- Chaque nouvelle variable d'environnement doit suivre la convention :  
  **`<nom_du_module>_<clé>`**  
  Exemple : Si le module s'appelle `admin` et la clé est `API_KEY`, ajoutez :  
  ```env
  admin_API_KEY=12345
  ```

- Cette convention garantit que les variables spécifiques aux modules seront prises en compte en production.


### Scripts disponibles
- `npm start` : Démarre le serveur avec `nodemon`.

## Ressources supplémentaires

- [Express.js Documentation](https://expressjs.com/)
- [Sequelize Documentation](https://sequelize.org/)
- [Guide Submodules Git](https://git-scm.com/book/en/v2/Git-Tools-Submodules)

## Auteur

Créé par Maxim pour des projets modulaires avec une gestion optimisée des sous-domaines.
