# Midblock — notes for AI coding agents

One HTML file: markup, inline CSS and inline scripts; GSAP with ScrollTrigger, Lenis smooth scroll, all from jsDelivr. No build step, no framework.

## Files
Work from the files: a page read through a link comes back as a summary, and a page rebuilt from it would differ.
```bash
curl -LO https://raw.githubusercontent.com/8bsite/architecture-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/architecture-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/architecture-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/architecture-website-template/main/CREDITS.md
```
In Windows PowerShell type `curl.exe`. Publish `index.html` with LICENSE and CREDITS.md; this file, README.md and `previews/` are not part of the site.

## Do not break
- Keep it one file unless the user asks otherwise; no framework or bundler for copy, colour or photo changes.
- Keep the ids and the `data-8b-section` / `data-8b-motion` attributes. Each section has its styles in `<style data-8b-part="section:<id>">` and its animation, if any, in `<script data-8b-part="scene:<id>">`.
- The scripts find these classes and attributes; when you change a section's markup, keep them or update the script:
  - `section-script:navigation`: `.nav__toggle` `.nav__menu` `.nav__close`
  - `scene:opening`: `.op__slab` `.op__slab--gap` `.op__floor` `.op__block` `.op__stage` `.op__img`
  - `section-script:contact`: `.ct__form` `.ct__status` `data-sent-text` `data-error-text`
  - `scene:buildings`: `.bl__pin` `.bl__track` `.bl__item` `.bl__shift`
  - `scene:scan`: `.sc__frame` `.sc__smear` `.sc__line` `.sc__tick` `.sc__step` `.sc__steps`
  - `scene:colours`: `.co__band` `.co__bands` `.co__fill` `.co__label`
  - `scene:floors`: `.fl__frame` `.fl__slice` `.fl__floor` `.fl__list`
  - `scene:studio`: `.st__person` `.st__row` `.st__frame`
  - `scene:contact`: `.ct__slab--l` `.ct__slab--r` `.ct__stage`
- Colours, fonts, radii and shadows are CSS variables in the `:root` block (`data-8b-part="tokens"`); change them there and keep body text at 4.5:1 contrast or more.
- Animations run only when the visitor allows motion (`prefers-reduced-motion: no-preference`); the page must stay readable without them.
- A display line with `style="--len:N"` is sized to fill its width: N is its number of characters, spaces included (`Midblock` → 8).
- Keep the header comment and `<meta name="generator">`; the "Design: 8B" footer link is optional.

## Replace before publishing
- Everything marked `data-8b-placeholder` (og-image, favicon, form, phone, email); remove the attribute once the real value is in. With no real value: no preview image — delete the `og:image` tag and set `twitter:card` to `summary`; no phone, email or address — remove that link or row.
- Bring us a plot (nav, first screen, footer) and Add a plot (register): link to #contact now; point them to your booking or enquiry URL, or leave them on the form.
- **The form sends nothing.** `section-script:contact` checks the fields and shows a thank-you message without sending. Pick one:
  - Formspree: set `action="https://formspree.io/f/<id>"` on the form; in the script, before the thank-you message, `await fetch(form.action, { method: 'POST', body: new FormData(form), headers: { Accept: 'application/json' } })` and show it only if the response is ok.
  - Netlify Forms (site on Netlify): add `name="contact" data-netlify="true"` and `<input type="hidden" name="form-name" value="contact">`; send with `fetch('/', { method: 'POST', headers: { 'Content-Type': 'application/x-www-form-urlencoded' }, body: new URLSearchParams(new FormData(form)) })`.
  - No form service: remove the `<form>` together with the script that handles it (it would fail without the form) and keep the email link.
- Invented demo facts (ask the user for the real ones; do not make up prices, dates or addresses):
  - The offer "plots under ten metres wide" (opening, register, footer, meta description) and the city: Bristol (contact, footer).
  - The studio address "Ropewalk Yard 9, Bristol BS1 6XN" (contact, footer); the phone was replaced with +44 117 000 0000 and the email is studio@midblock.example (contact, footer).
  - Hours: "Monday to Friday, 9:00–18:00. Site walks on Thursdays." (contact).
  - Company facts: "Since 2014", "Eleven buildings", "Forty-one gaps mapped across the city", narrowest plot "2.9 metres at 9 Ropewalk" (opening, floors, FAQ) and "© 2026 Midblock Architects Ltd. Registered in England." (footer).
  - Five projects with invented addresses, plot widths, floors and years: 11 Kerr Lane (4.1 m, 5 floors, 2023, gap "open since 1941"), 4 Saltmarket Row (6.2 m, 4 floors, 2021), Quay 27 (7.8 m, 3 floors, 2022), Mill & Ash corner (5.5 m, 2 floors, 2019, 38 m²), 18 Weir Road (9 m, 4 floors, 2024, timber from the old tannery roof) (buildings; the names also appear in colours).
  - 9 Ropewalk details: between a garage and a print shop, seven floors, a bike workshop, a roof garden with a river view, a 28 m² studio, a flat let at a fixed rent (opening, floors).
  - The method: filming the street with a slit camera from first light to midnight, times 05:40, 12:10, 19:30, 23:55, "one contractor" and a street that stays open (opening manifesto, scan).
  - The register: eight plots with addresses, widths, depths, orientations and statuses, "updated every month", listed "with their owners' agreement" (register, FAQ).
  - Colour stories with dates: a render "painted in 1932 and repainted four times", a door "painted in 1958", a tram shelter (colours).
  - Testimonials from invented people: Ines Calder (florist, Ropewalk), Tom Abara (9 Kerr Lane), Margit Holm (Weir Road), with "seven months" of building and "forty years" of nettles (neighbours).
  - Team names and roles: Owen Marsh, Hana Okafor, Leo Varga, Mei Lindqvist, Jun Park (studio); the portraits are stock photos of other people.
  - FAQ answers: built on 2.9 m, about 2.4 m minimum, a free first visit, buildings within an hour of the studio and "one plot further away each year", plot owners ("the council and two housing associations"), about two years from scan to keys (three months design, nine to twelve months planning, seven to ten months on site) (FAQ).
  - Service: "We reply within a week" (contact text and the data-sent-text message).
- `<title>`, the meta description and the og tags; photos (Unsplash, see CREDITS.md) when the user has their own.

## Notes
- The smeared slabs in the opening and contact are one street photo stretched sideways with CSS: to change it, replace the same URL in all eight opening layers and both contact slabs. The floors section uses one photo for all seven slices, the scan section one photo twice.
- Project card widths and heights come from the inline style="--plot: N; --h: N" on each building: --plot is the plot width in metres, used as a relative width.
- Without JavaScript the phone menu button cannot open the overlay; the links stay reachable in the first screen and the footer.
- On phones the opening's second screen (manifesto and facts) is taller than the viewport, so the climbing bands are mostly seen behind and around it, and just before the buildings walk starts the top of its frame is empty for a moment.
- The floors photo has a white sky: when the slices slide apart, their white ends read as white blocks on the navy ground.

## Common edits
- Rebrand: search the old name (`Midblock`) in any letter case and replace every match; change the favicon letter and colours in `<link rel="icon">`.
- Photos: replace `src` and delete `srcset` and `sizes` (they list Unsplash sizes), keep `width`/`height` to the new photo's ratio, update `alt` and CREDITS.md.
- Remove a section: delete its markup, its `section:<id>` and `scene-style:<id>` styles, its `scene:<id>` and `section-script:<id>` scripts, and links to `#<id>`.
- Native scroll instead of smooth scroll: delete the Lenis block in `page-init` and the Lenis `<script>` tag.

## Check and publish
- Open the page at 375 and 1440 px, with reduced motion on, with the console open.
- Search `data-8b-placeholder` and the old name: nothing should be left but class names.
