# Sprint-03 - Guide Complet du Fichier CSS

## 📄 Projet
Ce projet consiste à styliser un CV créé en HTML5 sémantique avec du CSS professionnel et bien documenté.

---

## 🎨 Explication Complète du Fichier `style.css`

### **1️⃣ EN-TÊTE DU FICHIER (Commentaires)**

```css
/* =====================================================
   FICHIER : style.css
   SPRINT : 03 - Programmation Web  / IMeN Bénin
   AUTEUR : Emmanuel GBODOU 
   ========================== ========================== */
```
**Explication :** C'est un commentaire qui identifie le fichier, son objectif, le sprint et l'auteur. Les commentaires en CSS commencent par `/*` et se terminent par `*/`. Cela aide les futurs développeurs à comprendre d'où vient le code.

---

### **2️⃣ RÉINITIALISATION DU BOX MODEL**

```css
*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
```

**Ligne par ligne :**
- `*` = Le sélecteur universel qui cible **tous les éléments** HTML de la page
- `box-sizing: border-box;` = Change le calcul de la largeur/hauteur des éléments. Sans cela, les marges et bordures augmentent la taille totale de l'élément. Avec `border-box`, la largeur inclut tout (bordure, padding, contenu)
- `margin: 0;` = Supprime les marges externes (espace en dehors de la bordure) de tous les éléments
- `padding: 0;` = Supprime les marges internes (espace entre la bordure et le contenu) de tous les éléments

**Pourquoi ?** Cela crée une base de départ uniforme. Les navigateurs appliquent des marges et paddings par défaut, ce qui cause des espacements inattendus.

---

### **3️⃣ VARIABLES CSS (Personnalisation Globale)**

```css
:root{
    /* Couleurs */
    --couleur-primaire: #1B3A5C;
    --couleur-secondaire: #2A6496;
    --couleur-fond-page: #F7F4EF;
    --couleur-fond-blanc: #FFFFFF;
    --couleur-fond-aside: #EBF3FA;
    --couleur-texte: #444441;
    --couleur-texte-fort: #2C2C2A;
    --couleur-bordure: #D3D1C7;
```

**Explication :**
- `:root` = Le sélecteur racine de la page. Les variables définies ici sont **accessibles partout** dans le CSS
- `--couleur-primaire: #1B3A5C;` = Crée une variable nommée `couleur-primaire` avec la valeur bleu foncé `#1B3A5C`. Les variables CSS commencent par `--`
- Les codes hexadécimaux `#FFFFFF`, `#444441` etc. sont des **codes couleur** (6 chiffres/lettres après le #)

**Avantage :** Vous pouvez changer une couleur au seul endroit et elle s'applique partout !

```css
    /* Polices */
    --police-titres: 'Playfair Display' , Georgia, serif;
    --police-texte: 'Source Sans 3' , Arial, sans-serif;
```

- `--police-titres` = Variable pour les polices des titres
- `'Playfair Display'` = Première police préférée (Google Font)
- `Georgia, serif` = Alternatives si la première n'est pas disponible

```css
    /*Espacements en rem (relatifs à la taille de police racine) */
    --espace-xs: 0.25rem;
    --espace-sm: 0.5rem;
    --espace-md: 1rem;
    --espace-lg: 1.5rem;
    --espace-xl: 2rem;
```

- `rem` = Unité relative (1rem = 16px par défaut)
- Ces variables créent une **échelle d'espacement cohérente** : xs (très petit), sm (petit), md (moyen), lg (grand), xl (très grand)

```css
    --largeur-max: 960px;
```
- Définit la largeur maximale du contenu à 960 pixels pour éviter les pages trop larges

---

### **4️⃣ BODY - LE CORPS DE LA PAGE**

```css
body {
    font-family: var(--police-texte);
```
- `font-family:` = Définit la police de caractères
- `var(--police-texte)` = Utilise la variable définie plus haut (`'Source Sans 3'`)

```css
    font-size: 16px;
```
- Définit la taille de base du texte à 16 pixels

```css
    line-height: 1.6;
```
- L'espacement entre les lignes. 1.6 signifie 1.6 fois la taille de la police (espace agréable à lire)

```css
    color: var(--couleur-texte);
```
- Couleur du texte utilisée partout (gris foncé)

```css
    background-color: var(--couleur-fond-page);
```
- Couleur de fond de la page (beige clair)

```css
    max-width: var(--largeur-max);
    margin-top: var(--espace-xl);
    margin-bottom: var(--espace-xl);
    margin-right: auto;
    margin-left: auto;
```
- `max-width:` = La page ne dépasse pas 960px de large
- `margin-top/bottom:` = Espace en haut et bas de 2rem (32px)
- `margin-right: auto; margin-left: auto;` = Centre la page horizontalement (espaces égaux à gauche et droite)

```css
    padding-left: var(--espace-md);
    padding-right: var(--espace-md);
```
- `padding:` = Espace intérieur. Cela crée un espacement de 1rem (16px) de chaque côté du contenu

---

### **5️⃣ LES PARAGRAPHES**

```css
p {
    margin-bottom: var(--espace-sm);
}

p:last-child {
    margin-bottom: 0;
}
```

- `p` = Cible tous les paragraphes
- `margin-bottom:` = Ajoute un espace sous chaque paragraphe (0.5rem)
- `p:last-child` = Cible uniquement le **dernier** paragraphe d'un conteneur
- `:last-child` = Pseudo-classe qui sélectionne le dernier enfant
- `margin-bottom: 0;` = Supprime l'espace du dernier paragraphe (évite un espacement excessif)

---

### **6️⃣ LES TITRES (h1, h2, h3)**

```css
h1, h2, h3 {
    font-family: var(--police-titres);
    color: var(--couleur-primaire);
    line-height: 1.3;
}
```

- `h1, h2, h3` = La virgule signifie "appliquer les mêmes styles à tous ces éléments"
- `font-family:` = Utilise la police "Playfair Display" pour tous les titres
- `color:` = Couleur bleue foncée
- `line-height: 1.3;` = Moins d'espacement que le corps (1.3 vs 1.6) pour des titres plus compacts

```css
h1 { font-size: 2rem; }
```
- Le h1 (grand titre) = 32px (2 × 16px)

```css
h2 { font-size: 1.3rem; margin-bottom: var(--espace-md); }
```
- Le h2 (titre section) = 20.8px et espacement de 1rem en bas

```css
h3 { 
    font-family: var(--police-texte);
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--couleur-texte-fort);
}
```

- Le h3 (petit titre) utilise une police différente, plus petite (0.95rem = ~15px)
- `font-weight: 600;` = Gras (600 est entre normal=400 et très gras=700)
- Couleur grise foncée au lieu du bleu

---

### **7️⃣ MISE EN PAGE : FLOAT (Disposition à Deux Colonnes)**

```css
main {
    float: left;
    width: 62%;
    padding-right: var(--espace-lg);
}
```

- `float: left;` = Place le contenu principal à gauche
- `width: 62%;` = Occupe 62% de la largeur
- `padding-right:` = Ajoute 1.5rem d'espace entre main et aside

```css
aside {
    float: right;
    width: 35%;
}
```

- `float: right;` = Place la barre latérale à droite
- `width: 35%;` = Occupe 35% de la largeur
- **62% + 35% = 97%** (3% pour l'espacement entre les deux)

```css
footer {
    clear: both;
}
```

- `clear: both;` = Force le footer à se placer **sous** les éléments flottants (main et aside)

---

### **8️⃣ EN-TÊTE (header)**

```css
header {
    background-color: var(--couleur-fond-blanc);
    padding: var(--espace-xl);
    margin-bottom: var(--espace-md);
    border-radius: 8px;
    border-top: 5px solid var(--couleur-primaire);
    box-shadow: 0 2px 8px rgba(27, 58, 92, 0.08);
    text-align: center;
}
```

- `background-color:` = Fond blanc
- `padding: 2rem;` = Espace intérieur tout autour
- `margin-bottom:` = Espace sous le header
- `border-radius: 8px;` = Arrondit les coins (8px de rayon)
- `border-top: 5px solid` = Une bordure bleue de 5px au-dessus
- `box-shadow: 0 2px 8px rgba(27, 58, 92, 0.08);` = Une ombre légère (0 horizontal, 2px vertical, 8px de flou, couleur semi-transparente)
- `text-align: center;` = Centre le texte

```css
header img {
    width: 120PX;
    height: 120px;
    border-radius: 50%;
    border: 4px solid var(--couleur-primaire);
    object-fit: cover;
}
```

- `width/height: 120px;` = Image carrée de 120×120 pixels
- `border-radius: 50%;` = **Transforme le carré en cercle** (50% = rayon de 50%)
- `border: 4px solid` = Bordure bleue de 4px
- `object-fit: cover;` = Remplit l'espace (recadre l'image si nécessaire)

---

### **9️⃣ LIENS DANS LE HEADER**

```css
header address a {
    display: inline-block;
    background-color: var(--couleur-primaire);
    color: #FFFFFF;
    padding: 2px 8px;
    border-radius: 4px;
    font-weight: 600;
    font-size: 0.85rem;
    text-decoration: none;
    transition: backgrond-color 0.2s ease, transform 0.1s ease;
}
```

- `display: inline-block;` = Le lien peut avoir une largeur/hauteur (contrairement à `inline`)
- `background-color:` = Fond bleu foncé
- `color: #FFFFFF;` = Texte blanc
- `padding: 2px 8px;` = 2px haut/bas, 8px gauche/droite (crée un bouton)
- `border-radius: 4px;` = Coins légèrement arrondis
- `text-decoration: none;` = Supprime le soulignement des liens
- `transition:` = Animation smooth en 0.2s quand on change background-color ou transform

```css
header address a:hover {
    background-color: var(--couleur-secondaire);
}
```

- `:hover` = Quand la souris survole le lien, change la couleur en bleu plus clair

```css
header address a:active {
    transform: scale(0.96);
}
```

- `:active` = Quand on clique, le lien rétrécit à 96% (effet de bouton enfoncé)

---

### **🔟 SECTIONS PRINCIPALES (main et aside)**

```css
main section, aside section {
    background-color: var(--couleur-fond-blanc);
    border-radius: 8px;
    padding: var(--espace-lg);
    margin-bottom: var(--espace-md);
    border: 1px solid var(--couleur-bordure);
    box-shadow: 0 1px 4px rgba(27, 58, 92, 0.05);
}
```

- Crée des **boîtes blanches** avec coins arrondis et une légère ombre pour chaque section
- `border: 1px solid` = Une fine bordure grise

```css
main section h2, aside section h2 {
    font-size: 0.82rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    font-family: var(--police-texte);
    font-weight: 700;
    padding-bottom: var(--espace-sm);
    margin-bottom: var(--espace-md);
    border-bottom: 2px solid var(--couleur-primaire);
}
```

- `text-transform: uppercase;` = Convertit le texte en MAJUSCULES
- `letter-spacing: 0.12em;` = Écartement entre les lettres
- `font-weight: 700;` = Très gras
- `border-bottom: 2px solid` = Bordure bleue sous le titre (ligne de séparation)

---

### **1️⃣1️⃣ SECTION EXPÉRIENCES**

```css
#experiences article {
    padding: var(--espace-md);
    background-color: var(--couleur-fond-page);
    border-radius: 6px;
    border-left: 3px solid var(--couleur-secondaire);
    margin-bottom: var(--espace-md);
}
```

- `#experiences` = Cible l'élément avec `id="experiences"`
- `border-left: 3px solid` = Bande bleue à gauche (style moderne)
- Chaque article (expérience) a un fond légèrement teinté

```css
#experiences article:last-child {
    margin-bottom: 0;
}
```

- Supprime l'espacement du dernier article

---

### **1️⃣2️⃣ SECTION FORMATIONS (Avec Compteur)**

```css
#formation ol {
    list-style: none;
    padding-left: 0;
    counter-reset: formation-counter;
}
```

- `list-style: none;` = Supprime les chiffres par défaut des listes ordonnées
- `counter-reset: formation-counter;` = Initialise un compteur personnalisé à 0

```css
#formation li::before {
    content: counter(formation-counter);
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 26px;
    height: 26px;
    background-color: var(--couleur-primaire);
    color: #FFFFFF;
    border-radius: 50%;
    font-size: 0.75rem;
    font-weight: 700;
    text-align: center;
    line-height: 26px;
}
```

- `::before` = Ajoute du contenu avant chaque élément de liste
- `counter-increment:` = Augmente le compteur (1, 2, 3...)
- `content: counter(formation-counter);` = Affiche le numéro du compteur
- `position: absolute; left: 0;` = Positionne le numéro à gauche
- `transform: translateY(-50%);` = Centre verticalement
- `border-radius: 50%;` = Transforme le carré en cercle bleu avec le numéro dedans

---

### **1️⃣3️⃣ ASIDE (BARRE LATÉRALE)**

```css
#profil {
    background-color: var(--couleur-primaire) !important;
    border: none !important;
}
```

- `!important` = Force l'application de ce style (écrase les autres règles)
- Le profil a un fond bleu primaire au lieu du blanc

```css
#profil h2 {
    color: #FFFFFF !important;
    border-bottom-color: rgba(255, 255, 255, 0.3) !important;
}

#profil p {
    color: rgba(255, 255, 255, 0.88);
}
```

- Le texte du profil est blanc/semi-blanc sur fond bleu
- `rgba(255, 255, 255, 0.88)` = Blanc avec 88% d'opacité (0 = invisible, 1 = opaque)

---

### **1️⃣4️⃣ COMPÉTENCES ET LANGUES**

```css
#langues dl {
    font-size: 0.88rem;
}

#langues dt {
    font-weight: 600;
    color: var(--couleur-texte-fort);
    margin-top: var(--espace-sm);
}

#langues dd {
    margin-left: var(--espace-md);
    color: var(--couleur-texte);
}
```

- `dl, dt, dd` = Liste de définitions HTML
- `dt` = Terme (ex: "Français")
- `dd` = Définition (ex: "Courant")
- `margin-left:` = Indente la description

---

### **1️⃣5️⃣ LOGICIELS (Avec Puces Personnalisées)**

```css
#logiciels li::before {
    content: "‣";
    position: absolute;
    left: 0;
    color: var(--couleur-secondaire);
}
```

- `content: "‣";` = Utilise une puce personnalisée (le caractère ‣)
- `position: absolute; left: 0;` = La puce est positionnée à gauche

---

### **1️⃣6️⃣ QUALITÉS (Badges)**

```css
#qualities li {
    background-color: var(--couleur-primaire);
    color: #FFFFFF;
    font-size: 0.78rem;
    padding: var(--espace-xs) var(--espace-sm);
    border-radius: 20px;
    margin-bottom: 0;
    transition: background-color 0.2s ease, transform 0.1s ease;
}

#qualities li:hover {
    background-color: var(--couleur-secondaire);
    transform: translateY(-1px);
}
```

- `border-radius: 20px;` = Arrondit beaucoup = crée des **badges/pilules**
- `display: flex; flex-wrap: wrap; gap:` = Les badges s'arrangent en ligne flexible
- `:hover` = Au survol, changement de couleur et montée légère (`translateY(-1px)`)

---

### **1️⃣7️⃣ RÉSEAUX SOCIAUX**

```css
#reseaux a {
    display: block;
    padding: var(--espace-sm) 0;
    padding-left: var(--espace-md);
    font-size: 0.88rem;
    font-weight: 600;
    color: var(--couleur-secondaire);
    text-decoration: none;
    position: relative;
    transition: padding-left 0.2s ease, color 0.2s ease;
}

#reseaux a::before {
    content: "‣";
    position: absolute;
    left: 0;
    color: var(--couleur-secondaire);
}

#reseaux a:hover {
    color: var(--couleur-primaire);
    padding-left: 1.4rem;
}
```

- Les liens ont une puce devant
- `:hover` = Augmente le `padding-left` (l'animation fait glisser le texte à droite)

---

### **1️⃣8️⃣ PIED DE PAGE (footer)**

```css
footer {
    clear: both;
    text-align: center;
    padding: var(--espace-md);
    margin-top: var(--espace-md);
    background-color: var(--couleur-fond-blanc);
    border-top: 3px solid var(--couleur-primaire);
    border-radius: 8px;
    font-size: 0.8rem;
    color: #888780;
}
```

- Fond blanc avec bordure bleue en haut
- Texte petit et gris
- Centré

---

## 📚 Résumé des Concepts Clés

| Concept | Signification | Exemple |
|---------|---------------|---------|
| **Sélecteur** | Cible les éléments HTML | `h1`, `.class`, `#id`, `*` |
| **Propriété** | Ce qu'on change | `color`, `font-size`, `margin` |
| **Valeur** | La valeur de la propriété | `16px`, `red`, `0.5rem` |
| **Pseudo-classe** | État spécial | `:hover`, `:focus`, `:last-child` |
| **Pseudo-élément** | Contenu ajouté | `::before`, `::after` |
| **Unités** | Mesures | `px` (pixels), `rem` (relatif) |
| **Flexbox** | Disposition flexible | `display: flex`, `flex-wrap: wrap` |
| **Float** | Disposition ancienne | `float: left`, `float: right` |
| **Variables** | Valeurs réutilisables | `--couleur-primaire`, `var(--couleur-primaire)` |

---

## 🎯 Comment Modifier le CSS

1. **Changer les couleurs** : Modifiez les valeurs hexadécimales en haut du fichier (`:root`)
2. **Changer les espacements** : Modifiez les variables `--espace-*`
3. **Changer les polices** : Modifiez `--police-titres` ou `--police-texte`
4. **Ajouter une section** : Duplicez un bloc de code et adaptez l'ID

---

**Créé pour le Sprint 03 - IMeN Bénin** 💡
