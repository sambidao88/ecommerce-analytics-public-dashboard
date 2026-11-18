# Ecommerce Analytics Public Dashboard

Static public version of the MotherDuck Dive **Ecommerce Portfolio BI Dashboard**.

## Included
- Overview, Sales Analytics, Product & Customer
- Date, store, category, sales-channel filters
- Status filter for the order-status visual
- 35 synthetic ecommerce order-item rows exported from `md:ecommerce_portfolio`

## Run locally on Windows
Install Node.js LTS from https://nodejs.org/, extract this folder, open PowerShell here and run:

```powershell
npm install
npm run dev
```

Open the localhost URL printed by Vite (normally http://localhost:5173).

Build check:

```powershell
npm run build
npm run preview
```

## Deploy to GitHub Pages
1. Create a new GitHub repository, e.g. `ecommerce-analytics-public-dashboard`.
2. In PowerShell from this folder:

```powershell
git init
git add .
git commit -m "Build public ecommerce analytics dashboard"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/ecommerce-analytics-public-dashboard.git
git push -u origin main
```

3. GitHub repository → **Settings → Pages** → Source: **GitHub Actions**.
4. Open **Actions** and wait for the deployment workflow to finish.
5. Site URL: `https://YOUR_USERNAME.github.io/ecommerce-analytics-public-dashboard/`.

Vite uses a relative base path (`./`) for GitHub Pages project URLs.

## Data and metrics
The site uses a static JSON snapshot and does not connect to MotherDuck at runtime. No MotherDuck token is included. Refresh `public/data/ecommerce.json` and push a new commit when the source data changes.

- Fact grain: one row per order item.
- Order discount is allocated proportionally across all items in the order based on `net_item_revenue`.
- Revenue and AOV include delivered orders only.
- Gross profit is before shipping and operating expenses.
- All records are synthetic portfolio data.
