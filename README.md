# LDS Temple Locator

A single-page web app for exploring the dedicated temples of The Church of Jesus Christ of Latter-day Saints. Search by the Church's 5-letter abbreviation (SLAKE, PROVO, NZEAL, LANGE…), open a detail card with location, dedication date, language, and a short Church/mission-history note, and see every temple as a star on a spinnable 3D globe.

## Features

- 177 dedicated temples worldwide
- Search by abbreviation, full name, city, or country
- Detail card with photo (or graceful SVG placeholder), city/country, exact coordinates, dedication date, primary languages, and a short Church/mission-history note
- 3D globe (globe.gl + three.js) with golden-star markers; selected temple becomes a bigger glowing white star and the camera flies to it
- Pure static site — no build step, no server. Open `index.html` directly or deploy to any static host.

## Project layout

```
.
├── index.html              Main app (HTML + CSS + JS in one file)
├── vercel.json             Static-site config (caching, security headers)
├── data/
│   ├── temples.json        Canonical dataset (177 temples)
│   └── temples.js          Same data exposed as window.TEMPLES (works on file://)
└── images/
    ├── _placeholder.svg    Fallback temple silhouette
    └── README.txt          How to add real temple photos
```

## Adding real temple photos

Drop a JPG into `images/` named with the temple's abbreviation in lowercase, for example:

- `images/slake.jpg` → Salt Lake Temple
- `images/provo.jpg` → Provo Utah Temple
- `images/nzeal.jpg` → Hamilton New Zealand Temple

If a photo is missing, the app falls back to `_placeholder.svg` automatically.

Recommended size: 1200 × 800 JPG, landscape.

## Data sources

- Temple abbreviations: [FamilySearch temple-codes](https://github.com/FamilySearch/temple-codes/blob/master/temples.xml)
- Cross-referenced with the Church's official [List of Temples](https://www.churchofjesuschrist.org/temples/list?lang=eng) and [ChurchofJesusChristTemples.org](https://churchofjesuschristtemples.org/temples/)

## Local development

This is a plain static site. Open `index.html` directly or run any static server:

```bash
python3 -m http.server 8765
# then visit http://localhost:8765/
```

## License

The app code is released for personal/educational use. Temple photos and Church-published content remain the property of their respective owners.
