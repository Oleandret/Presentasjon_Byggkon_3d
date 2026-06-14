# Byggkon AI — Produktlansering 🚀

En interaktiv 3D-presentasjon (Three.js) som lanserer Byggkons tre AI-agenter:

| Agent | Rolle | Lenke |
|-------|-------|-------|
| **Nova** | Fagassistent — byggfag, regelverk og rutiner (TEK17, NS-standarder, SINTEF) | [nova-ai-agent-bygg-kon-production.up.railway.app](https://nova-ai-agent-bygg-kon-production.up.railway.app/) |
| **Loki** | Privat AI-kunnskapsmotor over OneDrive/SharePoint, inkl. AutoCAD-tegninger | [byggkon-loki-ai-production.up.railway.app](https://byggkon-loki-ai-production.up.railway.app/) |
| **Hilde** | Eiendomsagent — eierinfo og oppslag i Kartverkets matrikkel | — |

## Navigering

- **Piltaster** ← → (eller ↑ ↓ / mellomrom) for å bla
- **Scroll**, **sveip** (mobil) eller knappene nede til høyre
- Prikkene til venstre hopper rett til en slide

## Kjøre lokalt

Krever Node 18+. Ingen npm-avhengigheter.

```bash
npm start
# åpne http://localhost:3000
```

(Eller bare åpne `index.html` direkte i nettleseren.)

## Legg på GitHub

```bash
git init
git add .
git commit -m "Byggkon AI – 3D produktlansering"
git branch -M main
git remote add origin https://github.com/<bruker>/<repo>.git
git push -u origin main
```

## Deploy til Railway

1. Gå til [railway.app](https://railway.app) → **New Project** → **Deploy from GitHub repo**.
2. Velg dette repoet. Railway oppdager Node automatisk (Nixpacks).
3. Build/Start trengs ikke å konfigureres — `railway.json` setter:
   - Start: `npm start`
   - Helsesjekk: `/healthz`
4. Under **Settings → Networking → Generate Domain** for en offentlig URL.

Appen lytter på `process.env.PORT` (satt av Railway) og faller tilbake til `3000` lokalt.

## Struktur

```
index.html     # Hele presentasjonen (Three.js via CDN, ingen build)
server.js      # Liten statisk Node-server (kun innebygde moduler)
package.json   # start-script + Node engine
railway.json   # Railway build/deploy-config
.gitignore
```

---

© 2026 Bygg-Kon AS · Travbaneveien 3, 4031 Stavanger · [byggkon.no](https://www.byggkon.no)
