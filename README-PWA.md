# Reflektionskort PWA

## 📱 Vad är en PWA?

En Progressive Web App (PWA) är en webbapp som fungerar som en vanlig app på din telefon eller dator. Den kan:
- Installeras på hemskärmen
- Fungera offline
- Skicka notifikationer (om du vill)
- Ladda snabbare

## 🚀 Installation

### För GitHub Pages:

1. **Ladda upp alla filer till ditt GitHub repository:**
   - index.html
   - barn.html
   - familj.html
   - tonaring.html
   - vanner.html
   - parrelation.html
   - manifest.json
   - service-worker.js
   - icon-192.png (skapa med create-icons.html)
   - icon-512.png (skapa med create-icons.html)

2. **Aktivera GitHub Pages:**
   - Gå till Settings → Pages
   - Välj main branch som källa
   - Din app blir tillgänglig på: `https://dittanvändarnamn.github.io/dittrepo/`

### För lokal testning:

```bash
# Installera en enkel webbserver
npm install -g http-server

# Starta servern i mappen med dina filer
http-server -p 8080

# Öppna i webbläsaren
open http://localhost:8080
```

## 📲 Installera på telefon

### iPhone/iPad:
1. Öppna sidan i Safari
2. Tryck på delnings-ikonen (📤)
3. Scrolla ner och välj "Lägg till på hemskärmen"
4. Ge appen ett namn och tryck "Lägg till"

### Android:
1. Öppna sidan i Chrome
2. Tryck på menyn (⋮)
3. Välj "Installera app" eller "Lägg till på hemskärmen"
4. Bekräfta installationen

### Dator (Chrome/Edge):
1. Öppna sidan i Chrome eller Edge
2. Klicka på installations-ikonen i adressfältet (➕ eller 💻)
3. Klicka "Installera"

## 🎨 Skapa ikoner

1. Öppna `create-icons.html` i din webbläsare
2. Två PNG-filer laddas ner automatiskt:
   - icon-192.png
   - icon-512.png
3. Lägg dessa i samma mapp som dina andra filer

### Eller skapa egna ikoner:
- Storlekar: 192x192px och 512x512px
- Format: PNG med transparent bakgrund (eller färgad)
- Naming: icon-192.png och icon-512.png

## 🔧 Anpassa PWA

### Ändra färger i manifest.json:
```json
{
  "theme_color": "#007AFF",     // Färg i statusfältet
  "background_color": "#ffffff"  // Bakgrundsfärg när appen startar
}
```

### Ändra app-namn:
```json
{
  "name": "Ditt Namn",           // Fullständigt namn
  "short_name": "Kort Namn"      // Visas under ikonen
}
```

## ✅ Testa att det fungerar

1. Öppna Developer Tools (F12)
2. Gå till "Application" eller "Programtillägg"
3. Kontrollera:
   - ✓ Manifest laddas korrekt
   - ✓ Service Worker är registrerad
   - ✓ Ikoner visas

## 🌐 HTTPS krävs!

PWA kräver HTTPS för att fungera (utom på localhost). GitHub Pages använder automatiskt HTTPS, så det fungerar perfekt där!

## 📝 Viktiga filer

- **manifest.json**: Definierar hur appen ser ut och beter sig
- **service-worker.js**: Hanterar offline-funktionalitet och caching
- **icon-192.png & icon-512.png**: App-ikoner

## 🔄 Uppdatera din PWA

När du gör ändringar:

1. Ändra `CACHE_NAME` i service-worker.js (t.ex. 'reflektionskort-v2')
2. Ladda upp de uppdaterade filerna
3. Användare får automatiskt uppdateringen nästa gång de öppnar appen

## 🐛 Felsökning

**Appen installeras inte:**
- Kontrollera att du använder HTTPS (eller localhost)
- Kolla att manifest.json är korrekt formaterad
- Se till att ikonerna finns

**Offline fungerar inte:**
- Kolla att service-worker.js är registrerad
- Öppna DevTools → Application → Service Workers
- Tryck "Update" för att ladda om

**Ändringar syns inte:**
- Rensa cacheminnet (DevTools → Application → Clear storage)
- Eller ändra CACHE_NAME i service-worker.js

## 💡 Tips

- Test alltid på riktiga enheter, inte bara desktop
- Använd Lighthouse (i Chrome DevTools) för att testa PWA-kvalitet
- Håll ikonerna enkla och tydliga
- Test offline-funktionalitet genom att stänga av wifi

## 📚 Mer information

- [PWA Dokumentation](https://web.dev/progressive-web-apps/)
- [Manifest Generator](https://www.simicart.com/manifest-generator.html/)
- [Icon Generator](https://realfavicongenerator.net/)
