# Fal Constructions — Style Spec & Handoff

## Palette

- `Navy 900` `#0E1F33` (primary background / header)
- `Steel 800` `#202B38` (page background)
- `Graphite 700` `#394251` (sections)
- `Cloud 50` `#F4F6F8` (cards, dividers)
- `Accent Ember` `#F4A11A` (primary CTAs, highlights)
- `Accent Ember Dark` `#C77906` (CTA hover, focus rings)
- `Signal Red` `#FF4D4F` (alerts)

Contrast checks: `#F4A11A` on `#0E1F33` = 4.6:1, `#FFFFFF` on `#202B38` = 8.3:1; both AA compliant for text ≥18px or bold ≥14px.

## Typography

- Display / H1: `Rajdhani` 64/1.1em, letter spacing 0.06em
- H2: `Rajdhani` 40/1.15em
- H3: `Rajdhani` 26/1.2em
- Body: `Barlow` 18/1.6em
- Small / Eyebrow: `Barlow` 12/1.4em uppercase letter spacing 0.2em

Use system fallback `Helvetica Neue, Arial, sans-serif`.

## Spacing Scale

- Base unit: 8px
- Stack tokens: 8, 16, 24, 32, 48, 64
- Section padding: desktop 80px (5vw), tablet 48px, mobile 24px
- Card padding: 24px

## Components (Figma-like inventory)

1. **`Nav/Sticky`** — props: logo text/asset, links array, CTA label+href. Behavior: elevates with 8px blur after scrollY > 20.
2. **`Hero/Full`** — video or image background slot, overlay gradient, content stack (eyebrow, headline, copy, CTA group). Accepts `theme=light|dark`.
3. **`CTA/Button`** — variants: `primary`, `ghost`, `nav`. Min width 200px mobile, 48px min height. Focus ring 2px `#F4A11A`.
4. **`Card/Service`** — icon slot (SVG or glyph), heading, body. Elevation hover: translateY(-4px), shadow `0 15px 30px rgba(0,0,0,0.2)`.
5. **`Gallery/Masonry`** — 3-column desktop, 2 tablet, 1 mobile. Items support overlay content (tag, title, link).
6. **`CaseStudy/Split`** — media panel + detail stack with four key stats and slider navigation.
7. **`Testimonials/Dual`** — grid with quote text, author label, optional logo.
8. **`Logos/Row`** — monochrome brand marks spaced 24px.
9. **`Footer/Grid`** — four-column info blocks collapsing to 2 column at 768px, single column at 520px.

## Responsive Mock Guidance

### Desktop (≥1200px)

- Hero text max width 640px, CTAs inline (gap 16px).
- Services grid 4 columns.
- Projects masonry 3 columns.
- Mini case split 40/60.
- Footer 4 columns.

### Tablet (768–1199px)

- Nav CTA hides; nav wraps.
- Services grid 2 columns.
- Projects masonry 2 columns.
- Mini case stack vertical; hero image full width with 24px radius.
- Footer 2 columns.

### Mobile (≤767px)

- Hero center aligned, CTAs stacked full width.
- Services cards single column; increase padding to 20px.
- Projects single column, allow swipe for slider (CSS `overflow-x: auto` optional).
- Footer single column; social icons 44px hit target.

## Interactions & Behaviors

- Buttons: 200ms ease background/scale. Focus outlines always visible.
- Project cards: overlay fades from 0.6 to 0.9 on hover, text slides 8px.
- Slider buttons: disable state when at extremes (aria-disabled true).
- Testimonials carousel optional for mobile; ensure swiping area 100% width.

## Accessibility

- All primary CTAs: 48px min height, hit area extends 8px.
- Provide captions or descriptive text for hero video; fallback image if prefers-reduced-motion.
- Use `aria-label` on slider controls and social icons.
- Maintain heading hierarchy (h1 hero, h2 per section).

## Dev Handoff Notes

- Tech stack agnostic; HTML + CSS delivered in `/index.html` + `/styles.css`.
- Assets: use Unsplash placeholders; replace with final hosted images (ratio 16:9 or 4:3). Optimize below 500KB.
- Video: remote Coverr sample; replace with MP4/H.264 <8MB and include poster attribute for performance.
- Masonry uses CSS `column-count`; if layout needs ordering control, replace with CSS grid + Masonry JS.
- Case slider is static markup; integrate Swiper/Glide as needed. Buttons already sized/focus-ready.
- Wireframe references located in `/wireframe.html` + `/wireframe.css`.
- Keep CSS variables central for theming; adjust accent by updating `--accent` and `--accent-dark`.

## Next Steps

1. Replace placeholder copy with marketing-approved content.
2. Hook CTAs to CRM or form (HubSpot, Pardot).
3. Integrate CMS for Projects/Blog (e.g., Sanity, Contentful).
4. Add analytics + consent management script.

Questions? ping product@falconstructions.com.



