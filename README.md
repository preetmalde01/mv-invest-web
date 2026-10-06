# MV Invest — Your Personal CIO (Web Suite)

Independent, fee-only wealth advisory web suite for **MV Invest** (a Malde Ventures entity), featuring Swiss minimalist editorial typography, a live interactive ambient orange glow canvas, and complete regulatory disclosures.

---

## Quickstart: Running Locally Without Publishing

This project is configured to run completely on your local machine with zero external deployment or public hosting.

### Option 1: Running the React App (Recommended for Development)

The `react-app/` directory is built with **React 18**, **Vite**, and **Tailwind CSS**.

```bash
# 1. Navigate to the React app folder
cd react-app

# 2. Install dependencies
npm install

# 3. Start local development server
npm run dev
```

* Your local development server will start at `http://localhost:3000` (or `http://localhost:5173`).
* Open your browser and navigate to the address shown in your terminal.
* It runs strictly on your machine (`localhost`) and is **not published** to the internet.
* Features instant Hot Module Replacement (HMR) for live editing.

---

### Option 2: Running the Standalone Static Edition (Zero Dependencies)

The `standalone/` directory requires **no package installations or build tools**.

```bash
# 1. Navigate to the standalone folder
cd standalone

# 2. Run a local HTTP server using Python (built-in on macOS/Linux):
python3 -m http.server 8000

# Or using Node:
npx serve .
```

* Open `http://localhost:8000` in your browser.
* Alternatively, on macOS you can simply run:
  ```bash
  open index.html
  ```
  or double-click `index.html` to open it directly in Safari, Chrome, or Edge.

---

## Pushing to a Private GitHub Repository

To back up and manage this codebase on GitHub without publishing it publicly:

### Step 1: Create a New Private Repository on GitHub
1. Log in to [GitHub](https://github.com).
2. Click the **`+`** icon in the top right corner and select **New repository**.
3. Set the **Repository name** (e.g., `mv-invest-web`).
4. Select **Private** (ensures your code and website remain confidential and unpublished).
5. Leave "Add a README file", ".gitignore", and "Choose a license" **unchecked** (we already provide these).
6. Click **Create repository**.

### Step 2: Push Your Local Code to GitHub
In your local project root directory (where this `README.md` and `.git` are located):

```bash
# 1. Add your GitHub repository as the remote origin
# (Replace YOUR_USERNAME and YOUR_REPO with your actual details)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git

# 2. Ensure your default branch is named 'main'
git branch -M main

# 3. Push all commits to your private GitHub repo
git push -u origin main
```

*(If you use the GitHub CLI, you can do this in one command from the project root:)*
```bash
gh repo create mv-invest-web --private --source=. --push
```

---

## Project Structure

```
├── .gitignore              # Ignores node_modules, build artifacts, and system files
├── README.md               # Repository documentation and local setup guide
├── react-app/              # Component-driven React 18 + Vite + Tailwind application
│   ├── index.html          # HTML entry point with Google Fonts (Syne, Plus Jakarta Sans)
│   ├── package.json        # Dependencies and scripts (dev, build, preview)
│   ├── vite.config.js      # Vite build configuration
│   ├── tailwind.config.js  # Custom theme extensions and color tokens
│   ├── postcss.config.js   # PostCSS configuration
│   ├── public/             # Static public assets
│   └── src/
│       ├── App.jsx         # Root app layout & theme state management
│       ├── main.jsx        # React DOM mount point
│       ├── index.css       # Global styles, Tailwind directives, slider styling
│       ├── assets/         # Vector brand assets (logo.svg)
│       └── components/     # Modular UI components:
│           ├── Hero.jsx            # "YOUR PERSONAL CIO" headline & primary CTA
│           ├── GlowCanvas.jsx      # Live interactive orange ambient glow canvas
│           ├── Mandate.jsx         # 01 / Mandate fiduciary comparison
│           ├── WhyAdvisory.jsx     # 02 / Transparency conflict audit cards
│           ├── Calculator.jsx      # 03 / Mathematical commission leak slider
│           ├── Solutions.jsx       # 04 / Architecture across wealth tiers
│           ├── HowWeWork.jsx       # 05 / Process 4-step advisory protocol
│           ├── ContactForm.jsx     # 06 / Engage consultation request form
│           └── Footer.jsx          # Compliance and regulatory SEBI RIA disclosures
│
└── standalone/             # Zero-dependency static build (pure HTML5, CSS3, ES6)
    ├── index.html          # Semantic markup with adaptive inline SVGs
    ├── css/
    │   └── styles.css      # Swiss minimalist layout, responsive grid, dark/light theme
    ├── js/
    │   └── main.js         # Particle canvas physics, theme toggle, commission calculator
    └── assets/
        └── logo.svg        # Scalable vector logo badge
```

---

## Design System & Branding Tokens

* **Headline Typography:** `Syne` (Bold `700` on hero headline).
* **Body & Section Typography:** `Plus Jakarta Sans` (`500` / `600` on section headings).
* **Technical Labels & Monospace:** `JetBrains Mono`.
* **Theme Colors:**
  * **Light Mode (Default):** Studio Grey `#E2E2E4`, Dark Text `#0A0A0A`.
  * **Dark Mode:** Obsidian `#090C12`, White Text `#FFFFFF`.
  * **Core Glow Accent:** Vibrant Coral Orange `#F36F43` / `#FF5722`.
* **Logo:** Adaptive inline SVG that automatically responds to light and dark modes with `currentColor`.
