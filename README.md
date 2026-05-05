# Every Park SLC 🌲

An interactive map of all 489 parks across Salt Lake County — built as a static site on GitHub Pages. Data originally sourced from [City Cast SLC](https://citycastslc.com).

## Setup

### 1. Get a Google Maps API Key
1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Create a project → Enable **Maps JavaScript API**
3. Create an API key and restrict it to your `*.github.io` domain
4. In `index.html`, replace `YOUR_GOOGLE_MAPS_API_KEY` with your key

### 2. Create the Suggestion Form
1. Create a [Google Form](https://forms.google.com) with fields like:
   - Park name
   - What needs correcting?
   - Your suggested change
   - Contact email (optional)
2. Copy the form's shareable URL
3. Replace `YOUR_GOOGLE_FORM_URL` in `index.html` (appears twice)

### 3. Deploy to GitHub Pages
1. Create a new GitHub repo (e.g. `every-park-slc`)
2. Push these files:
   - `index.html`
   - `parks.js`
   - `README.md`
3. Go to repo **Settings → Pages → Branch: main → / (root)**
4. Your site will be live at `https://yourusername.github.io/every-park-slc`

## File Structure

```
/
├── index.html   # The entire site (map, filters, detail panel)
├── parks.js     # All 489 parks as a JS constant (generated from KML)
└── README.md
```

## Updating Park Data

If the source data changes, export a new KML from uMap and run:

```bash
python3 convert_kml.py every_park_slc.kml
```

Then commit the updated `parks.js`.

## Credits

Park data collected by [City Cast SLC](https://citycastslc.com) host Ali Vallarta.
