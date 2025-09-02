# ILIA – Mini Site (Landing • Ressources • Club • Contact • FAQ)

Un site statique composé de 5 pages : Accueil, Ressources, Club, Contact et FAQ.  
Cette notice explique comment lancer le site, éditer le contenu (textes, couleurs, FAQ, ressources), et le déployer en ligne.

>  Le guide est en français (avec quelques termes en anglais).  
> A short English quick start is included near the end.

---

## Aperçu des pages

- **Accueil (Home)** – Section d’accueil avec bouton *Learn more*, illustration à droite, barre de navigation (Ressources, Club, Contact, FAQ, Home).  
- **Ressources** – Moteur de recherche et filtre par thème, liste de documents avec bouton *Download*, zone visuelle (logos HTML/JS/CSS) et bouton *Next*.  
- **Club (CTGINC)** – Texte de présentation, note d’information, bouton WhatsApp pour rejoindre le groupe.  
- **Contact** – Formulaire (Nom, Email, Message), bouton *Envoyer*, carte Google Maps, liens de réseaux sociaux.  
- **FAQ** – 8 questions réparties en deux colonnes, badge numéroté à gauche et bouton **+** à droite pour afficher la réponse. Bouton *plus sur ILIA* en haut.

Les captures d’écran dans le dossier `/screens/` donnent le rendu attendu.

---

## Arborescence conseillée

ilia-site/
├─ index.html            # Accueil
├─ ressources.html       # Page Ressources
├─ club.html             # Page Club (CTGINC)
├─ contact.html          # Page Contact
├─ faq.html              # Page FAQ
├─ assets/
│  ├─ css/
│  │  └─ styles.css      # Styles communs (variables, grille, composants)
│  ├─ js/
│  │  ├─ main.js         # Comportements généraux
│  │  ├─ ressources.js   # Filtre + ajout simulé + download (frontend only)
│  │  └─ faq.js          # Accordéon FAQ
│  ├─ img/
│  │  ├─ logo.svg
│  │  ├─ hero-illustration.svg
│  │  └─ tech-logos/ (html5.svg, js.svg, css3.svg)
│  └─ data/
│     ├─ ressources.json # Données éditables
│     └─ faq.json        # Questions / réponses
└─ README.md

---

## Personnalisation rapide

### Couleurs et ambiance
- Définies via `:root` dans `assets/css/styles.css` :
  :root{
    --bg1:#0b0730; --bg2:#2b1560;
    --card:#321c6a; --card2:#3a2079;
    --accent:#ffc300; --accent-2:#ffcf33;
    --text:#eae6ff; --muted:#b9b3e6;
    --ring:#6b40d8;
  }

### Typographies
- Par défaut, `Inter, system-ui, Segoe UI, Roboto, Arial, sans-serif`.  
- Possibilité d’ajouter Google Fonts dans `<head>`.

### Icônes et illustrations
- Placez vos visuels dans `assets/img/`.  
- Remplacez `hero-illustration.svg` pour l’image d’accueil.

---

## Contenus dynamiques (JSON)

### FAQ (`assets/data/faq.json`)
Exemple :
{
  "mode": "multi",
  "items": [
    {"id":1,"q":"Combien de temps dure la formation ?","a":"Réponse…","col":"left"},
    {"id":2,"q":"Quels types de cours sont enseignés ?","a":"Réponse…","col":"left"},
    {"id":3,"q":"Y a-t-il des stages obligatoires ?","a":"Réponse…","col":"left"},
    {"id":4,"q":"Quelles compétences vais-je acquérir ?","a":"Réponse…","col":"left"},
    {"id":5,"q":"Quels sont les débouchés ?","a":"Réponse…","col":"right"},
    {"id":6,"q":"La filière est-elle pratique ?","a":"Réponse…","col":"right"},
    {"id":7,"q":"Quels langages/technologies ?","a":"Réponse…","col":"right"},
    {"id":8,"q":"Ouverture à l’international ?","a":"Réponse…","col":"right"}
  ]
}

- `mode`: `"multi"` pour plusieurs réponses ouvertes, `"single"` pour un accordéon classique.  
- `col`: `"left"` ou `"right"` pour le placement en colonne.

### Ressources (`assets/data/ressources.json`)
Exemple :
[
  {"title":"Cours HTML","theme":"Programmation","size":"2 MB","href":"files/cours-html.pdf"},
  {"title":"Cours Java-script","theme":"Programmation","size":"708 KB","href":"files/js-notes.pdf"},
  {"title":"Java","theme":"Programmation","size":"6 MB","href":"files/java.pdf"}
]

---

## Accessibilité

- Items FAQ avec `<button>` et attributs ARIA.  
- Focus visible via `--ring`.  
- Couleurs testées pour contraste suffisant.  
- Images décoratives marquées `aria-hidden="true"` ou `role="presentation"`.

---

## Lancer en local

Aucun build requis. Ouvrez simplement `index.html` dans le navigateur.  

Serveur local recommandé :  

python -m http.server 8000

Puis visiter http://localhost:8000

---

## Déploiement rapide

- **GitHub Pages** : pousser le dossier, activer Pages (branch `main`, root `/`).  
- **Netlify / Vercel** : drag & drop du dossier ou connexion du repo.  
- **Serveur personnel** : uploader par FTP/SSH (HTML statique).

---

## Checklist de qualité

- Navbar active et liens vers toutes les pages.  
- Contrastes lisibles sur mobile et desktop.  
- FAQ utilisable au clavier.  
- Ressources : recherche, filtre, faux upload, bouton *Download*.  
- Contact : champs requis + message d’état.  
- Meta `<title>` et description par page.  
- Favicon et logo présents.  

---

## Quick start (EN)

1. Open `index.html` or serve the folder with a static server.  
2. Edit colors in `assets/css/styles.css`.  
3. Update content in `assets/data/faq.json` and `assets/data/ressources.json`.  
4. Deploy to GitHub Pages / Netlify / Vercel.  

---

## Licence et crédits

- Code : MIT.  
- Illustrations et logos : assurez-vous d’avoir les droits d’utilisation (ou remplacez par vos propres visuels).  
- Design inspiré des captures fournies (fond violet, cartes arrondies, badges numérotés).

