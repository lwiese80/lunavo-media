# Lunavo Media — Landingpage

## Dateien
- `index.html` — Komplette One-Pager Landingpage (single file, kein Build nötig)
- `logo.png` — Hier dein Logo ablegen
- `profil.jpg` — Profilbild für "Über mich"-Sektion

## Anpassungen

### Kontaktformular
Das Formular hat aktuell `action="#"`. Für echte Funktionalität:
1. **Formspree**: `action="https://formspree.io/f/DEINE_ID"` + `method="POST"`
2. **IONOS Webmailer**: PHP-Script oder IONOS eigenes Kontaktformular-Tool

### E-Mail-Adresse
Aktuell `info@lunavomedia.de` — bei Bedarf anpassen.

## Deployment auf IONOS

### Option 1: IONOS Webspace (empfohlen)
1. Im IONOS Kundencenter einloggen
2. **Hosting → Webspace** öffnen
3. Per **WebFTP** oder **SFTP** verbinden:
   - Host: Steht in IONOS unter "SFTP-Zugang"
   - User/Passwort: Aus IONOS Zugangsdaten
4. `index.html` (+ `logo.png`, `profil.jpg`) ins Root-Verzeichnis hochladen
5. Domain auf den Webspace zeigen lassen (DNS A-Record auf IONOS-IP)

### Option 2: IONOS Deploy Now (Git-basiert)
1. Repo auf GitHub pushen
2. In IONOS "Deploy Now" → GitHub verbinden → Repo auswählen
3. Automatisches Deployment bei jedem Push

### SSL
- IONOS bietet kostenloses SSL (Let's Encrypt) — in den Domain-Einstellungen aktivieren
- HTTPS erzwingen via `.htaccess`:
```apache
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

### Performance
Die Seite lädt externe Ressourcen (Google Fonts, Font Awesome). Für maximale Performance optional lokal hosten.

## Impressum & Datenschutz
`impressum.html` und `datenschutz.html` müssen noch erstellt werden. Pflicht für deutsche Websites!
→ Generator: https://www.e-recht24.de/impressum-generator.html
