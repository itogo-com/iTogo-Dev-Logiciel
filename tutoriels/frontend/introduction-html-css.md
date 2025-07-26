# 🎨 Introduction au HTML et CSS

> **Votre premier pas** dans le développement web avec HTML et CSS

## 🎯 Objectif

À la fin de ce tutoriel, vous serez capable de :

- ✅ Créer une page web simple avec HTML
- ✅ Styliser votre page avec CSS
- ✅ Comprendre les concepts de base du web
- ✅ Publier votre première page web

## 📋 Prérequis

- **Aucune connaissance** en programmation requise
- **Ordinateur** avec un navigateur web (Chrome, Firefox, Safari)
- **Éditeur de texte** : VS Code recommandé (gratuit)
- **Motivation** et envie d'apprendre !

## 🚀 Installation

### 1. Installer VS Code

1. Allez sur [code.visualstudio.com](https://code.visualstudio.com/)
2. Téléchargez la version pour votre système d'exploitation
3. Installez VS Code en suivant les instructions

### 2. Installer les extensions recommandées

Dans VS Code, installez ces extensions :

- `Live Server` : Pour voir votre site en temps réel
- `Auto Rename Tag` : Pour faciliter l'écriture HTML
- `Prettier` : Pour formater votre code

## 📝 Guide pas à pas

### Étape 1 : Comprendre le web

#### Qu'est-ce qu'une page web ?

Une page web est composée de :

- **HTML** : La structure (comme les os d'un corps)
- **CSS** : Le style (comme les vêtements)
- **JavaScript** : L'interactivité (comme les muscles)

#### Comment ça marche ?

1. Vous écrivez du code HTML/CSS
2. Le navigateur lit ce code
3. Le navigateur affiche votre page web

### Étape 2 : Créer votre premier fichier HTML

#### 1. Créer un dossier de projet

```bash
# Créez un dossier pour votre projet
mkdir mon-premier-site
cd mon-premier-site
```

#### 2. Créer le fichier HTML

Dans VS Code, créez un fichier `index.html` :

```html
<!DOCTYPE html>
<html lang="fr">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Mon Premier Site Web</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header>
      <h1>Bienvenue sur mon site !</h1>
      <nav>
        <ul>
          <li><a href="#accueil">Accueil</a></li>
          <li><a href="#apropos">À propos</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <section id="accueil">
        <h2>Accueil</h2>
        <p>Bienvenue sur mon premier site web créé avec HTML et CSS !</p>
        <p>Ce site a été créé dans le cadre du tutoriel iTogo Dev Logiciel.</p>
      </section>

      <section id="apropos">
        <h2>À propos</h2>
        <p>
            Je suis un développeur web en formation, passionné par
            la création de sites web.
        </p>
        <p>J'apprends actuellement :</p>
        <ul>
          <li>HTML pour la structure</li>
          <li>CSS pour le style</li>
          <li>JavaScript pour l'interactivité</li>
        </ul>
      </section>

      <section id="contact">
        <h2>Contact</h2>
        <p>Vous pouvez me contacter :</p>
        <ul>
          <li>📧 Email : contact@example.com</li>
          <li>📱 Téléphone : +228 XX XX XX XX</li>
          <li>🌐 Site web : www.example.com</li>
        </ul>
      </section>
    </main>

    <footer>
      <p>&copy; 2024 - Mon Premier Site Web. Créé avec ❤️ et iTogo Dev Logiciel.</p>
    </footer>
  </body>
</html>
```

### Étape 3 : Comprendre la structure HTML

#### Les balises HTML de base

```html
<!-- Commentaire HTML -->

<!-- Balises de structure -->
<html>
  <!-- Conteneur principal -->
  <head>
    <!-- Métadonnées de la page -->
    <body>
      <!-- Contenu visible -->

      <!-- Balises de titre -->
      <h1>
        <!-- Titre principal (le plus important) -->
        <h2>
          <!-- Sous-titre -->
          <h3>
            <!-- Sous-sous-titre -->
            <!-- ... jusqu'à h6 -->

            <!-- Balises de contenu -->
            <p><!-- Paragraphe --></p>
            <div>
              <!-- Division (conteneur générique) -->
              <span>
                <!-- Portion de texte inline -->
                <ul>
                  <!-- Liste non ordonnée -->
                  <ol>
                    <!-- Liste ordonnée -->
                    <li>
                      <!-- Élément de liste -->

                      <!-- Balises de lien et image -->
                      <a>
                        <!-- Lien hypertexte -->
                        <img />
                        <!-- Image -->

                        <!-- Balises sémantiques -->
                        <header>
                          <!-- En-tête de page -->
                          <nav>
                            <!-- Navigation -->
                            <main>
                              <!-- Contenu principal -->
                              <section>
                                <!-- Section de contenu -->
                                <article>
                                  <!-- Article indépendant -->
                                  <aside>
                                    <!-- Contenu secondaire -->
                                    <footer><!-- Pied de page --></footer>
                                  </aside>
                                </article>
                              </section>
                            </main>
                          </nav>
                        </header></a
                      >
                    </li>
                  </ol>
                </ul></span
              >
            </div>
          </h3>
        </h2>
      </h1>
    </body>
  </head>
</html>
```

### Étape 4 : Ajouter du style avec CSS

#### 1. Créer le fichier CSS

Créez un fichier `styles.css` dans le même dossier :

```css
/* Reset CSS de base */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Variables CSS pour les couleurs */
:root {
  --primary-color: #2563eb;
  --secondary-color: #64748b;
  --background-color: #f8fafc;
  --text-color: #1e293b;
  --accent-color: #f59e0b;
}

/* Style du body */
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: var(--text-color);
  background-color: var(--background-color);
}

/* Style du header */
header {
  background: linear-gradient(135deg, var(--primary-color), #1d4ed8);
  color: white;
  padding: 2rem 0;
  text-align: center;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

header h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

/* Style de la navigation */
nav ul {
  list-style: none;
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 1rem;
}

nav a {
  color: white;
  text-decoration: none;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

nav a:hover {
  background-color: rgba(255, 255, 255, 0.2);
}

/* Style du contenu principal */
main {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

section {
  background: white;
  margin: 2rem 0;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

section:hover {
  transform: translateY(-5px);
}

section h2 {
  color: var(--primary-color);
  margin-bottom: 1rem;
  font-size: 1.8rem;
  border-bottom: 3px solid var(--accent-color);
  padding-bottom: 0.5rem;
}

section p {
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

/* Style des listes */
ul {
  list-style-position: inside;
  margin-left: 1rem;
}

li {
  margin-bottom: 0.5rem;
  padding-left: 0.5rem;
}

/* Style des liens */
a {
  color: var(--primary-color);
  text-decoration: none;
  transition: color 0.3s ease;
}

a:hover {
  color: var(--accent-color);
  text-decoration: underline;
}

/* Style du footer */
footer {
  background-color: var(--secondary-color);
  color: white;
  text-align: center;
  padding: 2rem;
  margin-top: 3rem;
}

/* Responsive design */
@media (max-width: 768px) {
  header h1 {
    font-size: 2rem;
  }

  nav ul {
    flex-direction: column;
    gap: 1rem;
  }

  main {
    padding: 1rem;
  }

  section {
    padding: 1.5rem;
  }
}
```

### Étape 5 : Comprendre les concepts CSS

#### Les sélecteurs CSS

```css
/* Sélecteur d'élément */
h1 {
  /* Style pour tous les h1 */
}

/* Sélecteur de classe */
.mon-classe {
  /* Style pour les éléments avec class="mon-classe" */
}

/* Sélecteur d'ID */
#mon-id {
  /* Style pour l'élément avec id="mon-id" */
}

/* Sélecteur descendant */
header nav {
  /* Style pour nav à l'intérieur de header */
}

/* Sélecteur d'enfant direct */
header > nav {
  /* Style pour nav enfant direct de header */
}

/* Pseudo-classes */
a:hover {
  /* Style au survol des liens */
}
button:active {
  /* Style quand le bouton est cliqué */
}
```

#### Les propriétés CSS importantes

```css
/* Couleurs et arrière-plans */
color: #ff0000; /* Couleur du texte */
background-color: #ffffff; /* Couleur d'arrière-plan */
background-image: url("image.jpg"); /* Image d'arrière-plan */

/* Typographie */
font-family: Arial, sans-serif; /* Police */
font-size: 16px; /* Taille de police */
font-weight: bold; /* Gras */
text-align: center; /* Alignement du texte */

/* Espacement */
margin: 10px; /* Marge extérieure */
padding: 10px; /* Marge intérieure */
width: 100%; /* Largeur */
height: 200px; /* Hauteur */

/* Positionnement */
display: flex; /* Disposition flexible */
position: relative; /* Position relative */
float: left; /* Flottement */

/* Bordures et ombres */
border: 1px solid #000; /* Bordure */
border-radius: 5px; /* Coins arrondis */
box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* Ombre */
```

### Étape 6 : Voir votre site en action

#### 1. Ouvrir avec Live Server

1. Dans VS Code, ouvrez votre fichier `index.html`
2. Clic droit sur le fichier
3. Sélectionnez "Open with Live Server"
4. Votre navigateur s'ouvre automatiquement

#### 2. Tester la responsivité

1. Ouvrez les outils de développement (F12)
2. Cliquez sur l'icône mobile/tablette
3. Testez différentes tailles d'écran

## 🎯 Exercices pratiques

### Exercice 1 : Personnaliser votre site

Modifiez votre site pour qu'il vous représente :

1. **Changez les couleurs** dans les variables CSS
2. **Ajoutez votre photo** de profil
3. **Modifiez le contenu** avec vos informations
4. **Ajoutez une section** "Mes projets"

### Exercice 2 : Créer une page de contact

Créez une nouvelle page `contact.html` avec :

1. **Formulaire de contact** avec HTML
2. **Style CSS** cohérent avec votre site
3. **Validation** basique des champs
4. **Design responsive**

### Exercice 3 : Ajouter des animations

Utilisez CSS pour ajouter des animations :

1. **Effet de survol** sur les boutons
2. **Animation d'apparition** des sections
3. **Transition** sur les liens
4. **Effet de pulsation** sur les éléments importants

## 📚 Ressources pour aller plus loin

### Documentation officielle

- [MDN Web Docs - HTML](https://developer.mozilla.org/fr/docs/Web/HTML)
- [MDN Web Docs - CSS](https://developer.mozilla.org/fr/docs/Web/CSS)
- [W3Schools HTML](https://www.w3schools.com/html/)
- [W3Schools CSS](https://www.w3schools.com/css/)

### Outils utiles

- [Color Hunt](https://colorhunt.co/) : Palettes de couleurs
- [Google Fonts](https://fonts.google.com/) : Polices gratuites
- [CSS Grid Generator](https://cssgrid-generator.netlify.app/) : Générateur de grille
- [Flexbox Froggy](https://flexboxfroggy.com/) : Jeu pour apprendre Flexbox

### Tutoriels avancés

- [CSS Grid Layout](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Variables](https://developer.mozilla.org/fr/docs/Web/CSS/Using_CSS_custom_properties)
- [Responsive Design](https://developer.mozilla.org/fr/docs/Learn/CSS/CSS_layout/Responsive_Design)

## 🎉 Félicitations !

Vous avez créé votre premier site web ! Voici ce que vous avez appris :

- ✅ **Structure HTML** : Balises, sémantique, organisation
- ✅ **Style CSS** : Couleurs, typographie, mise en page
- ✅ **Responsive Design** : Adaptation mobile
- ✅ **Bonnes pratiques** : Code propre et organisé

## 🚀 Prochaines étapes

1. **JavaScript** : Ajouter de l'interactivité
2. **Frameworks CSS** : Bootstrap, Tailwind CSS
3. **Préprocesseurs** : Sass, Less
4. **Outils de build** : Webpack, Vite

---

**💡 Conseil** : Pratiquez régulièrement !  
Créez de petits projets pour consolider vos connaissances.

**🤝 Besoin d'aide ?** Rejoignez la communauté iTogo sur Discord ou GitHub !
