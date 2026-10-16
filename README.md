# Free HTML architecture website template with GSAP scroll animations — Midblock

**Website for an architecture office, with projects, method, team and an enquiry form: a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02)

**[Live demo](https://8bsite.github.io/architecture-website-template/)** · **[Use this template](https://github.com/new?template_name=architecture-website-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/architecture-website-template/archive/refs/heads/main.zip)**

<a href="https://8bsite.github.io/architecture-website-template/"><img src="previews/desktop.png" alt="Midblock, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/architecture-website-template/"><img src="previews/phone.png" alt="Midblock, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/architecture-website-template/"><img src="previews/scroll.gif" alt="Midblock, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page site for a small architecture office that builds on narrow city plots, with its buildings, method, a register of plots, team and an enquiry form. Flat pastel blocks and street photos that start as streaks of smeared colour and come into focus as you scroll; the projects pass sideways like a walk along a street.

Good for: architecture or design office; architect's portfolio; urban planning or housing studio; construction or development company; any studio showing projects one by one plus a team. Free for personal and commercial use (MIT), made by [8B](https://8b.com/).

## Quick start

Pick one:

- **With an AI coding agent** (Claude Code, Codex, Cursor, Windsurf…). Download the files into your project (in Windows PowerShell type `curl.exe`):
  ```bash
  curl -LO https://raw.githubusercontent.com/8bsite/architecture-website-template/main/index.html
  curl -LO https://raw.githubusercontent.com/8bsite/architecture-website-template/main/AGENTS.md
  curl -LO https://raw.githubusercontent.com/8bsite/architecture-website-template/main/LICENSE
  curl -LO https://raw.githubusercontent.com/8bsite/architecture-website-template/main/CREDITS.md
  ```
  Then give your agent this prompt:
  ```text
  Read AGENTS.md, then edit index.html. Use this template as the base for a site for <your architecture office or studio: what you design, where, your projects with photos, your team, how to get in touch>. Keep the layout, the motion and the single-file format; replace the brand name, copy, photos, project data, the register table, team, address, links and contacts, and recolour it through the CSS variables if needed.
  ```
  Give the agent the downloaded file, not a link: an agent reads a link as a summary and would rebuild a different page.
- **No code.** Download the ZIP, unzip it, replace the contacts and texts in `index.html`, put `index.html` into an empty folder and drag that folder onto [Netlify Drop](https://app.netlify.com/drop). The page is online in a minute.
- **On GitHub.** Click **[Use this template](https://github.com/new?template_name=architecture-website-template&template_owner=8bsite)** to get your own copy, then **Settings → Pages → Deploy from a branch → main**. Your site appears at `https://<you>.github.io/<repo>/`.

## What's on the page

- **Navigation** — top bar: wordmark, four section links, Bring us a plot button; phone menu overlay
- **We build in the gaps a city leaves.** — first screen: headline on stepped blocks between slabs of a street photo, then a manifesto and three short facts
- **Five buildings, none wider than a bus** — projects walked sideways: five buildings at their relative plot widths, each with a plate
- **We read a street for a whole day** — method in four steps beside a photo crossed by a red scan line
- **The gap register** — table of entries with status badges (demo: a public list of plots)
- **Borrowed colours** — six full-width colour bands, each with a name, a sentence and where it is used
- **What the neighbours said** — three testimonials on blocks at stepped heights, with one photo
- **9 Ropewalk, floor by floor** — one project floor by floor: a building photo cut into seven slices beside a list of seven levels
- **Five people, one long table** — team: five portraits at stepped heights with names and roles
- **Questions we hear on site** — questions and answers (native &lt;details&gt;)
- **Bring us a plot** — enquiry form between two street-photo slabs, then address, phone, email and hours
- **Footer** — colour bands, width-filling MIDBLOCK wordmark, links, address, copyright and the Design: 8B credit

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, form, phone, email) and the invented demo facts — prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The contact form does not send anything yet: connect it to a form service (Formspree, Netlify Forms) or remove it; [AGENTS.md](AGENTS.md) shows both.

## Customize

- **Colours and fonts**: CSS variables in the `:root` block at the top of `<head>`.
- **Text**: edit it in place. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.
- **Photos**: replace `src`, delete `srcset` and `sizes` (they list Unsplash sizes) and update the `alt` texts.
- **Animations**: each section's animation is one `<script data-8b-part="scene:<id>">` block at the end of the file. For native scroll, delete the Lenis block in `page-init`.

## For developers

- **Stack.** HTML and CSS (custom properties, cascade layers) with GSAP 3.13.0, ScrollTrigger, Lenis 1.3.27 from jsDelivr. No build step, no framework, no npm. 93 KB.
- **Layout of the file.** `<head>`: CSS variables, shared classes, then one style block per section. Then the markup, one element per section with a one-line comment above it. End of `<body>`: small behaviour scripts, the libraries, smooth scroll (`page-init`), the effects, one animation script per section.
- **Browsers.** Chrome and Edge 108+, Safari 15.4+, Firefox 101+ (it uses cascade layers, small/dynamic viewport units).
- **Accessibility.** Motion runs only when the visitor's system allows it; with "reduce motion" the page is complete and still. FAQ answers use native `<details>` and open without JavaScript. Every photo has alt text.
- **External requests.** fonts.gstatic.com, images.unsplash.com, cdn.jsdelivr.net. No analytics, no cookies. To self-host everything (offline use, or Google Fonts and GDPR in the EU), download those files and change the URLs.
- **Licences of the parts.** GSAP is free, commercial use included, under its own standard licence (not MIT); Lenis is MIT; fonts are SIL OFL; photos are under the Unsplash License. See [CREDITS.md](CREDITS.md).

## FAQ

**Can I use it for a client or a commercial site?** Yes. The code is MIT: use it, change it, sell the site you build with it.

**Do I have to keep the "Design: 8B" link?** No. It is welcome, not required.

**Can I use it in React, Next.js, Astro or Vue?** Yes. Move each section's markup and style block into a component and run its animation script in `useGSAP()` (React) or `onMounted` (Vue); start Lenis once. Or keep it as a separate static landing page next to your app (`example.com` for the landing, `app.example.com` for the app).

**Why doesn't the contact form send?** It is a demo. Connect it to Formspree, Netlify Forms or your backend; AGENTS.md has the steps.

**Where are the photos from?** Unsplash; they load from Unsplash's servers. Replace them with your own when you can.

## More free templates

[More 8B templates on GitHub](https://github.com/8bsite) · [8b.com](https://8b.com/)

## License

The template code is MIT licensed — see [LICENSE](LICENSE). Photos, fonts and libraries keep their own licences — see [CREDITS.md](CREDITS.md).
