# CAVIAR-LOUIE-DESIGN.md
> Brand design system for AI coding agents. Drop this file into your project root and reference it in every build, rebuild, and component prompt. Do not deviate from the tokens, rules, or patterns defined here.
> Last updated: May 2026. Maintained by Bespoke MKTG for Caviar Louie, St. Louis MO.

---

## 0. BRAND IDENTITY

**Concept.** Caviar Louie is a caviar bar and dining concept in St. Louis, Missouri. The positioning is elevated American heritage — confident, refined, celebratory, and approachable. Nantucket meets New Orleans. A place for date nights, birthdays, and special occasions. Not cold. Not pretentious.

**The room is the product.** This site must feel like the room before anyone walks in. Atmosphere first, information second.

**Tagline.** "St. Louis' Finest Caviar Experience"

**Permanent descriptor.** "St. Louis Caviar Bar" — appears in 11px tracked caps under the nav logo, under the footer logo, and as a watermark element in the hero. Never omit this.

**Established.** Est. 2025

**Logo.** Circular crest PNG at `logo.png`. Contains a sturgeon illustration, pearl bead field, gold ring, navy ring, red accent ring. Use `<img src="logo.png" class="site-logo" alt="Caviar Louie">`. Never recreate in SVG. The crest is the gravitational center of the entire hero — it anchors everything.

**The sturgeon.** The engraving-style sturgeon illustration inside the crest is the brand's native illustration asset. Used as a large-scale watermark in the hero and menu sections. This is how the site creates atmosphere without photography. The sturgeon at low opacity behind content turns a dark background into a world.

**The pearl bead motif.** Derived from the bead field in the logo. Expressed as a CSS radial-gradient dot texture throughout the site. This is the brand's fingerprint and must appear in every dark section.

**One rule above all others.** If a design choice could appear on any generic restaurant or SaaS site, it is wrong. Every decision must reference the brand world: pearls, gold, sturgeon, celebration, heritage, St. Louis.

---

## 1. COLOR TOKENS

```css
:root {
  --cl-navy:           #1B2A6B;
  --cl-navy-deep:      #0E1A40;
  --cl-navy-mid:       #162258;
  --cl-gold:           #C9A84C;
  --cl-gold-light:     #DFC07A;
  --cl-gold-glow:      rgba(201, 168, 76, 0.15);
  --cl-gold-dim:       rgba(201, 168, 76, 0.08);
  --cl-gold-border:    rgba(201, 168, 76, 0.22);
  --cl-gold-ring:      rgba(201, 168, 76, 0.10);
  --cl-gold-texture:   rgba(201, 168, 76, 0.09);
  --cl-red:            #C8102E;
  --cl-cream:          #F9F6EF;
  --cl-cream-dim:      rgba(249, 246, 239, 0.06);
  --cl-text-cream:     #F0EBE0;
  --cl-text-muted:     rgba(240, 235, 224, 0.48);
  --cl-text-navy:      #0E1A40;
  --cl-text-muted-lt:  rgba(14, 26, 64, 0.55);
  --cl-shadow-sm:      0 2px 12px rgba(14, 26, 64, 0.18);
  --cl-shadow-md:      0 8px 40px rgba(14, 26, 64, 0.28);
  --cl-shadow-gold:    0 0 48px rgba(201, 168, 76, 0.10);
}
```

**Hard color rules.**
- Gold fills buttons. Solid. Never gradient. Never outline-only for primary actions.
- Red appears exactly once per page — one thin ring element in the hero. Never on buttons or text.
- Cream is the light world. `--cl-navy-deep` is the dark world. They strictly alternate by section.
- Never use `#ffffff` as a background. Never use `#000000` in any shadow or border.
- All borders: alpha tokens only. `border: 1px solid #ccc` is banned unconditionally.

---

## 2. TYPOGRAPHY

Load via `<link>` tag in `<head>`:
`https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,400;1,500;1,600&family=Work+Sans:wght@300;400;500;600;700&display=swap`

```css
:root {
  --font-display: 'Playfair Display', Georgia, serif;
  --font-body:    'Work Sans', system-ui, sans-serif;
}
```

### Type Scale

The defining characteristic of every great bar and restaurant site (Death & Co, Dead Rabbit, Dante) is violent contrast between type sizes. The nav is tiny and restrained. The hero is enormous and commanding. Section headers are large enough to feel like architecture, not just labels. The previous version of this spec used safe, conservative sizes. This version does not.

| Role | Font | Weight | Size | Line-Height | Tracking | Case |
|---|---|---|---|---|---|---|
| Hero Crest | logo.png | n/a | 380px width | n/a | n/a | n/a |
| Hero Headline | Playfair Display | 700 | `clamp(3.6rem, 8vw, 6.5rem)` | 1.06 | -0.02em | Sentence |
| Hero Subhead | Work Sans | 300 | 13px | 1.4 | 0.28em | ALL CAPS |
| Section H2 | Playfair Display | 600 | `clamp(2.4rem, 5vw, 4rem)` | 1.1 | -0.015em | Sentence |
| About Mood Words | Playfair Display | 700 | `clamp(3rem, 6vw, 5rem)` | 1.0 | -0.02em | Sentence |
| Pull Quote | Playfair Display italic | 400 | `clamp(1.15rem, 2.4vw, 1.5rem)` | 1.75 | 0 | Sentence |
| Eyebrow / Label | Work Sans | 600 | 11px | 1 | 0.24em | ALL CAPS |
| Nav Link | Work Sans | 600 | 11px | 1 | 0.18em | ALL CAPS |
| Menu Col Header | Work Sans | 700 | 13px | 1 | 0.22em | ALL CAPS |
| Menu Item Name | Playfair Display | 500 | 1.05rem | 1.3 | 0 | Sentence |
| Body | Work Sans | 400 | 16px | 1.68 | 0 | Sentence |
| Body Small | Work Sans | 400 | 14px | 1.6 | 0 | Sentence |
| Price | Work Sans | 700 | 15px | 1 | 0.04em | Default |
| Button | Work Sans | 600 | 11px | 1 | 0.16em | ALL CAPS |
| Marquee Quote | Playfair Display italic | 400 | 15px | 1 | 0.02em | Sentence |
| Footer Col Head | Work Sans | 600 | 11px | 1 | 0.20em | ALL CAPS |

**The size relationship rule.** Hero headline at `clamp(3.6rem, 8vw, 6.5rem)` paired with a 13px subhead creates a 6:1 to 8:1 size ratio. That ratio IS the drama. The subhead should feel like a whisper beneath a shout. If both sizes feel similar in visual weight, the hierarchy is broken.

**Non-negotiable rules.**
- Playfair Display: hero headline, H2s, menu item names, pull quotes, marquee, mood words. Nowhere else.
- Work Sans: nav, buttons, labels, eyebrows, body, footer, form fields, prices, subheads. Nowhere else.
- Never set hero headline below 3.6rem on any viewport.
- Never set section H2s below 2.4rem.
- Letter-spacing on all Work Sans labels: 0.18em minimum.
- Never use Inter, Roboto, Arial, or system-ui as a visible display choice.

---

## 3. SPACING SYSTEM

Base unit: 8px

```
4px   — micro
8px   — tight component gaps
16px  — internal padding
24px  — between related elements
32px  — between distinct elements
48px  — component vertical padding (mobile)
64px  — section sub-grouping
96px  — section vertical padding (desktop)
128px — hero padding top and bottom
```

Max content width: 1160px. Padding: `0 40px` desktop, `0 20px` mobile.

Layout ratios: Experience section 55/45. Menu columns 47/6/47. Standard 50/50.

---

## 4. THE PEARL DOT TEXTURE

The single most important brand-specific CSS element. Derived from the pearl bead field in the logo. Every dark section carries it. It is the brand's fingerprint.

```css
.pearl-texture {
  position: relative;
}
.pearl-texture::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: radial-gradient(
    circle,
    var(--cl-gold-texture) 1.5px,
    transparent 1.5px
  );
  background-size: 28px 28px;
  pointer-events: none;
  z-index: 0;
}

.pearl-texture-light::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: radial-gradient(
    circle,
    rgba(27, 42, 107, 0.055) 1.5px,
    transparent 1.5px
  );
  background-size: 28px 28px;
  pointer-events: none;
  z-index: 0;
}
```

Applies to: hero, press marquee, menu section, footer, photo placeholders.
Hard limits: dot size 1.5px max. Never above 0.10 opacity. Supporting texture, never foreground.

---

## 5. THE STURGEON WATERMARK SYSTEM

The sturgeon engraving from the logo is the brand's primary atmospheric element when photography is not available. It functions exactly the way Death & Co's hand-lettered script functions in their hero — it creates a sense of world, craft, and specificity that no generic background can achieve.

Use `logo.png` with `mix-blend-mode: luminosity` as a fallback if a standalone sturgeon PNG is not available. The full crest at very low opacity still reads as a brand watermark and is preferable to a plain dark background.

```css
.sturgeon-hero {
  position: absolute;
  width: 700px;
  height: auto;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -42%);
  opacity: 0.05;
  filter: sepia(1) saturate(2) hue-rotate(5deg) brightness(1.6);
  pointer-events: none;
  z-index: 0;
  mix-blend-mode: luminosity;
}

.sturgeon-menu {
  position: absolute;
  width: 900px;
  height: auto;
  bottom: -60px;
  right: -120px;
  opacity: 0.04;
  filter: sepia(1) saturate(2) hue-rotate(5deg) brightness(1.8);
  pointer-events: none;
  z-index: 0;
  mix-blend-mode: luminosity;
}
```

Rules: hero opacity 0.05 max. Menu opacity 0.04 max. Never on cream sections. Never above 0.07. Must be felt, not seen directly.

---

## 6. DECORATIVE RING SYSTEM

Derived from the concentric ring structure of the crest logo. CSS-only. Purely decorative.

```css
.ring {
  position: absolute;
  border-radius: 50%;
  pointer-events: none;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.ring-1 { width: 440px;  height: 440px;  border: 1px solid rgba(201,168,76,0.18); }
.ring-2 { width: 640px;  height: 640px;  border: 1px solid rgba(201,168,76,0.12); }
.ring-3 { width: 860px;  height: 860px;  border: 1px solid rgba(201,168,76,0.07); }
.ring-4 { width: 1100px; height: 1100px; border: 1px solid rgba(201,168,76,0.04); }
.ring-red {
  width: 480px;
  height: 480px;
  border: 1px solid rgba(200, 16, 46, 0.20);
}
```

All four gold rings plus the one red ring in the hero, all centered on the logo position. Red ring sits between ring-1 and ring-2. Mobile: scale to 55%. Never use rings as button or card borders.

---

## 7. COMPONENT SYSTEM

### 7.1 Buttons

```css
.btn-primary {
  font-family: var(--font-body);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  background: var(--cl-gold);
  color: var(--cl-navy-deep);
  border: none;
  padding: 15px 32px;
  border-radius: 2px;
  min-height: 50px;
  cursor: pointer;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: background 0.18s ease, transform 0.15s ease;
}
.btn-primary:hover { background: var(--cl-gold-light); transform: translateY(-1px); }
.btn-primary:focus-visible { outline: 2px solid var(--cl-gold); outline-offset: 3px; }

.btn-ghost {
  font-family: var(--font-body);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  background: transparent;
  color: var(--cl-gold);
  border: 1px solid var(--cl-gold-border);
  padding: 15px 32px;
  border-radius: 2px;
  min-height: 50px;
  cursor: pointer;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: background 0.18s ease, border-color 0.18s ease;
}
.btn-ghost:hover { background: var(--cl-gold-glow); border-color: var(--cl-gold); }
.btn-ghost:focus-visible { outline: 2px solid var(--cl-gold); outline-offset: 3px; }

/* Nav CTA pulse — 3 seconds on load then stops */
@keyframes cl-pulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(201,168,76,0.5); }
  50%       { box-shadow: 0 0 0 9px rgba(201,168,76,0); }
}
.nav-cta-pulse { animation: cl-pulse 1.4s ease 0.6s 3; }
```

### 7.2 Navigation

```css
#site-nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  background: var(--cl-navy-deep);
  border-bottom: 1px solid var(--cl-gold-border);
  height: 72px;
  transition: box-shadow 0.3s ease;
}
#site-nav.scrolled { box-shadow: var(--cl-shadow-md); }
```

Logo + descriptor left. Links center. CTA right. Collapses at 640px to hamburger. Mobile menu slides down — never modal overlay.

Nav links: Work Sans 600, 11px, 0.18em tracking, ALL CAPS, cream at 80%. Hover: gold, 1px gold bottom border.

Logo descriptor: "St. Louis Caviar Bar" — Work Sans 400, 9px, 0.20em tracking, ALL CAPS, `--cl-gold`, beneath the logo img. Never omit.

### 7.3 Section Headers

Every major section. No exceptions.

```css
.section-header { text-align: center; margin-bottom: 80px; }

.eyebrow {
  font-family: var(--font-body);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.24em;
  text-transform: uppercase;
  color: var(--cl-gold);
  margin-bottom: 14px;
}

.section-header h2 {
  font-family: var(--font-display);
  font-size: clamp(2.4rem, 5vw, 4rem);
  font-weight: 600;
  line-height: 1.1;
  letter-spacing: -0.015em;
  margin-bottom: 24px;
}

.header-rule {
  width: 48px;
  height: 1px;
  background: var(--cl-gold);
  opacity: 0.45;
  margin: 0 auto;
}
```

Dark section H2: `--cl-text-cream`. Light section H2: `--cl-navy`.

### 7.4 Menu Items

```css
.menu-item {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 20px;
  padding: 22px 0;
  border-bottom: 1px solid rgba(249,246,239,0.07);
  position: relative;
  z-index: 1;
}
.menu-item:last-child { border-bottom: none; }
.menu-item-name {
  font-family: var(--font-display);
  font-size: 1.05rem;
  font-weight: 500;
  color: var(--cl-text-cream);
  margin-bottom: 4px;
}
.menu-item-detail {
  font-size: 12px;
  color: var(--cl-text-muted);
  letter-spacing: 0.04em;
}
.menu-item-price {
  font-family: var(--font-body);
  font-size: 15px;
  font-weight: 700;
  color: var(--cl-gold);
  white-space: nowrap;
  font-variant-numeric: tabular-nums;
  flex-shrink: 0;
}
/* Featured item — Grand Tasting only */
.menu-item-featured {
  padding-top: 28px;
  margin-top: 8px;
  border-top: 1px solid var(--cl-gold-border);
}
.menu-item-featured .menu-item-name {
  font-size: 1.15rem;
  font-weight: 600;
  color: var(--cl-gold-light);
}
```

No cards. No background fills. No side borders. Dividers only. One featured item treatment — Grand Tasting — is the single moment of deliberate excess on the menu.

### 7.5 Form Fields

```css
.form-label {
  font-family: var(--font-body);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  color: rgba(201,168,76,0.80);
  margin-bottom: 7px;
  display: block;
}
.form-field {
  font-family: var(--font-body);
  font-size: 14px;
  color: var(--cl-text-cream);
  background: rgba(249,246,239,0.05);
  border: 1px solid var(--cl-gold-border);
  border-radius: 4px;
  padding: 14px 18px;
  width: 100%;
  min-height: 50px;
  outline: none;
  transition: border-color 0.18s, background 0.18s;
  -webkit-appearance: none;
}
.form-field::placeholder { color: rgba(240,235,224,0.20); }
.form-field:focus {
  border-color: rgba(201,168,76,0.55);
  background: rgba(249,246,239,0.09);
}
textarea.form-field { min-height: 130px; resize: vertical; }
```

### 7.6 Photo Placeholders

Atmospheric panels, not wireframes.

```css
.photo-placeholder {
  background: var(--cl-navy-mid);
  border: 1px solid var(--cl-gold-border);
  position: relative;
  overflow: hidden;
}
.photo-placeholder::before {
  content: '';
  position: absolute;
  inset: 18px;
  border: 1px solid rgba(201,168,76,0.09);
  z-index: 1;
}
.photo-placeholder::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image: radial-gradient(
    circle,
    rgba(201,168,76,0.08) 1.5px,
    transparent 1.5px
  );
  background-size: 28px 28px;
  z-index: 0;
}
```

---

## 8. PAGE SECTION ARCHITECTURE

| # | ID | Section | Background | Key Atmospheric Element |
|---|---|---|---|---|
| 0 | `#site-nav` | Sticky Nav | `--cl-navy-deep` | Gold border bottom |
| 1 | `#hero` | Hero | `--cl-navy-deep` | Crest 380px + pearl texture + 4 rings + 1 red ring + sturgeon watermark |
| 2 | `#marquee` | Press Strip | `--cl-navy-mid` | Scrolling quotes |
| 3 | `#about` | About | `--cl-cream` | Mood words at dramatic scale |
| 4 | `#menu` | Menu | `--cl-navy` | Sturgeon watermark lower-right + pearl texture |
| 5 | `#experience` | Experience | `--cl-cream` | Asymmetric image/content split |
| 6 | `#private-events` | Private Events | `--cl-navy-deep` | Form + partial ring upper-right |
| 7 | `#footer` | Footer | `--cl-navy-deep` | Pearl texture + logo 160px |

---

## 9. SECTION SPECIFICATIONS

### Section 1 — Hero

Layer order back to front:
1. `--cl-navy-deep` background
2. Pearl dot texture (full coverage)
3. Sturgeon watermark (700px, opacity 0.05, centered behind logo)
4. Four gold rings + one red ring (all centered on logo)
5. Radial gold glow: `radial-gradient(ellipse 60% 50% at 50% 45%, rgba(201,168,76,0.07) 0%, transparent 65%)`
6. Content (z-index 1+)

Content stack top to bottom:
- Logo `<img class="site-logo-hero">` 380px, centered, `--cl-shadow-gold`
- "St. Louis Caviar Bar" — 9px, 0.22em tracking, ALL CAPS, `--cl-gold`, 12px below logo
- 32px gap
- Eyebrow: flanking 36px gold rules + "St. Louis, Missouri"
- 20px gap
- Headline: "St. Louis' Finest Caviar Experience" — Playfair 700, `clamp(3.6rem, 8vw, 6.5rem)`, cream, max-width 800px
- 20px gap
- Subhead: "Caviar service, champagne, and celebration — Est. 2025" — Work Sans 300, 13px, 0.28em tracking, ALL CAPS, `--cl-text-muted`
- 48px gap
- CTA pair: `.btn-primary` "Reserve a Table" + `.btn-ghost` "View the Menu", 16px gap
- Scroll chevron: absolute bottom 36px, `--cl-gold` 45%, bouncing loop

**Size relationship check.** The 380px crest and `clamp(3.6rem, 8vw, 6.5rem)` headline must feel like they share the same scale world. The 13px subhead is the whisper that makes both feel larger. If the subhead looks close in size to the headline, the hierarchy is broken. Fix it before moving on.

### Section 2 — Press Marquee Strip

Mandatory. The pulse of the room. Must scroll.

```css
.marquee-wrap {
  background: var(--cl-navy-mid);
  border-top: 1px solid var(--cl-gold-border);
  border-bottom: 1px solid var(--cl-gold-border);
  height: 72px;
  overflow: hidden;
  display: flex;
  align-items: center;
}
.marquee-track {
  display: flex;
  align-items: center;
  white-space: nowrap;
  animation: marquee-scroll 44s linear infinite;
}
.marquee-wrap:hover .marquee-track { animation-play-state: paused; }
@keyframes marquee-scroll {
  from { transform: translateX(0); }
  to   { transform: translateX(-50%); }
}
.marquee-item {
  font-family: var(--font-display);
  font-style: italic;
  font-size: 15px;
  color: rgba(240,235,224,0.70);
  padding: 0 48px;
  display: inline-flex;
  align-items: center;
  gap: 48px;
}
.marquee-dot {
  display: inline-block;
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: var(--cl-gold);
  opacity: 0.6;
}
```

Duplicate all items to fill the loop. Placeholder quotes:
"The finest caviar experience in St. Louis." / "An unforgettable evening from start to finish." / "Tableside service, impeccably done." / "The room St. Louis didn't know it needed." / "Pearl by pearl, a perfect night." / "Reserve early. This one fills up."

### Section 3 — About

Background: `--cl-cream`.

Centered pull quote in Playfair italic, `clamp(1.15rem, 2.4vw, 1.5rem)`, `--cl-navy`, max-width 680px, line-height 1.75, margin-bottom 72px. Text: "Caviar Louie is St. Louis' destination for refined caviar service, curated champagne, and the art of celebration. We believe the finest things should be joyfully shared — poured without ceremony, savored with intention."

Three mood blocks in a horizontal row:

```css
.mood-grid {
  display: flex;
  border-top: 1px solid rgba(27,42,107,0.12);
  border-bottom: 1px solid rgba(27,42,107,0.12);
}
.mood-block {
  flex: 1;
  text-align: center;
  padding: 48px 32px;
  border-right: 1px solid rgba(27,42,107,0.10);
}
.mood-block:last-child { border-right: none; }
.mood-word {
  font-family: var(--font-display);
  font-size: clamp(3rem, 6vw, 5rem);
  font-weight: 700;
  line-height: 1.0;
  letter-spacing: -0.02em;
  color: var(--cl-navy);
  margin-bottom: 16px;
}
.mood-rule {
  width: 32px;
  height: 1px;
  background: var(--cl-gold);
  margin: 0 auto 16px;
}
.mood-caption {
  font-family: var(--font-body);
  font-size: 14px;
  color: var(--cl-text-muted-lt);
  line-height: 1.6;
}
```

Content:
- DATE NIGHT. / "The perfect table for two."
- BIRTHDAYS. / "Arrive as a guest. Leave as a story."
- CELEBRATIONS. / "Every occasion deserves a pearl."

No cards. No backgrounds. No icon circles. Just words and conviction.

### Section 4 — Menu

Background: `--cl-navy`. Pearl texture active. Sturgeon at lower-right, opacity 0.04.

Section header eyebrow "The Selection" + H2 "The Menu" in `--cl-gold`.
Two columns, 1px vertical rule `--cl-gold-border` between them on desktop.
Column headers: Work Sans 700, 13px, 0.22em tracking, ALL CAPS, `--cl-gold`.

Caviar Service: Baerii Classic $65 / Ossetra Reserve $85 / Kaluga Hybrid $120 / The Louie Service $185 / Grand Tasting $265 (featured).
Accompaniments: Classic Accoutrements $18 / Champagne by the Glass $24+ / Bottle Service $95+ / Oysters on the Half Shell $28 / Foie Gras Toast $32.

Ghost button "View Full Menu" centered below.

### Section 5 — Experience

Background: `--cl-cream`. 55/45 asymmetric grid.

Left: `.photo-placeholder` aspect-ratio 4/3.
Right: eyebrow + H2 "Intimate by Design. Memorable by Nature." + four points using 24px gold horizontal rule as bullet marker.

Points: Private Table Service / Premium Sourcing / Intimate Atmosphere / Celebration Packages.

### Section 6 — Private Events

Background: `--cl-navy-deep`. Pearl texture. One partial ring-3 off-center upper-right.

Centered max-width 680px. H2 "Host Your Celebration" in cream. Short paragraph in muted cream.

Form: 2-col desktop / 1-col mobile. Name + Email / Phone + Event Date / Party Size (full) / Message (full) / "Send Inquiry" `.btn-primary` centered.

On submit: hide form, show Playfair italic gold message: "Thank you. We'll be in touch shortly."

### Section 7 — Footer

Background: `--cl-navy-deep` + pearl texture at 55%.

Logo 160px centered. "St. Louis Caviar Bar" descriptor below. Three columns: Hours / Location / Social. Gold divider above copyright. Copyright: "© 2025 Caviar Louie. All rights reserved."

---

## 10. ANIMATION SYSTEM

```css
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.65s ease, transform 0.65s ease;
}
.reveal.visible { opacity: 1; transform: translateY(0); }
.reveal-d1 { transition-delay: 0.10s; }
.reveal-d2 { transition-delay: 0.22s; }
.reveal-d3 { transition-delay: 0.34s; }
.reveal-d4 { transition-delay: 0.46s; }
.reveal-d5 { transition-delay: 0.58s; }
```

```javascript
var revealObserver = new IntersectionObserver(function(entries) {
  entries.forEach(function(entry) {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
      revealObserver.unobserve(entry.target);
    }
  });
}, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });

document.querySelectorAll('.reveal').forEach(function(el) {
  revealObserver.observe(el);
});

document.querySelectorAll('#hero .reveal').forEach(function(el, i) {
  setTimeout(function() { el.classList.add('visible'); }, 80 + (i * 130));
});
```

Fade-up only. No slide, no scale, no bounce, no parallax, no physics.
Marquee pauses on mouseenter, resumes on mouseleave.
Durations: hover 0.18s / reveal 0.65s / nav 0.30s / marquee 44s linear.

---

## 11. RESPONSIVE RULES

```css
@media (max-width: 1024px) { }
@media (max-width: 768px)  { }
@media (max-width: 640px)  { }
@media (max-width: 375px)  { }
```

Mobile (640px and below):
- Nav collapses to hamburger. Slides down. Never modal.
- Hero logo: 240px.
- Hero headline: clamp floor 3.6rem. Never reduce below this.
- Hero rings: 55% scale.
- Mood words: `clamp(2.4rem, 8vw, 3.5rem)` — still large.
- Menu: single column.
- Experience: image stacks above content.
- Mood blocks: stack vertically, horizontal gold rules as dividers.
- Form: single column, full width fields.
- Section padding: 72px vertical.
- Content padding: 0 20px.

---

## 12. TECHNICAL REQUIREMENTS

- Single HTML file, embedded CSS and JS
- Google Fonts via `<link>` tag in `<head>`, not `@import`
- Lucide icons: `https://unpkg.com/lucide@0.344.0/dist/umd/lucide.min.js`
- Guard all Lucide calls: `if (typeof lucide !== 'undefined' && lucide.createIcons) lucide.createIcons()`
- All JS in ES5: `var`, `function`. No `const`, `let`, arrow functions
- Wrap all JS in `document.addEventListener('DOMContentLoaded', function() { ... })`
- Form: static, `preventDefault()`, hide form, show success message
- `scroll-behavior: smooth` on `html`
- Logo: `<img src="logo.png" class="site-logo" alt="Caviar Louie">`
- Output file: `caviar-louie.html`

---

## 13. NEVER ALLOWED

Read before writing any code. If about to do any of the following, stop.

- Gradient fills on buttons
- `#ffffff` as any background
- Solid gray borders
- Black in any shadow
- Colored circles or rounded squares around icons
- Emoji of any kind
- Colored side borders on list or menu items
- Border-radius above 6px
- Inter, Roboto, Arial, or system-ui as a display typeface
- Playfair Display in nav, buttons, labels, or eyebrows
- Work Sans in any headline or display role
- Red used more than once per page
- Parallax scrolling
- External JS beyond Lucide
- Modal overlay for mobile nav
- Menu cards with drop shadows
- Pill-shaped buttons
- Uppercase body text paragraphs
- Hero headline below 3.6rem — the floor is the floor
- Section H2 below 2.4rem — they are structural, not labels
- "Safe" conservative type sizes — the dramatic contrast is the design
- The word "experience" in any copy — use specific sensory language

---

## 14. PROMPT TEMPLATE FOR CLAUDE CODE

```
Read CAVIAR-LOUIE-DESIGN.md completely before writing any code.
Do not begin coding until you have read every section.

Logo file: logo.png in project root.

Build caviar-louie.html as a single HTML file with embedded CSS and JS.

Requirements:
- Colors: tokens from Section 1 only. No other values.
- Typography: fonts and sizes from Section 2 only. Hero headline min 3.6rem. Section H2 min 2.4rem.
- Pearl texture: Section 4 — every dark section.
- Sturgeon watermark: Section 5 — hero and menu sections.
- Rings: Section 6 — hero only.
- Components: exact CSS from Section 7.
- Sections: all 8 in the order from Section 8.
- Animations: Intersection Observer per Section 10.
- Responsive: all rules from Section 11.
- JS: ES5 only, wrapped in DOMContentLoaded.

Do not introduce any design element not defined in this file.
Do not scale down the hero headline or section H2s below spec minimums.
Do not make type sizes safe — the dramatic size contrast is intentional and required.

When complete, the site must feel like a room, not a menu.
Handcrafted, specific, and unmistakably Caviar Louie.
```

---

*Last updated: May 2026. Maintained by Bespoke MKTG for Caviar Louie, St. Louis MO.*
