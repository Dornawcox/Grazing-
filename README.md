# Grazing Manager

A map-based seasonal planning tool for rotational grazing management. Built for the Farm Management Suite alongside Kennel, Barn, and Hunter tools.

## Features

- **Map View**: Visual paddock layout with active grazing indicators
- **Seasonal Planning**: Spring/Summer/Fall/Winter planning cycles  
- **Forage Calculations**: HMI-style grazing stick methodology
  - Height + density → estimated lbs DM/acre
  - Recovery period by season
  - Grazing days calculator
- **Herd Management**: Track animal groups, AU, daily DM intake
- **Winter Feed Budget**: Calculate hay needs based on herd size
- **Mobile-optimized**: Touch-friendly for field data entry

## Quick Start

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build
```

## Demo Data

Pre-loaded with Tuckaway Farm data (Lee, NH):
- 8 paddocks across 33+ acres
- Sheep flock (65 ewes, 92 lambs)
- Beef herd (4 cows, 4 calves)
- ~21 Animal Units total

## Key Concepts (HMI Methodology)

- **Animal Units (AU)**: Standardized to 1000 lb cow equivalent
- **DM Intake**: Cattle ~3% body weight/day, Sheep ~4%
- **Grazing Stick**: Height (inches) × density factor = lbs DM/acre
- **Recovery Period**: Spring 21d, Summer 35d, Fall 45d
- **Residual Height**: Leave 4" minimum for regrowth

## Data Storage

- localStorage for offline-first operation
- JSON export/import for FarmOS sync compatibility
- Ready for Supabase backend integration

## Tech Stack

- React 18 + TypeScript
- Vite build system
- Tailwind CSS
- No external map dependencies (SVG-based)

## Future Enhancements

- [ ] Leaflet/MapLibre integration for real map tiles
- [ ] FarmOS sync adapter
- [ ] Offline PWA support
- [ ] Weather data integration
- [ ] Multi-farm support

## License

MIT - Part of the Farm Management Suite
