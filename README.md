# Regional Emerging Events Dashboard

A web-based dashboard for viewing natural disaster events from NASA's EONET API, FEMA Disaster Declarations, and NWS Weather Alerts, organized by US FEMA regions. Built for ITDRC (Information Technology Disaster Resource Center) to support disaster response operations.

## Tech Stack

- **Frontend**: Vanilla HTML/CSS/JavaScript (single-page app)
- **Styling**: Tailwind CSS (via CDN)
- **Map**: Leaflet.js with MarkerCluster
- **Map Tiles**: CartoDB (dark/light themes)
- **APIs**:
  - NASA EONET API (`https://eonet.gsfc.nasa.gov/api/v3/events`)
  - FEMA OpenFEMA API (`https://www.fema.gov/api/open/v2/DisasterDeclarationsSummaries`)
  - NWS Weather API (`https://api.weather.gov/alerts`)
  - GNews API (`https://gnews.io/api/v4/search`)
  - CORS Proxy: AllOrigins (`https://api.allorigins.win/raw?url=`)

## Features

- **FEMA Region Filtering** - Filter events by 10 FEMA regions with map highlighting
- **Category Filtering** - Wildfires, Severe Storms, Floods, Volcanoes, Earthquakes, Snow & Ice, Drought, Landslides
- **Date Range** - Last 24h, 7 days, 30 days, 90 days, 1 year, or all time
- **Status Filter** - Active or closed events
- **Magnitude Filter** - Filter earthquakes by minimum magnitude (4.0+, 5.0+, 6.0+, 7.0+)
- **Search** - Text search in event titles
- **Map View** - Interactive map with color-coded markers by category and region highlighting
- **List View** - Sortable table with event details
- **Dashboard** - Statistics with drill-down filtering
- **FEMA Declarations View** - View official FEMA disaster declarations (last 60 days)
- **FEMA Overlay** - Toggle to show FEMA declarations as overlay on map
- **Weather Alerts View** - Real-time NWS weather alerts (watches, warnings, advisories)
- **Dark Mode** - Toggle between light and dark themes (defaults to dark)
- **News Integration** - Fetch related news articles for each event
- **Auto-refresh** - Configurable automatic data refresh (5/15/30 minutes)
- **Export** - Download data as CSV or JSON

## Getting Started

1. Open `index.html` in a web browser
2. The app will automatically fetch events from NASA's EONET API
3. Click "Set News API" to configure your GNews API key (free at https://gnews.io)
4. Explore the different views: Map, List, Dashboard, FEMA Declarations, Weather Alerts

## API Rate Limits

| API | Limit | Notes |
|-----|-------|-------|
| NASA EONET | No documented limit | Free, public API |
| FEMA OpenFEMA | No documented limit | Free, public API |
| NWS Weather | No documented limit | Free, public API |
| GNews API | 100 requests/day | Free tier; requires API key |
| AllOrigins (CORS Proxy) | 100 requests/day | Used for GNews CORS bypass |

## Views

### Map View
- Color-coded markers by event category (wildfires=red, floods=blue, etc.)
- Select a FEMA region to highlight on map and zoom to bounds
- Toggle FEMA Overlay to show disaster declarations by state
- Click markers to see event details, map zoom, or news

### List View
- Sortable table with Date, Title, Category, Region, Magnitude, Status
- Click row to zoom to event on map
- Click News button to see related articles

### Dashboard
- Total events, active/closed counts
- Category breakdown with clickable filtering
- Region and category statistics

### FEMA Declarations
- Last 60 days of official FEMA disaster declarations
- Color-coded by type: DR (red), EM (yellow), FM (orange)
- Stats by type, region, and state
- Click region stats to filter events

### Weather Alerts
- Real-time NWS weather alerts (no API key needed)
- Color-coded by severity: Extreme (red), Severe (orange), Moderate (yellow), Minor (green)
- Stats by severity, type, and state
- Shows all active watches, warnings, and advisories

## News API Setup

1. Get a free API key from https://gnews.io
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

## Usage Tips

- Click stat cards to filter by that category/status
- Click event rows in list view to center map on that event
- Select a FEMA region to highlight on the map
- Use the magnitude filter to focus on significant earthquakes
- Toggle FEMA Overlay to see official disaster declarations on the map

## Browser Storage

The app uses browser localStorage to persist:
- GNews API key
- Dark mode preference
