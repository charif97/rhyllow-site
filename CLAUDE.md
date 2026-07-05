# CLAUDE.md — RHY / Guadalupe Sánchez · Dancer Portfolio

Context file so any future session picks up instantly. Keep this updated when things change.

## The person
- **Real name:** María Guadalupe Sánchez Sanz
- **Stage name:** RHY
- **Instagram:** [@rhyllow](https://www.instagram.com/rhyllow) — bio *"miro al miedo con coraje"*
- **Based:** Madrid (Vallekas), Spain · available worldwide
- **Profession:** Professional dancer & performer
- **Disciplines:** Commercial · Contemporary · Floorwork · Heels · Acrobatic conditioning · Teaching
- **Booking email (placeholder):** booking@rhyllow.dance
- **Identity verified:** @rhyllow = "RHY", Madrid dancer/artist — consistent with the name provided.

## The goal
A professional, shareable, **bilingual EN/ES** dancer portfolio she can send when applying for contracts. Target audience: casting directors, talent scouts, labels, event producers. Aesthetic direction from the user: **artistic + cinematic, creative, black & white, refined & elegant.**

## Career / CV (real, user-provided)
**International — Morocco (luxury circuit):**
- Palais Dar Soukkar — dinner-show residency, Marrakech
- Casa Emma — dinner-show residency, Rabat
- Nostalgia Lovers Festival — AI Dance Agency
- Snor (Moroccan rapper) — **lead / main character** in music video
- Skipline Productions — Rabat, Quartier Hassan

**Spain — Madrid:**
- Shôko Madrid — flagship club / live venue
- Cabalgata de Reyes (Three Kings Parade) — Comunidad de Madrid
- Rawr Studio Madrid — teaching & choreography
- Collaborations: Pablo Brotons, Luix Cabeza, Leslie Delage

## Deliverables — 5 style options (all in this folder)
All are single self-contained `.html` files. Open by double-clicking. Each has an EN/ES toggle and labelled placeholders where real photos/videos go.

| File | Style | Vibe |
|------|-------|------|
| `rhy_style_A_editorial.html` | Editorial / Fashion | Magazine, big serif, ivory, asymmetric grid |
| `rhy_style_B_cinematic.html` | Cinematic / Fullscreen | Dark, fullscreen video hero, film strips |
| `rhy_style_C_gallery.html` | Minimal Gallery / Swiss | Off-white, sticky sidebar, hover captions |
| `rhy_style_D_premium.html` | Premium data-hub | Dark #0B0B0C + purple #8A2BE2 + gold #D4AF37, Tailwind, booking form, showreel modal, masonry |
| `rhy_style_E_immersive.html` | Immersive gallery | B&W, filterable gallery (All/Stage/Screen/Studio), slide-in contact panel — inspired by yassine-lens.com |

## Conventions used in every file
- **Bilingual:** elements carry `data-en` / `data-es`; `toggleLang()` swaps `innerHTML`. Toggle button has class `.lang`.
- **Placeholders:** `<div class="ph" data-label="...">` marks where media goes. Replace with `<img src="photos/name.jpg">` or `<video src="videos/clip.mp4" autoplay muted loop playsinline>`. Grayscale filter applied for B&W look.
- **Suggested media folders (create alongside the HTML):** `photos/` and `videos/`.

## Finishing touches applied (D & E)
- **Direct DM link:** Instagram button uses `https://ig.me/m/rhyllow` so scouts land straight in her DMs (her preferred platform).
- **Instagram live feed:** placeholder + embedded HTML-comment instructions to plug in a **Behold.so** or **Elfsight** widget so the media section auto-updates with her newest posts (no manual code edits). Apply the same to A/B/C if desired.

## Media / Instagram download note
- Claude cannot operate arbitrary browser extensions (e.g. Turbo Downloader) as tools.
- BUT: if such an extension saves files to disk, drop them into `photos/` and `videos/` in this folder and Claude can integrate them into any site.

## Open / next steps
- User to pick a preferred style (or a hybrid).
- Add real photos/videos into `photos/` & `videos/`, swap out `.ph` placeholders.
- Optionally register `rhyllow.dance` domain (or host free on Netlify/GitHub Pages/Vercel).
- Confirm real booking email.
