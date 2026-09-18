# OrluCodex — page de présentation

Page statique d'une seule feuille, présentant le projet **OrluCodex** (manuel in-game du serveur
Rust La Fistinière) au staff.

Aucune dépendance, aucun build, aucun framework. Un seul fichier `index.html` : tout le CSS et le
JavaScript sont en ligne, seules les polices viennent de Google Fonts.

## Mise en ligne sur GitHub Pages

1. Crée un dépôt sur GitHub (public — Pages est gratuit sur les dépôts publics).
2. Dépose `index.html`, ce `README.md` et `.nojekyll` à la racine, puis pousse sur `main`.
3. Dans le dépôt : **Settings → Pages**.
4. Sous *Build and deployment*, choisis **Deploy from a branch**, branche `main`, dossier `/ (root)`.
5. Enregistre. La page est en ligne une à deux minutes plus tard, à l'adresse :

   ```
   https://<ton-pseudo>.github.io/<nom-du-depot>/
   ```

Le fichier `.nojekyll` indique à GitHub de servir les fichiers tels quels, sans les passer par
Jekyll. Il est inutile ici mais évite des surprises si tu ajoutes plus tard un dossier commençant
par un underscore.

## Adresse personnalisée (facultatif)

Tu possèdes déjà `fistgames.fr`, donc tu peux servir la page sur un sous-domaine du type
`codex.fistgames.fr` :

1. Chez ton hébergeur DNS, ajoute un enregistrement **CNAME** :

   ```
   codex   CNAME   <ton-pseudo>.github.io.
   ```

2. Crée à la racine du dépôt un fichier nommé `CNAME` (sans extension) contenant une seule ligne :

   ```
   codex.fistgames.fr
   ```

3. Pousse, puis dans **Settings → Pages**, renseigne le domaine dans *Custom domain* et coche
   *Enforce HTTPS* une fois le certificat émis (compter jusqu'à une heure).

## Modifier la page

Tout est dans `index.html` :

- les **couleurs** sont des variables CSS dans le bloc `:root` en haut du fichier, avec leur
  équivalent sombre juste en dessous ;
- le **contenu** suit, en HTML lisible, section par section ;
- le seul script gère la bascule clair/sombre.

Un thème clair et un thème sombre sont fournis. Par défaut la page suit le réglage du système du
visiteur ; le bouton en haut à droite permet de forcer l'un ou l'autre, et le choix est retenu
dans le navigateur.

## Partage sur Discord

Les métadonnées Open Graph sont renseignées : l'aperçu affiche le titre, la description et la
couleur d'accent. Pour ajouter une vignette d'aperçu, dépose une image dans le dépôt et ajoute
dans le `<head>` :

```html
<meta property="og:image" content="https://<ton-pseudo>.github.io/<depot>/apercu.png">
```

Dimensions conseillées : 1200 × 630.
