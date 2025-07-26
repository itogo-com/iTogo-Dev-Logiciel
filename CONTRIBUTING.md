# 🤝 Guide de Contribution - iTogo Développement Logiciel

Merci de votre intérêt
pour contribuer à la communauté **iTogo Développement Logiciel**
Ce guide vous aidera à participer efficacement au projet.

## 📋 Table des matières

- [Comment contribuer] (#comment-contribuer)
- [Structure du projet] (#structure-du-projet)
- [Standards de code] (#standards-de-code)
- [Processus de contribution] (#processus-de-contribution)
- [Conventions de nommage] (#conventions-de-nommage)
- [Tests et qualité] (#tests-et-qualité)
- [Documentation] (#documentation)

## 🎯 Comment contribuer

### Types de contributions acceptées

- ✅ **Nouveaux tutoriels** : Créer des guides d'apprentissage
- ✅ **Amélioration de la documentation** : Corriger, clarifier, enrichir
- ✅ **Nouvelles ressources** : Ajouter des outils, e-books, liens utiles
- ✅ **Correction de bugs** : Signaler et corriger les problèmes
- ✅ **Suggestions d'amélioration** : Proposer de nouvelles fonctionnalités
- ✅ **Traduction** : Aider à traduire le contenu en français

### Avant de commencer

1. **Lisez ce guide** entièrement
2. **Vérifiez les issues existantes** pour éviter les doublons
3. **Discutez de votre idée** dans une issue avant de coder
4. **Assurez-vous d'avoir les prérequis** techniques

## 📁 Structure du projet

``` bash
iTogo-Dev-Logiciel/
├── projets/        # Projets réalisés par la communauté
│   ├── web/        # Applications web
│   ├── mobile/     # Applications mobiles
│   └── desktop/    # Applications desktop
├── ressources/     # Ressources éducatives
│   ├── cours/      # Cours et formations
│   ├── ebooks/     # Livres électroniques
│   └── outils/     # Outils de développement
├── tutoriels/      # Guides d'apprentissage
│   ├── frontend/   # Tutoriels frontend
│   ├── backend/    # Tutoriels backend
│   └── fullstack/  # Tutoriels fullstack
└── .github/        # Configuration GitHub
```

## 💻 Standards de code

### Technologies recommandées

#### Frontend

- **HTML**
- **CSS**
- **JavaScript**
- **React** (avec Next.js ou Vite)
<!-- - **Vue.js** (avec Nuxt.js) -->
<!-- - **JavaScript/TypeScript** -->
- **JavaScript**
- **TailwindCSS** pour le styling
- **Shadcn/ui** ou **Radix UI** pour les composants

#### Backend

- **Node.js** avec Express ou Fastify
<!-- - **Python** avec Django ou FastAPI
- **PHP** avec Laravel ou Symfony
- **Java** avec Spring Boot -->

#### Mobile

- **React Native**
- **Flutter**
<!-- - **Kotlin** (Android natif) -->

### Conventions de code

#### JavaScript/TypeScript

```javascript
// ✅ Bon
const handleUserClick = (userId) => {
  // Logique ici
};

// ❌ Éviter
const click = (id) => {
  // Logique ici
};
```

#### React Components

```jsx
// ✅ Bon - Composant fonctionnel
const UserProfile = ({ userData, onUpdate }) => {
  return <div className="user-profile">{/* Contenu */}</div>;
};

// ✅ Bon - Export par défaut
export default UserProfile;
```

#### CSS/TailwindCSS

```jsx
// ✅ Bon - Utiliser TailwindCSS
<div className="flex items-center justify-between p-4 bg-white rounded-lg shadow-md">
  {/* Contenu */}
</div>

// ❌ Éviter - Styles inline
<div style={{ display: 'flex', padding: '16px' }}>
  {/* Contenu */}
</div>
```

## 🔄 Processus de contribution

### 1. Fork et Clone

```bash
# Fork le repository sur GitHub
# Puis clonez votre fork
git clone https://github.com/votre-username/iTogo-Dev-Logiciel.git
cd iTogo-Dev-Logiciel
```

### 2. Créer une branche

```bash
# Créer une branche pour votre contribution
git checkout -b feature/nom-de-votre-feature
# ou
git checkout -b fix/nom-du-bug
```

### 3. Développer

- Suivez les standards de code
- Testez votre code
- Documentez vos changements

### 4. Commiter

```bash
# Ajouter vos fichiers
git add .

# Commiter avec un message descriptif
git commit -m "feat: ajouter tutoriel React hooks

- Ajouter guide complet sur les hooks React
- Inclure exemples pratiques
- Ajouter exercices d'entraînement"
```

### 5. Pousser et créer une Pull Request

```bash
git push origin feature/nom-de-votre-feature
```

## 📝 Conventions de nommage

### Fichiers et dossiers

- **kebab-case** pour les dossiers : `react-tutorial/`
- **PascalCase** pour les composants : `UserProfile.jsx`
- **camelCase** pour les utilitaires : `formatDate.js`

### Variables et fonctions

- **camelCase** pour les variables : `userName`, `isLoading`
- **camelCase** pour les fonctions : `handleClick`, `formatData`
- **PascalCase** pour les composants : `UserProfile`, `NavigationBar`

### Messages de commit

Utilisez le format **Conventional Commits** :

``` bash
type(scope): description

[body optionnel]

[footer optionnel]
```

**Types acceptés :**

- `feat` : Nouvelle fonctionnalité
- `fix` : Correction de bug
- `docs` : Documentation
- `style` : Formatage, style
- `refactor` : Refactoring
- `test` : Tests
- `chore` : Tâches de maintenance

**Exemples :**

```bash
git commit -m "feat(tutoriels): ajouter guide React hooks"
git commit -m "fix(readme): corriger lien cassé vers CONTRIBUTING.md"
git commit -m "docs(api): ajouter documentation des endpoints"
```

## 🧪 Tests et qualité

### Avant de soumettre votre PR

- [ ] Votre code fonctionne correctement
- [ ] Vous avez testé sur différents navigateurs (si applicable)
- [ ] La documentation est à jour
- [ ] Vous avez suivi les conventions de nommage
- [ ] Votre code est lisible et bien commenté

### Tests recommandés

```javascript
// Exemple de test simple
describe("UserProfile Component", () => {
  it("should render user name correctly", () => {
    const userData = { name: "John Doe" };
    // Test ici
  });
});
```

## 📚 Documentation

### Pour les tutoriels

Chaque tutoriel doit inclure :

1. **Introduction** : Objectif et prérequis
2. **Installation** : Comment configurer l'environnement
3. **Étapes détaillées** : Guide pas à pas
4. **Exemples de code** : Code fonctionnel
5. **Exercices** : Pratiques pour renforcer l'apprentissage
6. **Ressources** : Liens utiles pour aller plus loin

### Structure d'un tutoriel

````markdown
# Titre du tutoriel

## 🎯 Objectif

Description claire de ce que l'on va apprendre

## 📋 Prérequis

- Connaissances requises
- Outils nécessaires

## 🚀 Installation

Étapes pour configurer l'environnement

## 📝 Guide pas à pas

1. Première étape
2. Deuxième étape
3. ...

## 💻 Exemples de code

```javascript
// Code d'exemple
```
````

## 🎯 Exercices

Exercices pratiques pour s'entraîner

## 📚 Ressources

- Liens utiles
- Documentation officielle

```bash

## 🤝 Code de conduite

### Nos valeurs

- **Respect** : Traitez tous les membres avec respect
- **Bienveillance** : Soyez constructif dans vos retours
- **Apprentissage** : Encouragez l'apprentissage mutuel
- **Inclusion** : Soyez ouvert aux débutants

### Comportements attendus

✅ **Acceptables :**
- Poser des questions constructives
- Proposer des améliorations
- Partager des ressources utiles
- Aider les autres membres

❌ **Non acceptables :**
- Critiques non constructives
- Spam ou publicité
- Comportement irrespectueux
- Harcèlement

## 🆘 Besoin d'aide ?

### Avant de poser une question

1. **Recherchez** dans les issues existantes
2. **Lisez** la documentation
3. **Testez** votre problème

### Où demander de l'aide

- **Issues GitHub** : Pour les bugs et suggestions
- **Discussions GitHub** : Pour les questions générales
- **Pull Requests** : Pour les revues de code

### Comment poser une bonne question

1. **Décrivez clairement** votre problème
2. **Incluez** le code concerné
3. **Précisez** votre environnement
4. **Expliquez** ce que vous avez déjà essayé

## 🎉 Merci !

Merci de contribuer à faire de **iTogo Développement Logiciel**
une communauté d'apprentissage exceptionnelle !

Votre contribution, même petite,
fait une grande différence pour les développeurs togolais et africains.

---

**💡 Conseil** : Commencez par des contributions simples comme
corriger une faute de frappe ou améliorer la documentation.
Chaque contribution compte !
```
