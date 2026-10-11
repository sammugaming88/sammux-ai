# GitHub se SAMMUX AI host karna — step by step (beginner friendly)

GitHub se hosting ke **do tarike** hain. Dono ke steps niche diye hain.

| | Option A — GitHub Pages | Option B — Render (GitHub se) |
|---|---|---|
| Kya host hota hai | Sirf **website** (static) | **Website + server** (AI) |
| Key | User se nahi (Free mode) | Key **server pe** (best quality) |
| Time | ~5 minute | ~10 minute |
| URL | `https://<username>.github.io/<repo>/` | `https://<name>.onrender.com` |

---

## Option A — GitHub Pages (sabse aasan, phone se bhi ho jayega)

Isme app **Free mode** me chalti hai — user se koi key nahi maangi jaati.

1. **github.com** pe account banao / login karo.
2. Top-right **+** → **New repository**.
   - Repository name: `sammux-ai`
   - **Public** chuno
   - **Create repository**
3. Repo ke andar **Add file → Upload files** → apni **index.html** upload karo → neeche **Commit changes**.
   - Zaroori: file ka naam **`index.html`** hi ho, aur **root** (top level) me ho.
4. Repo me **Settings → Pages**.
   - **Source:** `Deploy from a branch`
   - **Branch:** `main` , folder **`/ (root)`** → **Save**
5. 1–2 minute ruko, page refresh karo — upar ek URL aa jayega:
   **`https://<tumhara-username>.github.io/sammux-ai/`**
   Wahi link kholo → app chalu. (HTTPS hai, to phone pe **Add to Home screen** se app ki tarah install bhi ho jayegi.)

> GitHub Pages sirf **website** host karta hai (Node server nahi chalta) — isliye ye **Free mode** chalega. User se koi key nahi maangi jayegi.

---

## Option B — Render (backend bhi, key server pe — best quality)

1. `sammux-ai.zip` **unzip** karo. Usme ye files hain:
   `index.html`, `server.js`, `package.json`, `render.yaml`, `DEPLOY.md`, `.env.example`, `Dockerfile`, `manifest.webmanifest`, `sw.js`, aur icon files.
2. GitHub pe **naya repo** banao aur **saari files upload karo** (Option A ke step 3 jaisa hi: Add file → Upload files). Sab **root** me rakho.
3. **render.com** → **Get Started** → **Sign in with GitHub** → allow karo.
4. **New → Web Service** → apna repo **Connect** karo. Phir:
   - **Name:** `sammux-ai`
   - **Environment:** `Node`
   - **Build Command:** *(khali chhod do)*
   - **Start Command:** `node server.js`
5. **Environment Variables** → **Add**:
   - Key: `GEMINI_API_KEY` , Value: tumhari key
   - *(optional)* Key: `POLLINATIONS_API_KEY` , Value: tumhari free key
6. **Create Web Service** → 1–2 minute → URL milega: **`https://sammux-ai.onrender.com`** → kholo → app chalu.
   Ab **user se koi key nahi maangi jayegi** — key sirf server pe rehti hai.

### Option B ka shortcut — Blueprint
Render → **New → Blueprint** → repo chuno → `render.yaml` auto-detect ho jayega → **Deploy**. Bas `GEMINI_API_KEY` daal do.

---

## Common galtiyan (dhyaan rakho)
- `index.html` **root** me hona chahiye (kisi folder ke andar nahi).
- GitHub Pages ke liye repo **Public** hona chahiye.
- Render me **Start Command** `node server.js` hona chahiye.
- Render ki **free** service thodi der "sleep" karti hai — pehli baar kholne me 30–50 sec lag sakta hai.
- File upload karne ke baad **Commit changes** dabana mat bhoolna.

## Key kahan se milegi (Option B ke liye)
Free Google Gemini key: **aistudio.google.com/apikey**
(Optional) free Pollinations key: **enter.pollinations.ai**
