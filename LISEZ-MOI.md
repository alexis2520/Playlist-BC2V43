# Playlist BCV 43 : mise en ligne

## Mise à jour depuis la version précédente
1. **Firebase → Firestore → Règles** : remplace par ceci, puis **Publier** (nouvelle collection `players` pour le questionnaire) :
```
rules_version = '2';
service cloud.firestore {
  match /databases/{db}/documents {
    match /songs/{id} { allow read, write: if true; }
    match /players/{id} { allow read, write: if true; }
  }
}
```
2. **GitHub** : ouvre ton dépôt → **Add file → Upload files** → dépose le nouvel `index.html` (il remplace l'ancien). Ton `config.js` est déjà rempli, tu peux le redéposer tel quel.
3. Attends 1 à 2 min, puis recharge le site (sur téléphone, ferme et rouvre l'appli).

## Accès admin
Touche **5 fois le logo**, ou le petit lien « Espace organisateur » tout en bas de la page.

## Première installation
Voir les étapes Firebase / GitHub Pages / ntfy de la version précédente : config.js est déjà prêt.

## À savoir
Le code admin protège l'écran admin, pas la base de données : suffisant pour un club, mais pas inviolable. Les réponses au questionnaire sont lisibles techniquement par quelqu'un qui sait fouiller.
