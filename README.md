# Landing page — Guide Meta Ads (Eagle Eye Digital)

Page de téléchargement du lead magnet « Pilotez vos pubs Meta comme un pro, sans agence ».
Site statique : aucune installation, aucun serveur, aucun coût. Hébergeable tel quel sur GitHub Pages.

## Ce qu'il y a dans le dossier

| Fichier | Rôle |
|---|---|
| `index.html` | La page. Tout est dedans : texte, design, structure. Aucun fichier CSS ou JS externe |
| `guide-pilotez-vos-pubs-meta.pdf` | Le guide téléchargé par le visiteur (22 pages) |
| `og-image.png` | L'image affichée quand le lien est partagé sur LinkedIn |
| `.nojekyll` | Fichier technique vide. Il évite que GitHub reformate la page. Ne pas le supprimer |
| `README.md` | Cette notice. Elle ne s'affiche pas sur le site |

---

## 1. Créer le dépôt

1. Aller sur [github.com](https://github.com) et se connecter (créer un compte gratuit si besoin)
2. Cliquer sur le **+** en haut à droite → **New repository**
3. **Repository name** : `guide-meta-ads` (ce nom apparaîtra dans l'adresse de la page)
4. Cocher **Public** — obligatoire pour que la page soit visible gratuitement
5. Cliquer **Create repository**

## 2. Envoyer les fichiers

1. Sur la page du dépôt : **Add file** → **Upload files**
2. Glisser les **5 fichiers** du dossier (y compris `.nojekyll` et `README.md`)
3. Cliquer **Commit changes** en bas

> Si `.nojekyll` refuse de partir avec les autres : envoyez-le seul dans un second upload. Sur Mac, les fichiers commençant par un point sont cachés dans le Finder — faire `Cmd + Shift + .` pour les afficher.

## 3. Activer la mise en ligne

1. Onglet **Settings** du dépôt → menu **Pages** dans la colonne de gauche
2. **Source** : *Deploy from a branch*
3. **Branch** : `main` et dossier `/ (root)` → **Save**
4. Attendre une à deux minutes, recharger la page : l'adresse s'affiche en haut

Elle ressemble à `https://votre-compte.github.io/guide-meta-ads/`

## 4. Corriger l'aperçu LinkedIn — important

Tant que cette étape n'est pas faite, le lien partagé sur LinkedIn s'affichera sans visuel.

1. Dans le dépôt, cliquer sur `index.html` → l'icône **crayon** (Edit)
2. Chercher les **3 lignes** qui contiennent `VOTRE-COMPTE.github.io/VOTRE-DEPOT` (elles sont regroupées tout en haut du fichier, signalées par un commentaire)
3. Remplacer à chaque fois par votre adresse réelle, par exemple `https://karen.github.io/guide-meta-ads`
4. **Commit changes**

Ensuite, pour forcer LinkedIn à recharger l'aperçu : coller l'adresse dans le [Post Inspector de LinkedIn](https://www.linkedin.com/post-inspector/) et cliquer *Inspect*. À faire une fois avant de publier le post, sinon LinkedIn garde en mémoire l'ancienne version pendant plusieurs jours.

## 5. Mettre votre photo à la place du « K »

1. Envoyer votre photo dans le dépôt (**Add file** → **Upload files**), nommée `karen.jpg`
2. Éditer `index.html`, chercher `<div class="photo">K</div>`
3. Remplacer cette ligne par :

```html
<div class="photo"><img src="karen.jpg" alt="Karen"></div>
```

Une photo carrée d'au moins 300 x 300 px donne le meilleur résultat (elle sera affichée en rond).

## 6. Activer le formulaire Systeme.io (plus tard, si vous voulez capter des emails)

Un bloc newsletter est déjà écrit dans la page, mais désactivé. Pour l'activer :

1. Dans Systeme.io, créer le formulaire d'inscription et copier son code d'intégration
2. Éditer `index.html` et chercher `BLOC NEWSLETTER SYSTEME.IO`
3. Remplacer la ligne `COLLEZ ICI LE CODE DU FORMULAIRE SYSTEME.IO` par le code copié
4. Supprimer la ligne qui contient seulement `<!--` (juste après le cadre d'explication) et la ligne qui contient seulement `-->` (juste avant `<footer>`)

Le téléchargement du guide reste libre : le formulaire est un bonus, pas une barrière.

## 7. Mettre à jour le guide plus tard

Envoyer le nouveau PDF avec **exactement le même nom de fichier** (`guide-pilotez-vos-pubs-meta.pdf`) : il remplacera l'ancien et le bouton de téléchargement continuera de fonctionner sans rien changer d'autre.

---

## Utiliser un nom de domaine à vous (optionnel)

Par exemple `guide.eagleeye.digital` au lieu de l'adresse github.io :

1. Chez votre hébergeur de domaine, créer un enregistrement **CNAME** : nom `guide`, valeur `votre-compte.github.io`
2. Dans GitHub : **Settings** → **Pages** → **Custom domain** → saisir `guide.eagleeye.digital` → **Save**
3. Cocher **Enforce HTTPS** une fois que c'est validé (peut prendre jusqu'à 24 h)
4. Refaire l'étape 4 avec la nouvelle adresse

## Suivre le trafic (optionnel)

GitHub Pages ne fournit aucune statistique. Pour savoir combien de personnes téléchargent le guide, coller un code de suivi (Google Analytics, Plausible, Umami) juste avant la ligne `</head>` dans `index.html`.
