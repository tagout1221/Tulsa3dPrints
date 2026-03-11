# Tulsa3dPrints — Claude Project Instructions

## What This Project Is
Tulsa3dPrints is a single-page marketing/landing website for a local 3D printing service based in Tulsa, Oklahoma. The site takes customer print orders and quotes via email and phone.

---

## Repositories & Deployment

- **GitHub:** https://github.com/tagout1221/Tulsa3dPrints
- **Branch:** `main` (auto-deploys to Vercel on every push)
- **Live site:** deployed via Vercel under the `tulsa3d-prints` project (team: `tagout1221-4109s-projects`)
- **Local working copy:** `C:\Users\tagou\Desktop\ClaudeCode\Tulsa3dPrints\`

---

## Tech Stack

- Pure HTML/CSS/JS — single file (`index.html`), no framework, no build step
- All styles are inline in a `<style>` block inside `index.html`
- `serve.mjs` — local dev server (serves at `http://localhost:3000`)
- `screenshot.mjs` — Puppeteer screenshot utility
- Puppeteer installed at `C:/Users/tagou/AppData/Local/Temp/puppeteer-test/`
- Chrome cache at `C:/Users/tagou/.cache/puppeteer/`

---

## File Structure

```
Tulsa3dPrints/
├── index.html              ← entire website (HTML + CSS + JS, ~1,280 lines)
├── logo.png                ← brand logo used in nav and footer
├── favicon.svg             ← site favicon
├── Company Logo T3DP.png   ← original logo file
├── serve.mjs               ← local dev server
├── screenshot.mjs          ← Puppeteer screenshot tool
├── package.json
├── package-lock.json
└── CLAUDE.md               ← Claude Code project rules (auto-loaded)
```

---

## Page Structure (index.html)

| Section | ID | Description |
|---|---|---|
| Navigation | `#main-nav` | Fixed header, logo + nav links + "Get a Quote" CTA |
| Hero | *(none)* | Headline, stats, animated 3D printer SVG |
| Services | `#services` | FDM Printing, Rapid Prototyping, Custom Parts, Rush Orders |
| Process | `#process` | 4-step: Send File → Quote → Print → Pickup/Ship |
| Gallery | `#gallery` | Portfolio showcase |
| Why Us | `#why` | Features, materials, satisfaction guarantee |
| CTA | `#cta` | Email + phone contact buttons |
| Footer | *(footer)* | Links, copyright, legal disclaimer, social icons |

---

## Brand & Design

- **Theme:** Dark background, teal (`#00d4aa` approx.) as the primary accent color
- **Logo:** `logo.png` (used in nav and footer), `favicon.svg` for browser tab
- **Contact:** wilsonbusiness1221@gmail.com | (918) 914-1482
- **Location:** Tulsa, Oklahoma
- **Footer muted text color:** `var(--muted)` CSS variable (tuned for dark theme)

---

## Key Decisions Made

- **Favicon:** Reverted to `logo.png` after experimenting with custom SVG favicons
- **Legal disclaimer:** Added to footer in fine print (`var(--muted)` color) stating customers must own rights to submitted files; Tulsa3dPrints not liable for IP violations
- **Footer legal text:** Uses `var(--muted)` (not hardcoded hex) to stay readable on dark background

---

## Legal Disclaimer (footer)

> Tulsa3dPrints reserves the right to refuse any print order that infringes upon copyrights, trademarks, patents, or other intellectual property rights. By submitting a file, you represent and warrant that you own or have obtained all necessary rights and permissions to reproduce the design. We are not liable for any intellectual property violations arising from customer-submitted files.

---

## Workflow Rules (from CLAUDE.md)

- Always invoke the `frontend-design` skill before writing any frontend code
- Always serve on localhost — never screenshot a `file:///` URL
- Screenshots go to `./temporary screenshots/screenshot-N.png` (auto-incremented)
- Single `index.html` output, all styles inline
- Mobile-first responsive
- Check `brand_assets/` folder before designing (use real assets, not placeholders)

### Anti-Generic Guardrails
- Never use default Tailwind palette — derive from brand teal
- Never use flat `shadow-md` — use layered, color-tinted shadows
- Pair a display/serif with a clean sans-serif for typography
- Only animate `transform` and `opacity` — never `transition-all`
- Every clickable element must have hover, focus-visible, and active states
- Surfaces must have a layering system (base → elevated → floating)

### Hard Rules
- Do not add sections or content not requested
- Do not "improve" a design beyond what was asked
- Do not stop after one screenshot pass — do at least 2 comparison rounds
