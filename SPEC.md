# Aquanor Fluidteknik — Site Spec

## Purpose
B2B website for fictional Danish engineering firm. Target audience: HVAC contractors, district heating operators, food/pharma plant engineers, municipal procurement. Should communicate that Aquanor is the BRIDGE between engineering analysis and physical installation.

## Hard requirements (from user)
1. Hamburger menu (sandwich bar) visible on phone widths — verified at 375px
2. EN/DA language toggle in nav — EN copy must sound natural, not Google Translated
3. "Bridge / mellemled" between engineering world and VVS/construction world must be obvious on first scroll
4. All boxes, nav bar, sections auto-scale cleanly on mobile + desktop
5. Push to GitHub + deploy to Netlify, send URL

## Stack
- Single index.html file, ~1700 lines
- Inline CSS + JS (no build step, no external libs except Google Fonts)
- IBM Plex Sans + JetBrains Mono
- Slate + safety orange palette (existing CSS vars)
- Live-status heartbeat to Telegram during long runs

## Sections (in order)
1. 24/7 strip (top)
2. Nav (sticky, with hamburger + EN/DA toggle)
3. Hero (h1, lead, stats, animated pipe SVG)
4. **NEW: Bridge callout** — VVS-side ↔ Engineering-side, Aquanor in middle. Two columns + center badge.
5. Capabilities (6 cards)
6. Methodology (5 phases)
7. Case study (Aalborg)
8. Calculator (Darcy-Weisbach, working JS)
9. Industries (6 sectors)
10. Credentials (standards + software stack)
11. Contact + form
12. Footer

## i18n implementation
- All visible text wrapped in `data-i18n="key"`
- JS dictionary `const I18N = { da: {...}, en: {...} }`
- `setLang(lang)` walks DOM, swaps textContent
- Saved in localStorage as `aquanor-lang`
- Default DA, toggle button in nav

## EN copy rules
- No Google Translate artifacts
- "Strømningsteknik" → "Flow Engineering"
- "VVS" → "HVAC & Process Piping" (Danish VVS splits in English)
- "Trykfald" → "Pressure drop"
- "Beregner" → "Sizing Tool"
- "Vagtc central" → "On-call dispatch"
- "Bro/mellemled" → "We bridge engineering analysis and on-site execution"
- Industry names: District Heating, Pharma, Food & Beverage, Process Industry, Municipal, Marine

## Tasks
- [ ] Write index.html (CSS + HTML + JS, complete)
- [ ] Local test: python http.server on :8765
- [ ] Headless chromium screenshot at 375px width — verify hamburger shows
- [ ] Headless chromium screenshot at 1440px — verify desktop layout
- [ ] git init, git add, git commit
- [ ] gh repo create aquanor-fluidteknik --public --source=. --push
- [ ] netlify deploy --dir=. (anonymous) OR link to GitHub repo
- [ ] Send user the URL + password
