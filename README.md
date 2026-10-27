# Pubcrawl Milan 2026

Het pubgolf-spel voor zaterdag 31 oktober, als gewone website (GitHub Pages).

- `index.html` – het hele spel (gegenereerd, niet met de hand aanpassen).
- `firebase-config.js` – de Firebase web-config. Zolang deze `null` is, werkt het spel per telefoon; met een config zijn scores, teamnamen, quiz, finale, drankjes en foto's live op alle telefoons.

Firestore-regels (Firebase console → Firestore → Rules):

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /games/{game}/{document=**} {
      allow read, write: if true;
    }
  }
}
```
