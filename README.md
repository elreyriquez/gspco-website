# Grant Stewart Phillips & Co — Website

A static website for Grant Stewart Phillips & Co, built for deployment on GitHub Pages.

## Local Preview

Open `index.html` in a browser, or run a local server:

```bash
# Python
python3 -m http.server 8000

# Node (npx)
npx serve .
```

Then visit `http://localhost:8000`

## Deploy to GitHub Pages

1. **Create a GitHub repo** (e.g. `gspco-website`)

2. **Push this code**:
   ```bash
   cd gspco-website
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Repo → **Settings** → **Pages**
   - Source: **Deploy from a branch**
   - Branch: `main` / root (`/`)
   - Save

4. **Your site will be live at**:
   - `https://YOUR_USERNAME.github.io/YOUR_REPO/`

## Point Your Domain (gspco.net) via GoDaddy DNS

### Option A: Use custom domain with GitHub Pages

1. **Add CNAME file** (for root domain):
   - Create a file named `CNAME` in the root of this project
   - Add one line: `gspco.net` (or `www.gspco.net` if you prefer www)

2. **In GitHub**:
   - Repo → Settings → Pages
   - Custom domain: `gspco.net` (or `www.gspco.net`)
   - Enable **Enforce HTTPS** after DNS propagates

3. **In GoDaddy DNS** (for root `gspco.net`):
   - Add/Edit **A records**:
     - `@` → `185.199.108.153`
     - `@` → `185.199.109.153`
     - `@` → `185.199.110.153`
     - `@` → `185.199.111.153`
   - Add **CNAME record**:
     - `www` → `YOUR_USERNAME.github.io`

4. **If using www only**:
   - CNAME: `www` → `YOUR_USERNAME.github.io`
   - Then set custom domain in GitHub to `www.gspco.net`

### Option B: Use Netlify or Vercel (free alternatives)

Both support custom domains and can deploy from your GitHub repo:

- **Netlify**: Connect repo → automatic deploys. Add domain in Domain settings.
- **Vercel**: Same process. Add domain in Project Settings.

For GoDaddy:
- **A record** `@` → Netlify/Vercel IP (check their docs)
- **CNAME** `www` → your Netlify/Vercel subdomain

## DNS propagation

Changes can take 24–48 hours. Check status at [dnschecker.org](https://dnschecker.org).

## Project structure

```
gspco-website/
├── index.html          # Home
├── practice-areas.html
├── attorneys.html
├── contact.html
├── css/
│   └── styles.css
└── README.md
```
