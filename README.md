# DeployKit: Frontend Deployment on Vercel

A responsive React + Vite website built for the university assessment **"Frontend Deployment on Vercel"**.
It explains the deployment workflow and includes two working tools: a pre-deployment checklist and a `vercel.json` generator.

## Features
- React 18 + Vite 5, reusable components, no backend
- Fully responsive (mobile, tablet, desktop) with a working mobile menu
- Dark/light mode toggle (remembers your choice, respects system preference)
- Scroll-reveal animations, hover effects, reduced-motion support
- Interactive checklist with saved progress (localStorage)
- Config generator form with validation and copy-to-clipboard

## Project structure
```
├── index.html
├── package.json
├── vite.config.js
├── vercel.json          # build command + output directory for Vercel
├── public/favicon.svg
└── src/
    ├── main.jsx, App.jsx
    ├── components/      # Navbar, Hero, Workflow, Features, Checklist, ConfigGenerator, Footer, Reveal, SectionHeading
    ├── hooks/           # useTheme, useLocalStorage
    └── styles/index.css
```

## Run locally
Requires Node.js 18 or newer.
```bash
npm install
npm run dev        # http://localhost:5173
npm run build      # production build into dist/
npm run preview    # serve the production build locally
```

## Deploy on Vercel
1. Create a GitHub repository and push this project:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
2. Go to https://vercel.com/new and sign in with GitHub.
3. Import the repository.
4. Confirm the settings (already set by `vercel.json`):
   - Framework Preset: **Vite**
   - Build Command: `npm run build`
   - Output Directory: `dist`
5. Click **Deploy**. Every later push to `main` redeploys automatically.

No environment variables or API keys are required.
