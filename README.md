# Grazing Manager

A map-based seasonal planning tool for rotational grazing, built for mobile-first field use.

## Features

- **Map View** - Visual paddock layout with grazing status indicators
- **Calendar View** - Two-week grazing schedule with recovery periods
- **List View** - Manage paddocks, animals, herds, and events
- **Dashboard** - Carrying capacity analysis and forage balance
- **Forage Readings** - Quick field measurements with grazing stick method
- **Season-Aware** - Automatic recovery period adjustments by season

## Demo Data

Pre-loaded with Tuckaway Farm data:
- 8 paddocks (33+ acres total)
- 4 animal groups (Ewes, Lambs, Cows, Calves)
- 2 herds (Sheep Flock, Beef Herd)

## Deployment to GitHub Pages

### Option 1: Direct Upload (Simplest)
1. Create a new repository on GitHub
2. Go to Settings → Pages
3. Set Source to "Deploy from a branch" and select `main` branch
4. Upload these files to your repository:
   - `index.html`
   - `404.html`
5. Your site will be live at `https://[username].github.io/[repo-name]/`

### Option 2: Using Git
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/[username]/[repo-name].git
git push -u origin main
```

Then enable GitHub Pages in repository Settings → Pages.

## Technical Notes

- **No build step required** - Uses CDN-hosted React, ReactDOM, and Babel
- **Mobile-first** - Designed for field use on phones/tablets
- **Offline-capable** - Data stored in localStorage
- **Export function** - Download data as JSON for FarmOS sync

## Data Model (CFC Compatible)

### Paddock
- Name, acres, soil pH, management type
- Current forage height and density
- Water/shade access flags

### Animal Groups
- Type (cattle_cow, sheep_ewe, etc.)
- Count and average weight
- Calculated Animal Units (AU)

### Herds
- Named groups of animals that graze together
- Used for movement planning

### Grazing Events
- Links herd to paddock with dates
- Tracks pre/post grazing forage

### Forage Readings
- Height (grazing stick method)
- Density (0-1 dots = high, 3+ = low)
- Calculated lbs DM/acre

## Calculations

**Animal Units (AU):**
- 1 AU = 1000 lb animal
- Sheep/goats: 0.9x multiplier
- Horses: 1.1x multiplier

**Dry Matter per Acre:**
- DM = (Height - 4") × Density Factor
- Density factors: High=250, Medium=200, Low=150

**Recovery Periods:**
- Spring: 21 days
- Summer: 35 days  
- Fall: 45 days
- Winter: 90 days

## License

MIT
