# FEMA Region Natural Events Dashboard

A web-based dashboard for viewing natural disaster events from NASA's EONET API, organized by US FEMA regions.

## Tech Stack

- **Frontend**: Vanilla HTML/CSS/JavaScript (single-page app)
- **Styling**: Tailwind CSS (via CDN)
- **Map**: Leaflet.js with MarkerCluster
- **Map Tiles**: CartoDB (dark/light themes)
- **APIs**:
  - NASA EONET API (`https://eonet.gsfc.nasa.gov/api/v3/events`)
  - NewsAPI.org (`https://newsapi.org/v2/everything`)

## Features

- **FEMA Region Filtering** - Filter events by 10 FEMA regions
- **Category Filtering** - Wildfires, Severe Storms, Floods, Volcanoes, Earthquakes, Snow & Ice, Drought, Landslides
- **Date Range** - Last 24h, 7 days, 30 days, 90 days, 1 year, or all time
- **Status Filter** - Active or closed events
- **Search** - Text search in event titles
- **Map View** - Interactive map with color-coded markers by category
- **List View** - Sortable table with event details
- **Dashboard** - Statistics with drill-down filtering
- **Dark Mode** - Toggle between light and dark themes (defaults to dark)
- **News Integration** - Fetch related news articles for each event
- **Auto-refresh** - Configurable automatic data refresh (5/15/30 minutes)
- **Export** - Download data as CSV or JSON

## Getting Started

1. Open `index.html` in a web browser
2. The app will automatically fetch events from NASA's EONET API
3. Click "Set News API" to configure your NewsAPI.org key (free at https://newsapi.org)

## News API Setup

1. Get a free API key from https://newsapi.org
2. Click "Set News API" button in the header
3. Enter your API key when prompted
4. The key is saved in your browser's localStorage

## FEMA Regions

| Region | States/Territories | HQ |
|--------|-------------------|-----|
| 1 | CT, ME, MA, NH, RI, VT | Boston |
| 2 | NJ, NY, PR, VI | New York |
| 3 | DE, MD, PA, VA, WV, DC | Philadelphia |
| 4 | AL, FL, GA, KY, MS, NC, SC, TN | Atlanta |
| 5 | IL, IN, MI, MN, OH, WI | Chicago |
| 6 | AR, LA, NM, OK, TX | Denton |
| 7 | IA, KS, MO, NE | Kansas City |
| 8 | CO, MT, ND, SD, UT, WY | Denver |
| 9 | AZ, CA, HI, NV, Pacific Territories | Oakland |
| 10 | AK, ID, OR, WA | Bothell |

## Keyboard Shortcuts

- Click on any stat card to filter by that category/status
- Click on event rows in list view to center map on that event
- Click "Map" button on map popup to zoom to event
- Click "News" button to see related news articles

## Browser Storage

The app uses browser localStorage to persist:
- News API key
- Dark mode preference (via CSS class)

## API Rate Limits

- **NASA EONET**: No documented rate limit (free, public API)
- **NewsAPI.org**: 100 requests/day (free tier)
