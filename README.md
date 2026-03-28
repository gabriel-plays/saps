# SAPS Crime Intelligence Web Map

An interactive choropleth web map of South African police station crime statistics (FY2008/09 → FY2024/25), built for static hosting on GitHub Pages.

## File Structure

```
webmap/
├── index.html          ← Single-page application (no build step)
└── data/
    ├── bounds.geojson  ← Police station boundaries (simplified, 3.1 MB)
    ├── points.geojson  ← Police station centroids (0.2 MB)
    └── crime_data.json ← All crime statistics indexed by station (3.0 MB)
```

## Deploy to GitHub Pages

### One-time setup

1. Create a new GitHub repository (e.g. `saps-crime-map`)
2. Copy the entire `webmap/` folder contents into the repo root:
   ```
   index.html
   data/bounds.geojson
   data/points.geojson
   data/crime_data.json
   ```
3. Push to GitHub
4. Go to **Settings → Pages → Source → Deploy from branch → main / (root)**
5. Click **Save** — your map will be live at `https://yourusername.github.io/saps-crime-map`

### Git commands (quick start)

```bash
cd webmap
git init
git add .
git commit -m "Initial SAPS crime intelligence map"
git remote add origin https://github.com/YOUR_USERNAME/saps-crime-map.git
git push -u origin main
```

Then enable Pages in the repository Settings.

## Data Coverage

| Period | Source | Stations |
|--------|--------|----------|
| FY2008/09 – FY2020/21 | SAPS Annual Reports (audited) | 1,158 |
| FY2021/22 – FY2022/23 | SAPS Annual Reports (audited) | 1,163 |
| FY2023/24 | Quarterly releases (summed) | 1,174 |
| FY2024/25 | Quarterly releases (summed) | 1,179 |

**44 crime categories** across **17 financial years**.

## Features

- **Choropleth map** — colour station boundaries by any crime category and financial year
- **Year slider** — scrub through FY2008/09 to FY2024/25
- **Station search** — type any station name to jump to it
- **Detail panel** — click any station for:
  - KPI cards with year-on-year change indicators
  - 17-year trend line chart (6 key crime categories)
  - Horizontal bar profile chart for the selected year
  - Full sortable crime table
- **Layer toggles** — show/hide boundaries and station points
- **Dark theme** — optimised for crime intelligence work
