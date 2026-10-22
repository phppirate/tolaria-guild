---
id: 01m56t82wnpgh9t15b9taz16tc
---

# Scan Montana Website

#website #design #seo #scan-montana
Assistant: [[Ethan]]

Content ideas and a design direction for [scanmontana.com](https://scanmontana.com), the site for Scan Montana LLC. Related: [[Web Design Inspiration Resources]].

> **How to read this note:** **[Fact]** means taken from the live site, its code, or our review (Oct 2026). **[Suggestion]** is a recommendation. Values in `[brackets]` are placeholders. Fill them in with real business info and don't make them up.

## Summary

- **[Fact]** Scan Montana LLC offers Matterport 3D virtual tours, rough-in scans (documenting electrical, plumbing, and HVAC before drywall), floor plans, and custom solutions across the Flathead Valley, MT: Kalispell, Whitefish, Columbia Falls, Bigfork, and Polson.
- **[Fact]** The site is a single-page Nuxt (Nuxt Content) build on Netlify with about 216 words. It has no nav, no portfolio or tour embeds, no real photos, no pricing, about, or testimonials, and no phone, email, or address. The contact form is the only CTA.
- **[Fact]** **The current logo is final.** Everything below is built around it.
- **[Suggestion]** Turn the one-pager into a small local-service site. Lead with real Matterport tours as the proof, add a page for each service and each town, and adopt a visual system taken straight from the logo: monoline ink on snow, one glacier-blue accent, pine/lake/sun motifs.

## The logo (final)

- **[Fact] File:** inline SVG in the site header (`viewBox="0 0 3838 3270"`, `class="fill-current text-foreground"`). Saved as `/workspace/scanmontana/logo.svg` (render: `logo.png`). The favicon is `/images/favicon.png` (128×128, black mark on `#e7e7e7`).
- **[Fact] Color:** the mark is **single-color**. It has no fill of its own and inherits `currentColor` from the theme's `--foreground`:
  - Light mode: **`#020817`** (near-black navy ink)
  - Dark mode: **`#f8fafc`** (snow white)
- **[Fact] Shapes:** a badge-style composition made of:
  - a large **open circle / sun arc** (thick stroke) that frames the scene, broken at the lower left and lower right where the trees and mountain run out past it
  - **three stylized pines**: a tall center tree flanked by two shorter ones, each built from stacked horizontal "branch bars" on a vertical trunk
  - a **faceted mountain peak** at right, drawn as a heavy outline with a notched snow line and angular planes
  - **three wavy lines** below (lake/river water). The top wave doubles as the ground line.
- **[Fact] Style:** flat, geometric, heavy uniform stroke (about 3% of the mark's width), square/butt line ends, no gradients, no outline-plus-fill mixing. It reads like a national-park badge or patch, and it holds up at favicon size.
- **[Fact] Current site theme:** shadcn/Tailwind slate defaults, plus accent `--accent: hsl(194 100% 57%)` = **`#24ccff`**. Font is **Figtree**.

## Brand & design direction (derived from the logo)

### Palette [Suggestion, built on the fact colors]

| Role | Name | Hex | Source | Notes |
|---|---|---|---|---|
| Primary ink: text, logo, buttons | Ink | `#020817` | **Fact** (logo/foreground) | 20:1 on white |
| Background (light) / logo on dark | Snow | `#f8fafc` | **Fact** (dark foreground) | |
| Accent / highlight | Glacier | `#24ccff` | **Fact** (site accent) | **Only 1.9:1 on white.** Never use it for text or thin icons on light backgrounds. Use it for fills behind Ink text (10.6:1), focus rings, map pins, and dark-mode links. |
| Accent for text/links on light | Deep Lake | `#0a5a7d` | Suggestion | 7.6:1 on white. A darker Glacier for links and small icons. |
| Secondary (trees) | Pine | `#1f4d3a` | Suggestion | 9.6:1 on white. Section bands, the rough-in/builder pages. |
| Warm highlight (sun arc) | Larch Gold | `#e0a526` | Suggestion | Nods to Flathead's fall larches. Use sparingly for badges and "new" tags, with Ink text on it (9.1:1). |
| Body secondary text | Slate | `#475569` | Suggestion | Replaces `#64748b` for small grey text: 7.6:1 vs 4.8:1 |
| Borders / dividers | Mist | `#e2e8f0` | Fact (border) | |
| Dark-mode surface | Night | `#020817` / `#0f172a` | Fact (background / primary) | |

Rule of thumb: about 80% Ink + Snow, 15% Pine/Deep Lake, under 5% Glacier/Gold. The logo is one color, so the palette should stay restrained around it.

### Typography [Suggestion]

- **Headings:** a geometric/grotesk with some weight and slightly squared shoulders that echoes the logo's heavy, even strokes. Options: **Archivo** (700–800, optionally Archivo Expanded for the hero), **Outfit**, or **Space Grotesk**.
- **Body:** keep **Figtree** (fact: it's already loaded) at 400/500 and 17–18px base. It pairs cleanly with any of the above.
- **Accent/data:** **JetBrains Mono** or **IBM Plex Mono**, small caps-style labels for measurements ("2,450 SQ FT · 3 BD · SCANNED 10/2026"). This nods to floor plans and blueprints.
- Self-host the fonts with `@nuxt/fonts`, subset them, and use `font-display: swap`.

### Imagery [Suggestion]

- **Replace the AI-style illustrated hero** (the [Fact] current hero is a soft painted landscape) with **real work**: a Matterport **dollhouse** view of a real Flathead property, or a short muted loop orbiting a dollhouse model.
- **Real Flathead photography**: Flathead Lake, Whitefish Mountain, Glacier-area ridgelines, downtown Kalispell and Whitefish. Shoot it yourself or license it. Cool, clear, slightly desaturated grading that lets Ink and Glacier pop.
- **Rough-in proof:** stills from rough-in tours with tagged Mattertags ("1/2" PEX supply, 16" o.c.") plus a before/after slider (open framing vs. finished drywall).
- **Floor plan samples:** clean schematic plans in Ink on Snow, which match the logo's line style.
- No generic stock "VR headset" imagery.

### Iconography & line style [Suggestion]

- Custom or curated **monoline icons with a heavy stroke** (about 2–2.25px at 24px), **square caps and miter joins** to match the logo's flat ends, single color (`currentColor`). The [Fact] current icons mix round-cap and square-cap sets (space-3d, hammer, blueprint, palette, clock). Unify them.
- Pull motifs from the logo: **wave dividers** (the logo's three waves as section separators), the **sun arc** as a frame for portraits or tour thumbnails, and **pine "branch bars"** as a subtle list-bullet or progress motif.
- Optional badge system: each service gets a small circular badge in the logo's style (3D cube, open wall with pipes, floor plan, wrench).

### Layout & components [Suggestion]

- **Sticky header:** logo + "Scan Montana" wordmark, nav (Services ▾, Portfolio, Pricing, About, FAQ), a **phone/tap-to-call** link `[phone]`, and a primary **"Book a Scan"** button.
- **Hero:** H1, one-line subhead, primary CTA "Book a Scan" plus secondary CTA "View a Live Tour" (opens an embedded tour). Trust strip below: "Serving Kalispell · Whitefish · Columbia Falls · Bigfork · Polson", "Replies within 24 hours" (Fact: the site already says "Usually replies within 24 hours"), `[Matterport partner badge if applicable]`.
- **Service cards** (4) with icon, 1–2 lines, "Learn more →" links to the service pages.
- **Tour embeds:** lazy-loaded Matterport iframes behind a static poster image plus a "Click to explore" button (good for performance).
- **Process strip:** Book → We scan (`[X]` hrs on-site) → Tour delivered in `[turnaround]` → Share anywhere.
- **Pricing cards**, a **testimonial carousel** (or a static grid), an **FAQ accordion**, and a **contact block** with form + phone + email + service area map (static image; Mapbox only on interaction).
- **Footer:** NAP (name, address/service area, phone), town links, service links, social, Matterport partner badge, and a wave divider on top.
- Corner radius: keep it modest (4–8px) to stay close to the logo's crisp geometry. No pill-shaped everything.

### Motion [Suggestion]

- Subtle and purposeful. Use a slow dollhouse orbit or parallax on the hero, fade/slide-up reveals on sections (respecting `prefers-reduced-motion`), and an optional **"draw-on" SVG animation of the logo's sun arc** on first load (stroke-dashoffset, under 1s).
- Replace the bouncing triangle scroll cue with a small monoline chevron, or just let the next section peek in.

### Dark mode [Suggestion]

- Keep it (Fact: the site already supports it). Night `#020817` background, Snow logo/text, Glacier `#24ccff` for links and accents (it passes at 10.6:1 on Night), and Pine tinted lighter for bands.
- Load **only one** hero image. Use `<picture>`/`media="(prefers-color-scheme: dark)"` or a CSS class toggle, so both images aren't downloaded.

### Accessibility [Suggestion]

- Body text 4.5:1 or better, large text 3:1 or better. Use Slate `#475569` or darker for secondary text, and never Glacier text on white.
- Visible focus rings (Glacier, 2px offset), 44px minimum tap targets, labelled form fields with real `<label>`s, an accessible name on the logo link ("Scan Montana, home"), and `title` attributes on tour iframes.
- Provide a text summary and floor-plan image alongside each 3D tour for people who can't use the 3D viewer.

## Proposed sitemap [Suggestion]

```
/                              Home
/services/3d-virtual-tours     3D Virtual Tours (Matterport)
/services/rough-in-scans       Rough-in Scans (pre-drywall documentation)
/services/floor-plans          Floor Plans
/services/custom               Custom Solutions (commercial, insurance, events, etc.)
/portfolio                     Portfolio (embedded tours, filter by type/town)
/pricing                       Pricing & packages
/about                         About
/faq                           FAQ
/contact                       Contact / Book a Scan
/areas/kalispell               Town landing pages (×5)
/areas/whitefish
/areas/columbia-falls
/areas/bigfork
/areas/polson
/blog                          Blog / guides (optional, phase 2)
```

Nuxt Content works well here: one Markdown file per service, town, and blog post, with frontmatter for title/meta/schema.

## Page-by-page content ideas [Suggestion]

### Home
- **H1:** Matterport 3D Tours & Rough-in Scans in the Flathead Valley
- **Subhead:** Immersive virtual tours, floor plans, and pre-drywall documentation for homes and buildings from Kalispell to Polson.
- **H2s:** Explore a live tour · What we scan · Who we work with (Realtors / Builders / Rental hosts / Property & insurance) · How it works · Pricing at a glance · What clients say · Serving the Flathead Valley · Book your scan
- **CTAs:** Book a Scan (primary) · View a Live Tour · Call `[phone]`

### 3D Virtual Tours
- **H1:** Matterport 3D Virtual Tours for Flathead Valley Listings
- **H2s:** Walk through before you drive out · What's included (tour, dollhouse, `[MLS-friendly unbranded link]`, `[photos?]`, `[floor plan add-on]`) · Live example · Turnaround `[X business days]` · Pricing `[price]` · FAQ
- **CTA:** Book a Listing Scan

### Rough-in Scans
- **H1:** Rough-in Scans: See Inside Your Walls After the Drywall Goes Up
- **H2s:** Document electrical, plumbing & HVAC before close-up · Why builders and homeowners use it (future remodels, nail/screw strikes, warranty disputes, inspection records, insurance) · Measure from the tour later · Before/after slider · Scan at multiple phases (`[package]`) · Pricing `[price]`
- **CTA:** Schedule a Pre-Drywall Scan. Note: book before insulation/drywall day.

### Floor Plans
- **H1:** Accurate Floor Plans from Your 3D Scan
- **H2s:** Schematic 2D plans with room measurements · Sample plan · Formats `[PDF/PNG/…]` · Accuracy note (state what Matterport claims, with a disclaimer; don't overstate it) · Add-on pricing `[price]`
- **CTA:** Add a Floor Plan to Your Scan

### Custom Solutions
- **H1:** Custom 3D Scanning for Commercial, Insurance & Unique Spaces
- **H2s:** Commercial and retail spaces · Pre-loss / insurance documentation · Facility management · Venues and short-term rentals · Construction progress (multi-visit) · Tell us what you need
- **CTA:** Describe Your Project

### Portfolio
- **H1:** Explore Our 3D Tours
- Filterable grid (Residential / Rough-in / Commercial / Rental; by town). Each card shows a poster image, type, town, and sq ft `[if shareable]`, then opens an embedded tour (lazy).
- **CTA:** Want your property to look like this? Book a Scan

### Pricing
- **H1:** Simple, Transparent Pricing
- Packages (placeholders): **Essentials** `[price]` up to `[sq ft]` · **Listing Pro** `[price]` tour + floor plan + `[photos]` · **Builder Rough-in** `[price]` per phase / `[multi-phase package]` · **Custom** quote. Add travel and hosting notes `[Matterport hosting duration/fees]`.
- **CTA:** Get a Quote / Book Now

### About
- **H1:** Local 3D Scanning, Based in the Flathead Valley
- **H2s:** Who we are `[owner name, photo, story]` · Our equipment `[camera model, e.g. Pro3, only if true]` · Why we do it · Service area map
- **CTA:** Let's work together

### FAQ
- How long does a scan take? `[X]` · When will I get my tour? `[turnaround]` · How should I prep the home? · Can tours go on the MLS / Zillow? `[confirm]` · How long is the tour hosted? `[confirm]` · Can you scan during rough-in or after insulation? · Do you travel outside the Flathead? `[confirm]` · Do you scan commercial spaces? · What do floor plans include?
- Mark it up with **FAQPage** schema.

### Contact / Book
- **H1:** Book a Scan
- Form fields: name, email, phone, **service (dropdown)**, property address/town, approx. sq ft, preferred date, message. Show phone `[phone]`, email `[email]`, service area, and "Usually replies within 24 hours" (Fact: current site copy).

### Town landing pages (×5)
- **H1 pattern:** Matterport 3D Tours & Rough-in Scans in `[Town]`, MT
- Unique local content per town: neighborhoods and property types (e.g. lake homes in Bigfork/Polson, resort condos in Whitefish, new construction in Kalispell). These are suggestions to verify, and each needs an embedded local tour plus local testimonials. Don't make them thin duplicates.
- **CTA:** Book a Scan in `[Town]`

## Audience segments [Suggestion]

| Segment | Pain / motivation | Key message | Lead service |
|---|---|---|---|
| **Realtors / brokers** | Out-of-state buyers (Flathead draws many), standing out on listings | "Let buyers walk through from anywhere." | 3D Tours + Floor Plans |
| **Builders / contractors / homeowners building** | Lost knowledge once walls close, future remodels, warranty disputes | "See inside your walls forever." | Rough-in Scans (multi-phase) |
| **Short-term rental hosts** (Whitefish, Bigfork, lake properties) | Booking confidence, fewer "not as pictured" complaints | "Guests book faster when they've already walked in." | 3D Tours |
| **Insurance / property managers** | Pre-loss documentation, condition records, remote inspections | "A measurable record of every room." | Custom / 3D Tours |
| **Commercial** (retail, venues, offices, facilities) | Marketing, facility documentation, planning | "Show and manage your space remotely." | Custom + Floor Plans |

## Trust elements [Suggestion]

- **Testimonials:** 3–6 real quotes with name, role, and town (e.g. "`[Name]`, `[Brokerage]`, Whitefish"). Collect them via the GBP review link.
- **Matterport Service Partner badge:** only if Scan Montana is actually enrolled `[confirm]`. Don't display it otherwise.
- **Turnaround promise:** e.g. "Tours delivered in `[X]` business days". The only current fact is "Usually replies within 24 hours" (form response time).
- **Proof of work:** live embedded tours, number of spaces scanned `[N]`, and logos of brokerages/builders worked with `[with permission]`.
- **Local identity:** owner photo and story, "Locally owned in `[town]`", and a service area map.
- Insured / licensed `[confirm before stating]`.

## SEO plan [Suggestion]

### Titles & meta (examples, under 60 / ~155 chars)
- **Home title:** `Matterport 3D Tours & Rough-in Scans | Scan Montana`
- **Home meta:** `Matterport 3D virtual tours, rough-in scans & floor plans in Kalispell, Whitefish, Columbia Falls, Bigfork & Polson. Book your scan today.` (about 140 chars). Replaces the current 190-char meta that says "Virtual Reality House" [Fact].
- **Service:** `Rough-in Scans in the Flathead Valley | Scan Montana`
- **Town:** `3D Virtual Tours in Whitefish, MT | Scan Montana`

### Structured data
- **LocalBusiness** (or `ProfessionalService`) JSON-LD on every page: name "Scan Montana LLC", url, logo, `telephone: [phone]`, `email: [email]`, `areaServed` (5 towns + Flathead County), `address` or service-area-only setup, `sameAs` (GBP, social), `openingHours [hours]`.
- **Service** schema per service page, **FAQPage** on the FAQ, **BreadcrumbList**, and **VideoObject/3DModel**-style descriptions are optional.
- Use `nuxt-schema-org` (part of `@nuxtjs/seo`) for this.

### Google Business Profile
- **[Fact]** No GBP was found. **[Suggestion]** Create one as a service-area business (hide the address if home-based), category "Photographer" / "Real estate photographer" / `[closest Matterport-type category]`, list all services, upload tour screenshots, add the booking URL, and request reviews after every job.
- Keep NAP identical on the site, GBP, and citations (Yelp, Bing Places, Apple Business Connect, local chamber listings `[Kalispell/Whitefish chambers]`).

### Local keywords (to validate in a keyword tool)
- matterport kalispell / whitefish / flathead valley
- 3d virtual tour kalispell mt, virtual tour real estate whitefish
- rough-in scan / pre-drywall scan montana, pre-drywall documentation
- floor plans for real estate listings kalispell
- 3d scanning commercial building flathead, insurance documentation 3d scan montana

### Blog / guide topics
1. What is a rough-in scan, and why should you get one before drywall?
2. How to prep your home for a Matterport scan (checklist)
3. Do 3D tours help sell homes faster? What the data says `[cite sources]`
4. Matterport for short-term rentals in Whitefish & Bigfork
5. Using a 3D scan to plan a remodel: measuring from the tour
6. Pre-loss documentation: protecting your Flathead home with a 3D record
7. Floor plans vs. 3D tours: which does your listing need?
8. Multi-phase construction documentation for builders

### Domain history
- **[Fact]** The domain was formerly a police/fire scanner radio site. **[Suggestion]** Check Search Console for old URLs still receiving traffic or links. 301 relevant ones to the home page, let irrelevant ones 410, disavow spammy backlinks only if a manual action appears, and expect some irrelevant "scanner" queries early on. Make the real business category unambiguous in titles, schema, and GBP.

## Quick fixes (do first)

1. **[Fact→Fix]** Remove the stray outline/focus box around the "S" in "Services we Provide" (likely an anchor/`:target` or focus outline on the heading).
2. **[Fact→Fix]** Restyle the scroll arrow (currently an unstyled bouncing triangle) or remove it.
3. **[Fact→Fix]** Make "Learn More" a real secondary button (outlined Ink, 44px tall) that scrolls to Services, or replace it with "View a Live Tour".
4. **[Fact→Fix]** Raise low-contrast small grey text to Slate `#475569` or darker (light) / `#cbd5e1` (dark), with a minimum size of 16px.
5. **[Fact→Fix]** Performance (mobile Lighthouse 78):
   - Stop shipping the 369 KiB `sqlite3.wasm` to the client. Nuxt Content v3 uses it for client-side queries. Prerender the page, query only at build/server time, or move to `queryCollection` on the server so the WASM isn't needed in the browser.
   - Load only one hero image (light **or** dark), sized and in modern formats (AVIF/WebP via Netlify Image CDN / `@nuxt/image`), with `fetchpriority="high"` on the LCP image.
   - Lazy-load Mapbox: show a static map image and load the interactive map on click or when it scrolls into view. Or drop it for a simple service-area graphic.
6. **[Fact→Fix]** Rewrite the meta description (under 160 chars, drop "Virtual Reality House").
7. **[Fact→Fix]** Add LocalBusiness JSON-LD.
8. **[Fact→Fix]** Add phone `[phone]`, email `[email]`, and service area to the header/footer, with tap-to-call on mobile.
9. **[Suggestion]** Add Open Graph/Twitter image (logo on Snow plus a tour still), canonical URL, `sitemap.xml`, and `robots.txt`.
10. **[Suggestion]** Embed at least one real Matterport tour on the home page right away.

## Next steps

- [ ] Sam: gather the business facts: phone, email, hours, owner bio/photo, pricing, turnaround, hosting terms, Matterport partner status, camera model, insurance.
- [ ] Collect 5–10 shareable tour links (with client permission) plus 3+ testimonials.
- [ ] Ship the quick fixes and re-run mobile Lighthouse (target 90+).
- [ ] Create and verify the Google Business Profile, then add the review link to the post-job email.
- [ ] Build the design tokens (palette, type, icon set) in Tailwind config around the final logo.
- [ ] Build service pages, then Portfolio, Pricing, About/FAQ, then town pages.
- [ ] Set up Search Console and Analytics, and review old scanner-site URLs.
- [ ] Phase 2: blog/guides, more town content, citations.
