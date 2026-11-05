# Curaval Castle — Brand Identity Guide

> **For Codex / developers:** This file is the single source of truth for the visual identity of the Curaval Castle website. Follow it strictly when building UI. Logo file: `brand-assets/logo-full.png`.

---

## 1. Brand Overview

**Name:** Curaval Castle
**Logo concept:** A circle of soft teal dots (a "castle" / protective ring, also reads as a stylised "C") with a guiding star and small sparkles rising from it. Meaning: care, trust, guidance, a touch of magic and hope.
**Brand personality:** Calm, trustworthy, caring, modern, optimistic, premium-but-approachable.
**Tone of voice:** Warm, clear, reassuring. Short sentences. No jargon. Confident, never pushy.

> Note: the brand name suggests a care / health / wellbeing domain ("Cura" = care). Keep the design clean, airy and reassuring.

---

## 2. Logo

- **Primary logo:** symbol (dots + star + sparkles) on the left, wordmark "Curaval / Castle" stacked on two lines on the right.
- **Files:** `brand-assets/logo-full.png` (full lockup, white background). Ask the owner for an SVG / transparent PNG if available; until then, recreate the symbol as inline SVG for crisp rendering where possible.
- **Clear space:** keep at least the height of the letter "C" in the wordmark free on all sides.
- **Minimum size:** full logo 140px wide on screen; below that use the symbol only (star + dots).
- **Backgrounds:** use on white or very light backgrounds. On dark backgrounds, use the wordmark in white and keep the teal symbol.
- **Don'ts:** don't stretch, rotate, recolor outside the palette, add shadows/outlines, or place on busy images without an overlay.

---

## 3. Color Palette

Colors were sampled from the logo.

| Role | Name | HEX | Usage |
|---|---|---|---|
| Primary | Castle Teal | `#50CCBC` | Brand color, buttons, highlights, icons |
| Primary (light) | Star Mint | `#5DD5CC` | Gradients, hover highlights |
| Primary (deep) | Deep Teal | `#3DB5B8` | Gradient end, pressed states, links on white |
| Text / Dark | Midnight Navy | `#202838` | Headings, body text, dark sections, footer |
| Background | White | `#FFFFFF` | Main background |
| Surface | Mist | `#F2FBFA` | Alternate sections, cards |
| Border | Soft Line | `#DDEFED` | Dividers, card borders |
| Muted text | Slate | `#5B6676` | Secondary text, captions |

**Brand gradient** (taken from the star): `linear-gradient(160deg, #5DD5CC 0%, #3DB5B8 100%)`

**Accessibility notes**
- Teal `#50CCBC` on white has low contrast for text — **do not use it for body text or small text**. Use Midnight Navy for text; use Deep Teal `#2A9AA0` (or darker) if teal text is required.
- Text on teal buttons: use Midnight Navy `#202838` (contrast passes), not white.
- Target WCAG AA (4.5:1) for all text.

### CSS Variables

```css
:root {
  /* Brand */
  --color-primary: #50CCBC;
  --color-primary-light: #5DD5CC;
  --color-primary-deep: #3DB5B8;
  --color-primary-link: #2A9AA0;

  /* Neutrals */
  --color-ink: #202838;
  --color-muted: #5B6676;
  --color-bg: #FFFFFF;
  --color-surface: #F2FBFA;
  --color-border: #DDEFED;

  /* Gradient */
  --gradient-brand: linear-gradient(160deg, #5DD5CC 0%, #3DB5B8 100%);

  /* Typography */
  --font-heading: "Lora", "Source Serif 4", Georgia, serif;
  --font-body: "Inter", "Segoe UI", system-ui, -apple-system, sans-serif;
  --font-arabic: "Cairo", "Tajawal", sans-serif;

  /* Shape & spacing */
  --radius-sm: 8px;
  --radius-md: 14px;
  --radius-lg: 24px;
  --radius-pill: 999px;
  --shadow-soft: 0 8px 30px rgba(32, 40, 56, 0.08);
  --container: 1160px;
}
```

### Tailwind config (if used)

```js
theme: {
  extend: {
    colors: {
      brand: { DEFAULT: '#50CCBC', light: '#5DD5CC', deep: '#3DB5B8', link: '#2A9AA0' },
      ink: '#202838',
      muted: '#5B6676',
      surface: '#F2FBFA',
      line: '#DDEFED',
    },
    fontFamily: {
      heading: ['Lora', 'Georgia', 'serif'],
      body: ['Inter', 'system-ui', 'sans-serif'],
      arabic: ['Cairo', 'sans-serif'],
    },
    borderRadius: { md: '14px', lg: '24px' },
  },
}
```

---

## 4. Typography

The wordmark uses a **warm, humanist serif** (similar to Lora / Source Serif). Mirror that in headings; pair with a clean sans for body.

- **Headings:** Lora (Google Fonts), weights 500–700, color Midnight Navy.
- **Body / UI:** Inter, weights 400/500/600.
- **Arabic (if the site is bilingual / RTL):** Cairo or Tajawal. Use `dir="rtl"` and logical CSS properties (`margin-inline-start`, etc.).

| Style | Size (desktop / mobile) | Weight | Line height |
|---|---|---|---|
| H1 | 56px / 36px | 700 | 1.1 |
| H2 | 40px / 28px | 600 | 1.2 |
| H3 | 28px / 22px | 600 | 1.3 |
| Body L | 18px | 400 | 1.7 |
| Body | 16px | 400 | 1.6 |
| Caption | 14px | 400 | 1.5 |
| Button | 16px | 600 | 1 |

---

## 5. Graphic Elements

- **Dots:** solid circles in Castle Teal. Use as section decorations — a loose arc/ring pattern of 8–12 dots, varying sizes slightly. Low opacity (10–25%) when used as background.
- **Sparkles:** four-pointed concave stars (like in the logo) in teal. Use sparingly: near headings, CTAs, icons for "new" or "highlight". Max 3–5 per screen.
- **Hero star:** the large gradient star can be used as a hero/illustration accent or loading/section divider.
- **Style:** flat, soft, rounded. No harsh shadows, no heavy outlines, no neon.
- **Iconography:** rounded line icons (2px stroke, round caps), Midnight Navy or Castle Teal (Lucide / Phosphor recommended).
- **Imagery:** bright, natural light, real people, calm and welcoming. Optional soft teal overlay (`rgba(80,204,188,0.12)`).

---

## 6. UI Components

**Buttons**
- Primary: background `--color-primary`, text `--color-ink`, radius pill, padding `14px 28px`, hover → `--color-primary-light` + slight lift (`translateY(-1px)`).
- Secondary: transparent, 2px border `--color-ink`, text `--color-ink`, hover → fill `--color-surface`.
- Ghost/link: text `--color-primary-link`, underline on hover.
- Focus: 3px outline `rgba(80,204,188,0.5)`, offset 2px (never remove focus states).

**Cards**
- White background, 1px `--color-border`, radius `--radius-md`, `--shadow-soft` on hover. Padding 24–32px.

**Forms**
- Inputs: height 48px, radius 10px, 1px `--color-border`, focus border `--color-primary` + soft teal ring.
- Labels above fields, 14px, weight 500, color ink.

**Navigation**
- Sticky white header, logo on the start side, links in ink color, active link with 2px teal underline, one primary CTA button at the end.

**Footer**
- Background Midnight Navy `#202838`, text white / 70% white, links hover teal, logo wordmark in white.

---

## 7. Layout & Spacing

- 8px spacing scale: 4, 8, 16, 24, 32, 48, 64, 96, 128.
- Container max-width 1160px, side padding 24px (16px on mobile).
- Section vertical padding: 96px desktop / 56px mobile.
- Alternate section backgrounds between White and Mist for rhythm.
- Generous whitespace — the brand should feel airy and calm.
- Mobile-first, breakpoints: 640 / 768 / 1024 / 1280.

---

## 8. Motion

- Subtle and calm: 200–300ms, `ease-out`.
- Fade-up on scroll (12–20px), gentle float/twinkle on sparkles.
- Respect `prefers-reduced-motion`.

---

## 9. Page Structure Suggestion (Homepage)

1. Header (logo + nav + CTA)
2. Hero — H1, short supporting line, primary + secondary CTA, hero star / dots decoration
3. Services / What we do — 3–4 cards
4. How it works — 3 steps with numbered teal dots
5. About / Why Curaval Castle — trust points
6. Testimonials (optional)
7. Contact / CTA banner — gradient background `--gradient-brand`, ink text
8. Footer

---

## 10. Implementation Checklist for Codex

- [ ] Use the CSS variables / Tailwind tokens above — no hard-coded random colors.
- [ ] Load Lora + Inter (and Cairo if Arabic) from Google Fonts with `display=swap`.
- [ ] Use `logo-full.png` in the header; set `alt="Curaval Castle"`; provide a favicon from the symbol (star + dots).
- [ ] Ensure text contrast meets WCAG AA.
- [ ] Fully responsive and RTL-ready.
- [ ] Add meta tags: `theme-color: #50CCBC`, Open Graph image using the logo.
- [ ] Keep the design clean: lots of white space, rounded shapes, teal accents only.
