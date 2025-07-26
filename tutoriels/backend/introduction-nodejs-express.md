# ⚙️ Introduction à Node.js et Express

> **Créez votre premier serveur web** avec Node.js et Express

## 🎯 Objectif

À la fin de ce tutoriel, vous serez capable de :

- ✅ Comprendre Node.js et son écosystème
- ✅ Créer un serveur web avec Express
- ✅ Gérer les routes et les requêtes HTTP
- ✅ Créer une API REST simple
- ✅ Connecter votre API à une base de données

## 📋 Prérequis

- **Connaissances de base** en JavaScript
- **Node.js** installé (version 18+)
- **Éditeur de code** : VS Code recommandé
- **Terminal** ou ligne de commande
- **Compréhension** des concepts web (HTTP, API, JSON)

## 🚀 Installation

### 1. Installer Node.js

1. Allez sur [nodejs.org](https://nodejs.org/)
2. Téléchargez la version LTS (Long Term Support)
3. Installez Node.js en suivant les instructions
4. Vérifiez l'installation :

```bash
node --version
npm --version
```

### 2. Configurer votre environnement

```bash
# Créer un dossier pour votre projet
mkdir mon-api-nodejs
cd mon-api-nodejs

# Initialiser un projet Node.js
npm init -y

# Installer Express
npm install express

# Installer les dépendances de développement
npm install --save-dev nodemon
```

## 📝 Guide pas à pas

### Étape 1 : Comprendre Node.js

#### Qu'est-ce que Node.js ?

**Node.js** est un runtime JavaScript qui permet d'exécuter du code JavaScript côté serveur. Il utilise le moteur V8 de Chrome.

#### Avantages de Node.js

- ✅ **JavaScript partout** : Même langage frontend et backend
- ✅ **Performance** : Architecture événementielle non-bloquante
- ✅ **Écosystème riche** : npm avec des millions de paquets
- ✅ **Communauté active** : Support et documentation excellents
- ✅ **Déploiement facile** : Support cloud natif

#### Architecture Node.js

```
┌─────────────────┐
│   Application   │
├─────────────────┤
│   Node.js       │
├─────────────────┤
│   V8 Engine     │
├─────────────────┤
│   Operating     │
│   System        │
└─────────────────┘
```

### Étape 2 : Créer votre premier serveur

#### 1. Créer le fichier principal

Créez un fichier `server.js` :

```javascript
// Import d'Express
const express = require("express");

// Création de l'application Express
const app = express();

// Configuration du port
const PORT = process.env.PORT || 3000;

// Middleware pour parser le JSON
app.use(express.json());

// Middleware pour parser les données de formulaire
app.use(express.urlencoded({ extended: true }));

// Route de base
app.get("/", (req, res) => {
  res.json({
    message: "Bienvenue sur mon API Node.js !",
    version: "1.0.0",
    author: "iTogo Dev Logiciel",
  });
});

// Route de test
app.get("/test", (req, res) => {
  res.json({
    status: "success",
    message: "L'API fonctionne correctement !",
    timestamp: new Date().toISOString(),
  });
});

// Démarrage du serveur
app.listen(PORT, () => {
  console.log(`🚀 Serveur démarré sur le port ${PORT}`);
  console.log(`📱 Accédez à votre API : http://localhost:${PORT}`);
  console.log(`🧪 Testez l'API : http://localhost:${PORT}/test`);
});
```

#### 2. Configurer le script de démarrage

Modifiez votre `package.json` :

```json
{
  "name": "mon-api-nodejs",
  "version": "1.0.0",
  "description": "Mon premier serveur Node.js avec Express",
  "main": "server.js",
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": ["nodejs", "express", "api", "itogo"],
  "author": "Votre nom",
  "license": "MIT",
  "dependencies": {
    "express": "^4.18.2"
  },
  "devDependencies": {
    "nodemon": "^3.0.1"
  }
}
```

#### 3. Démarrer le serveur

```bash
# Mode développement (avec redémarrage automatique)
npm run dev

# Mode production
npm start
```

### Étape 3 : Comprendre Express

#### Qu'est-ce qu'Express ?

**Express** est un framework web minimaliste et flexible pour Node.js qui simplifie la création d'applications web et d'APIs.

#### Concepts clés d'Express

```javascript
// Application Express
const app = express();

// Middleware (fonctions exécutées entre la requête et la réponse)
app.use(express.json());

// Routes (points d'entrée de votre API)
app.get("/users", (req, res) => {
  // Logique de la route
});

// Gestion d'erreurs
app.use((err, req, res, next) => {
  // Gestion des erreurs
});
```

#### Types de requêtes HTTP

```javascript
// GET - Récupérer des données
app.get("/users", (req, res) => {
  res.json(users);
});

// POST - Créer des données
app.post("/users", (req, res) => {
  const newUser = req.body;
  users.push(newUser);
  res.status(201).json(newUser);
});

// PUT - Modifier des données
app.put("/users/:id", (req, res) => {
  const { id } = req.params;
  const updatedUser = req.body;
  // Logique de mise à jour
});

// DELETE - Supprimer des données
app.delete("/users/:id", (req, res) => {
  const { id } = req.params;
  // Logique de suppression
});
```

### Étape 4 : Créer une API REST complète

#### 1. Structure du projet

```
mon-api-nodejs/
├── server.js          # Point d'entrée
├── routes/
│   ├── users.js       # Routes utilisateurs
│   └── products.js    # Routes produits
├── controllers/
│   ├── userController.js
│   └── productController.js
├── models/
│   ├── User.js
│   └── Product.js
├── middleware/
│   ├── auth.js
│   └── validation.js
├── config/
│   └── database.js
└── package.json
```

#### 2. Créer les routes utilisateurs

Créez `routes/users.js` :

```javascript
const express = require("express");
const router = express.Router();

// Données temporaires (remplacées plus tard par une base de données)
let users = [
  {
    id: 1,
    name: "John Doe",
    email: "john@example.com",
    age: 30,
  },
  {
    id: 2,
    name: "Jane Smith",
    email: "jane@example.com",
    age: 25,
  },
];

// GET - Récupérer tous les utilisateurs
router.get("/", (req, res) => {
  try {
    res.json({
      success: true,
      data: users,
      count: users.length,
    });
  } catch (error) {
    res.status(500).json({
      success: false,
      message: "Erreur lors de la récupération des utilisateurs",
      error: error.message,
    });
  }
});

// GET - Récupérer un utilisateur par ID
router.get("/:id", (req, res) => {
  try {
    const { id } = req.params;
    const user = users.find((u) => u.id === parseInt(id));

    if (!user) {
      return res.status(404).json({
        success: false,
        message: "Utilisateur non trouvé",
      });
    }

    res.json({
      success: true,
      data: user,
    });
  } catch (error) {
    res.status(500).json({
      success: false,
      message: "Erreur lors de la récupération de l'utilisateur",
      error: error.message,
    });
  }
});

// POST - Créer un nouvel utilisateur
router.post("/", (req, res) => {
  try {
    const { name, email, age } = req.body;

    // Validation basique
    if (!name || !email || !age) {
      return res.status(400).json({
        success: false,
        message: "Tous les champs sont requis (name, email, age)",
      });
    }

    // Vérifier si l'email existe déjà
    const existingUser = users.find((u) => u.email === email);
    if (existingUser) {
      return res.status(400).json({
        success: false,
        message: "Un utilisateur avec cet email existe déjà",
      });
    }

    // Créer le nouvel utilisateur
    const newUser = {
      id: users.length + 1,
      name,
      email,
      age: parseInt(age),
    };

    users.push(newUser);

    res.status(201).json({
      success: true,
      message: "Utilisateur créé avec succès",
      data: newUser,
    });
  } catch (error) {
    res.status(500).json({
      success: false,
      message: "Erreur lors de la création de l'utilisateur",
      error: error.message,
    });
  }
});

// PUT - Modifier un utilisateur
router.put("/:id", (req, res) => {
  try {
    const { id } = req.params;
    const { name, email, age } = req.body;

    const userIndex = users.findIndex((u) => u.id === parseInt(id));

    if (userIndex === -1) {
      return res.status(404).json({
        success: false,
        message: "Utilisateur non trouvé",
      });
    }

    // Mettre à jour l'utilisateur
    users[userIndex] = {
      ...users[userIndex],
      name: name || users[userIndex].name,
      email: email || users[userIndex].email,
      age: age ? parseInt(age) : users[userIndex].age,
    };

    res.json({
      success: true,
      message: "Utilisateur modifié avec succès",
      data: users[userIndex],
    });
  } catch (error) {
    res.status(500).json({
      success: false,
      message: "Erreur lors de la modification de l'utilisateur",
      error: error.message,
    });
  }
});

// DELETE - Supprimer un utilisateur
router.delete("/:id", (req, res) => {
  try {
    const { id } = req.params;
    const userIndex = users.findIndex((u) => u.id === parseInt(id));

    if (userIndex === -1) {
      return res.status(404).json({
        success: false,
        message: "Utilisateur non trouvé",
      });
    }

    const deletedUser = users.splice(userIndex, 1)[0];

    res.json({
      success: true,
      message: "Utilisateur supprimé avec succès",
      data: deletedUser,
    });
  } catch (error) {
    res.status(500).json({
      success: false,
      message: "Erreur lors de la suppression de l'utilisateur",
      error: error.message,
    });
  }
});

module.exports = router;
```

#### 3. Mettre à jour le serveur principal

Modifiez `server.js` :

```javascript
const express = require("express");
const app = express();
const PORT = process.env.PORT || 3000;

// Middleware
app.use(express.json());
app.use(express.urlencoded({ extended: true }));

// Middleware de logging
app.use((req, res, next) => {
  console.log(`${new Date().toISOString()} - ${req.method} ${req.url}`);
  next();
});

// Routes
app.use("/api/users", require("./routes/users"));

// Route de base
app.get("/", (req, res) => {
  res.json({
    message: "Bienvenue sur mon API Node.js !",
    version: "1.0.0",
    author: "iTogo Dev Logiciel",
    endpoints: {
      users: "/api/users",
      documentation: "/api/docs",
    },
  });
});

// Route de documentation
app.get("/api/docs", (req, res) => {
  res.json({
    title: "Documentation API",
    version: "1.0.0",
    endpoints: {
      "GET /api/users": "Récupérer tous les utilisateurs",
      "GET /api/users/:id": "Récupérer un utilisateur par ID",
      "POST /api/users": "Créer un nouvel utilisateur",
      "PUT /api/users/:id": "Modifier un utilisateur",
      "DELETE /api/users/:id": "Supprimer un utilisateur",
    },
    examples: {
      "Créer un utilisateur": {
        method: "POST",
        url: "/api/users",
        body: {
          name: "John Doe",
          email: "john@example.com",
          age: 30,
        },
      },
    },
  });
});

// Middleware de gestion d'erreurs
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).json({
    success: false,
    message: "Erreur interne du serveur",
    error: process.env.NODE_ENV === "development" ? err.message : {},
  });
});

// Route 404
app.use("*", (req, res) => {
  res.status(404).json({
    success: false,
    message: "Route non trouvée",
  });
});

// Démarrage du serveur
app.listen(PORT, () => {
  console.log(`🚀 Serveur démarré sur le port ${PORT}`);
  console.log(`📱 API : http://localhost:${PORT}`);
  console.log(`📚 Documentation : http://localhost:${PORT}/api/docs`);
  console.log(`👥 Utilisateurs : http://localhost:${PORT}/api/users`);
});
```

### Étape 5 : Tester votre API

#### 1. Avec cURL

```bash
# Récupérer tous les utilisateurs
curl http://localhost:3000/api/users

# Récupérer un utilisateur par ID
curl http://localhost:3000/api/users/1

# Créer un nouvel utilisateur
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{"name":"Alice Johnson","email":"alice@example.com","age":28}'

# Modifier un utilisateur
curl -X PUT http://localhost:3000/api/users/1 \
  -H "Content-Type: application/json" \
  -d '{"age":31}'

# Supprimer un utilisateur
curl -X DELETE http://localhost:3000/api/users/2
```

#### 2. Avec Postman

1. Téléchargez [Postman](https://www.postman.com/)
2. Créez une nouvelle collection
3. Ajoutez vos requêtes avec les URLs de votre API
4. Testez toutes les opérations CRUD

#### 3. Avec Thunder Client (VS Code)

1. Installez l'extension Thunder Client dans VS Code
2. Ouvrez Thunder Client (Ctrl+Shift+P → Thunder Client)
3. Créez vos requêtes directement dans VS Code

### Étape 6 : Ajouter la validation

#### 1. Installer Joi pour la validation

```bash
npm install joi
```

#### 2. Créer un middleware de validation

Créez `middleware/validation.js` :

```javascript
const Joi = require("joi");

// Schéma de validation pour les utilisateurs
const userSchema = Joi.object({
  name: Joi.string().min(2).max(50).required(),
  email: Joi.string().email().required(),
  age: Joi.number().integer().min(18).max(120).required(),
});

// Middleware de validation
const validateUser = (req, res, next) => {
  const { error } = userSchema.validate(req.body);

  if (error) {
    return res.status(400).json({
      success: false,
      message: "Données invalides",
      errors: error.details.map((detail) => detail.message),
    });
  }

  next();
};

module.exports = {
  validateUser,
};
```

#### 3. Utiliser la validation dans les routes

Modifiez `routes/users.js` :

```javascript
const express = require("express");
const router = express.Router();
const { validateUser } = require("../middleware/validation");

// ... autres routes ...

// POST avec validation
router.post("/", validateUser, (req, res) => {
  // La validation est déjà faite par le middleware
  // ... reste du code ...
});

// PUT avec validation
router.put("/:id", validateUser, (req, res) => {
  // ... reste du code ...
});
```

## 🎯 Exercices pratiques

### Exercice 1 : Créer une API de produits

1. **Créez les routes** pour les produits (CRUD)
2. **Ajoutez la validation** avec Joi
3. **Implémentez la recherche** par nom ou catégorie
4. **Ajoutez la pagination** pour les listes

### Exercice 2 : Ajouter l'authentification

1. **Installez bcrypt** pour le hachage des mots de passe
2. **Créez les routes** d'inscription et de connexion
3. **Implémentez JWT** pour les tokens d'authentification
4. **Protégez les routes** avec un middleware d'auth

### Exercice 3 : Connecter à une base de données

1. **Installez MongoDB** et Mongoose
2. **Créez les modèles** pour les utilisateurs et produits
3. **Remplacez les données temporaires** par la base de données
4. **Ajoutez les index** pour optimiser les performances

## 📚 Ressources pour aller plus loin

### Documentation officielle

- [Node.js Documentation](https://nodejs.org/docs/)
- [Express.js Documentation](https://expressjs.com/)
- [npm Documentation](https://docs.npmjs.com/)

### Outils utiles

- [Postman](https://www.postman.com/) : Tester les APIs
- [Thunder Client](https://www.thunderclient.com/) : Client API pour VS Code
- [Joi](https://joi.dev/) : Validation de données
- [Morgan](https://github.com/expressjs/morgan) : Logging des requêtes

### Tutoriels avancés

- [Authentication avec JWT](https://jwt.io/)
- [MongoDB avec Mongoose](https://mongoosejs.com/)
- [Tests avec Jest](https://jestjs.io/)
- [Déploiement sur Heroku](https://devcenter.heroku.com/)

## 🎉 Félicitations !

Vous avez créé votre première API Node.js ! Voici ce que vous avez appris :

- ✅ **Node.js** : Runtime JavaScript côté serveur
- ✅ **Express** : Framework web pour Node.js
- ✅ **API REST** : Création d'endpoints CRUD
- ✅ **Validation** : Vérification des données
- ✅ **Middleware** : Fonctions intermédiaires
- ✅ **Gestion d'erreurs** : Traitement des erreurs

## 🚀 Prochaines étapes

1. **Base de données** : MongoDB, PostgreSQL
2. **Authentification** : JWT, OAuth
3. **Tests** : Jest, Supertest
4. **Déploiement** : Heroku, Vercel, AWS
5. **Documentation** : Swagger, Postman Collections

---

**💡 Conseil** : Pratiquez en créant des APIs pour vos projets personnels !

**🤝 Besoin d'aide ?** Rejoignez la communauté iTogo sur Discord ou GitHub !
