# Playlist BCV 43 : mise en ligne (≈ 20 min, gratuit)

## 1. Base de données (Firebase)
1. Va sur console.firebase.google.com → **Ajouter un projet** (désactive Google Analytics).
2. **Build → Firestore Database → Créer** (région europe-west).
3. Onglet **Règles**, remplace tout par ceci, puis **Publier** :
```
rules_version = '2';
service cloud.firestore {
  match /databases/{db}/documents {
    match /songs/{id} { allow read, write: if true; }
  }
}
```
4. Roue dentée → **Paramètres du projet** → **Vos applications** → icône **</>** → crée l'appli web → copie `apiKey`, `authDomain`, `projectId`, `appId` dans **config.js**.
5. Dans config.js, change aussi `adminPin` (ton code admin) et `ntfyTopic` (un nom long et secret).

## 2. Héberger le site (GitHub Pages)
1. Sur github.com, crée un dépôt **public**.
2. **Add file → Upload files** : dépose le **contenu** du dossier (pas le zip).
3. **Settings → Pages → Deploy from a branch → main / (root)**. Ton lien : `https://TON-PSEUDO.github.io/NOM-DU-DEPOT/`

## 3. Notifications admin
Installe l'appli gratuite **ntfy** (iPhone/Android) → **+** → abonne-toi au sujet `ntfyTopic` de config.js.

## 4. Appli sur téléphone
Ouvre le lien sur le téléphone. **Android (Chrome)** : menu ⋮ → Installer l'application. **iPhone (Safari)** : Partager → Sur l'écran d'accueil.

## À savoir
Le code admin protège l'écran admin, pas la base : c'est suffisant pour un club, mais pas inviolable.
