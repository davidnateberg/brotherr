# Brotherr — Project Context for Claude

## What this is
Band website for **Brotherr**, the indie folk project of **David Berg** based in Lancaster, PA.
Live at: **brotherrmusic.com**
GitHub repo: **github.com/davidnateberg/brotherr**
Hosted via: **GitHub Pages** (deployed via GitHub Actions from `website/` folder)
DNS: **GoDaddy** (NS19/NS20.DOMAINCONTROL.COM)

---

## Repo structure

```
brotherr/
├── .github/
│   └── workflows/
│       └── deploy.yml          # Auto-deploys website/ to GitHub Pages on push to main
├── website/
│   ├── index.html              # Home page — full-screen hero, social icons
│   ├── bio.html                # Bio page — photo + bio text + Bio heading
│   ├── tour.html               # Tour page — "No upcoming shows"
│   ├── CNAME                   # brotherrmusic.com
│   ├── sitemap.xml
│   ├── robots.txt
│   ├── assets/
│   │   ├── css/
│   │   │   └── main.css        # Shared styles + design tokens (CSS variables)
│   │   ├── images/
│   │   │   ├── background.jpg  # Hero bg — "tractor hill_film_d_classic.jpg"
│   │   │   └── david.jpg       # Bio photo — "BTS_Charles_whistler.jpg"
│   │   └── fonts/
│   │       ├── Biro_Script_reduced.otf
│   │       └── Biro_Script_reduced.ttf
│   └── content/
│       └── bio.js              # Edit this file to update bio text (no HTML needed)
└── CLAUDE.md                   # This file
```

---

## Design system

### Color palette (Pennsylvania countryside — sky blues + farm greens)
Defined as CSS variables in `website/assets/css/main.css`:

```css
--sky-light:  #ccd6dd   /* pale overcast sky — primary text, headings */
--sky-mid:    #5274a1   /* Blue Mountain blue — nav links, accents */
--sky-bright: #2596be   /* summer sky — hover states */
--night:      #0e1a26   /* deep PA night — page background */
```

### Typography
- **Headings / Band name**: Biro Script (local font, `assets/fonts/`)
- **Body / Nav**: Georgia, serif
- Nav links: `#5274a1`, hover to `#ccd6dd`

### Background
- Full-bleed hero image with `brightness(0.78) saturate(0.85)` filter
- Blue gradient overlay: sky blue at top → deep navy at bottom

---

## Pages

### Home (`index.html`)
- Full-screen hero with background photo
- Band name "Brotherr" in Biro Script, centered
- Social icons: Instagram, TikTok, YouTube
- Nav: Home · Bio · Listen · Tour

### Bio (`bio.html`)
- Photo (david.jpg) on the left, bio text on the right
- "Bio" heading in Biro Script with `#5274a1` underline separator
- Bio text loaded from `content/bio.js` — **edit that file to update bio**
- Mobile: stacks vertically

### Tour (`tour.html`)
- "Tour" heading in Biro Script
- "No upcoming shows" in muted text

---

## Navigation
All pages share the same nav (defined per-page, styles in `main.css`):
- **Home** → `index.html`
- **Bio** → `bio.html`
- **Listen** → `https://ffm.bio/brotherr` (opens in new tab — Feature.fm link tree)
- **Tour** → `tour.html`
- Active page gets full opacity, inactive links are `#5274a1`

---

## Social links
| Platform  | URL |
|-----------|-----|
| Instagram | https://www.instagram.com/brotherrmusic |
| TikTok    | https://www.tiktok.com/@brotherr.music |
| YouTube   | https://www.youtube.com/@brotherrmusic |
| Listen (Feature.fm) | https://ffm.bio/brotherr |
| Spotify   | https://open.spotify.com/artist/2cNYsI4pJAoNuWdKArlGfM |
| Apple Music | https://music.apple.com/us/artist/david-berg/1676336363 |

---

## SEO
- Meta description, Open Graph, and Twitter card tags on all pages
- JSON-LD MusicGroup structured data on home page
- Sitemap at `brotherrmusic.com/sitemap.xml`
- Submitted to Google Search Console
- Domain property verified via GoDaddy DNS TXT record

---

## Deployment
Every push to `main` triggers GitHub Actions → deploys `website/` folder to GitHub Pages.
To update the site: edit files → commit → push to main. That's it.

## To update the bio text
Open `website/content/bio.js` and edit the string. Commit and push.

---

## Assets source files (on David's machine)
- Background: `/Users/david/Desktop/Brotherr/Assets/album art/tractor hill_film_d_classic.jpg`
- Bio photo: `/Users/david/Desktop/Brotherr/Assets/Audience Finding/Images/ME/BTS_Charles_whistler.jpg`
- Font: `/Users/david/Downloads/biro_script/Biro_Script_reduced.{otf,ttf}`
