# HP-READY PMIS

**Unified Project Management Information System**
Himachal Pradesh Resilient & Efficient Action for Development Yield

![License](https://img.shields.io/badge/license-GoHP--Internal-blue)
![Status](https://img.shields.io/badge/status-Active-green)
![World Bank](https://img.shields.io/badge/funded%20by-World%20Bank-blue)

---

## Overview

HP-READY PMIS is the unified web portal for monitoring and managing Himachal Pradesh's ₹1,150 Cr disaster recovery programme funded by the World Bank. It consolidates data from all four implementing agencies across 12 districts into a single source of truth.

### Key Features

| Module | Description |
|--------|-------------|
| **Executive Dashboard** | At-a-glance KPIs, disbursement trends, risk alerts, intervention registry |
| **Project Management** | 8-stage journey tracking, PIU performance scorecards, governance calendar |
| **Procurement** | HP Govt procurement methods, STEP sync status, seasonal risk tracking |
| **Financial Management** | Fund flow tracking (WB → Treasury → Dept → Vendor), IUFR tracker |
| **M&E & Reporting** | Results framework, automated reports, PMC team deployment tracker |
| **Safeguards & GRM** | Digital grievance redress, ESF instrument tracking, OHS compliance |
| **Knowledge Management** | Case studies (criteria-based), LMS platform, training calendar |
| **Report Downloads** | Time-selectable report downloads with custom report generator |

### Implementing Agencies

- **PWD** — Roads, bridges, infrastructure
- **Jal Shakti Vibhag** — Water supply, irrigation, sanitation
- **Department of Energy** — Power transmission, micro-hydro
- **Department of Rural Development** — Livelihood programmes

---

## Quick Start

### Prerequisites

- [Node.js](https://nodejs.org/) v18 or higher
- npm v9+ (comes with Node.js)

### Local Development

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/hp-ready-pmis.git
cd hp-ready-pmis

# Install dependencies
npm install

# Start development server
npm run dev
```

The portal will open at `http://localhost:3000`

### Build for Production

```bash
npm run build
```

Output will be in the `dist/` folder.

### Preview Production Build

```bash
npm run preview
```

---

## Deployment

### Option 1: GitHub Pages (Recommended — Free)

This repository includes automatic GitHub Pages deployment via GitHub Actions.

**Steps:**

1. Push this repository to GitHub
2. Go to **Settings → Pages**
3. Under "Build and deployment", select **GitHub Actions**
4. Push to `main` branch — the site deploys automatically

**Your site will be live at:**
```
https://YOUR_USERNAME.github.io/hp-ready-pmis/
```

> **Important:** If your repository name differs from `hp-ready-pmis`, update the `base` path in `vite.config.js`:
> ```js
> base: '/your-repo-name/',
> ```

### Option 2: Vercel (One-Click)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

1. Click the button above or go to [vercel.com](https://vercel.com)
2. Import your GitHub repository
3. Vercel auto-detects Vite — no config needed
4. For Vercel, change `base` in `vite.config.js` to `'/'`

### Option 3: Netlify

1. Go to [netlify.com](https://netlify.com) → "Add new site" → "Import from Git"
2. Connect your GitHub repo
3. Build command: `npm run build`
4. Publish directory: `dist`
5. For Netlify, change `base` in `vite.config.js` to `'/'`

### Option 4: Custom Server / NIC Cloud

```bash
# Build the static files
npm run build

# The dist/ folder contains all static files
# Upload to any web server (Apache, Nginx, NIC hosting)
```

For NIC/Gov hosting, set `base: '/'` in `vite.config.js` if deploying to root domain.

**Nginx sample config:**
```nginx
server {
    listen 80;
    server_name pmis.hp.gov.in;
    root /var/www/hp-ready-pmis/dist;
    index index.html;
    
    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

---

## Project Structure

```
hp-ready-pmis/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Pages auto-deploy
├── public/
│   └── favicon.svg             # HP-READY favicon
├── src/
│   ├── App.jsx                 # Main portal application (all 8 tabs)
│   ├── main.jsx                # React entry point
│   └── index.css               # Global styles
├── index.html                  # HTML entry point
├── package.json                # Dependencies & scripts
├── vite.config.js              # Build configuration
├── .gitignore                  # Git ignore rules
├── LICENSE                     # License
└── README.md                   # This file
```

---

## PMC Team

| Name | Role |
|------|------|
| Amit Tandon | Team Leader |
| Sunil Kashyap | Procurement Specialist |
| Shilpa Sharma | Financial Management |
| Anshul Tyagi | Environment Safeguards |
| Annie George | Social Safeguards |
| Manish Sen | QA/QC Specialist |
| Rohan Shinde | DRM Specialist |
| Anil Joshi | MIS/IT Specialist |
| Navneet Anand | Communication Specialist |
| Sakshi Bhutani | Training & Capacity Building |

---

## Tech Stack

- **React 18** — UI framework
- **Recharts** — Data visualization (charts & graphs)
- **Vite 5** — Build tool (fast HMR, optimized builds)
- **GitHub Actions** — CI/CD pipeline
- **GitHub Pages** — Static hosting

---

## Data Note

This portal currently contains **illustrative data** for demonstration purposes. In production, it will connect to:

- **Himkosh / IFMIS** — State treasury financial data
- **WB STEP** — Procurement tracking
- **HP e-Tender / GeM** — Procurement platforms
- **Departmental MIS** — PIU-level data feeds
- **Mobile App** — Field inspection data (offline-first)

---

## Support

For technical issues, contact the MIS/IT Specialist (Anil Joshi) via the PMC team.

---

*Government of Himachal Pradesh • Department of Revenue • World Bank Funded*
