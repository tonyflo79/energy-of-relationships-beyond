# DESIGN BRIEF — Energy of Relationships Sales Page

**Product:** Energy of Relationships — Relationship Sensor Activation System
**Client:** Dr. Barry Morguelan / Energy for Success
**Price:** $197 (one-time)
**Guarantee:** 30-Day Money-Back
**Date:** 2026-02-26
**Version:** 1.0

---

## Table of Contents

1. [Overview](#1-overview)
2. [Global Design System](#2-global-design-system)
3. [Typography System](#3-typography-system)
4. [Spacing & Layout](#4-spacing--layout)
5. [Shadow & Radius Tokens](#5-shadow--radius-tokens)
6. [Section Map](#6-section-map)
7. [Section-by-Section Spec](#7-section-by-section-spec)
8. [Headlines](#8-headlines)
9. [Copy Mapping (VSL → Page)](#9-copy-mapping-vsl--page)
10. [Key Differences from Soulmates](#10-key-differences-from-soulmates)
11. [Two Versions](#11-two-versions)
12. [Responsive Breakpoints](#12-responsive-breakpoints)
13. [Accessibility](#13-accessibility)
14. [JavaScript Behaviors](#14-javascript-behaviors)
15. [Performance Targets](#15-performance-targets)
16. [File Structure](#16-file-structure)
17. [Deployment](#17-deployment)
18. [Verification Checklist](#18-verification-checklist)

---

## 1. Overview

Build two versions of a sales page for Dr. Barry Morguelan's "Energy of Relationships" course:

- **Version A (index.html):** Copy-only sales page (no video)
- **Version B (index-vsl.html):** Identical page with VSL video embed in hero section

Both use the **Energy of Soulmates** site as the structural template — same Foundr-inspired layout patterns, section types, responsive behavior, and build approach (single HTML file with embedded CSS/JS).

### Core Mechanism
**Relationship Sensors** — physical sensor systems in hands, heart, gut, and spine that evolved to read other people's energy. When shut down (from stress, past relationships, overriding instincts), you can't distinguish builders from drainers.

### Core Framework
**Four Categories** — Category 1 (Builders/Win-Win-Win), Category 2 (Conditional), Category 3 (Takers/Win-Lose), Category 4 (Destroyers/Lose-Lose). You attract what you ARE, not what you want.

### Core Promise
Reactivate your body's relationship sensor system so you stop attracting the wrong people and start building connections that last.

---

## 2. Global Design System

### Purple/Violet Energy Palette

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-primary` | `#7C3AED` | Primary CTA buttons, accent headlines — deep violet |
| `--color-primary-dark` | `#5B21B6` | Hover states, deep sections |
| `--color-primary-light` | `#A78BFA` | Secondary accent, badges, gradient end |
| `--color-glow` | `#C4B5FD` | Soft accent, replaces rose/pink from Soulmates |
| `--color-mist` | `#F5F3FF` | Light section backgrounds (replaces blush) |
| `--color-cream` | `#FAFAFE` | Alternate section background |
| `--color-lavender` | `#EDE9FE` | Bonus icon bg, light decoration (replaces petal) |
| `--color-dark` | `#1E1B2E` | Primary headline text — warm dark indigo |
| `--color-body` | `#4A4558` | Body text — warm gray with violet undertone |
| `--color-muted` | `#8B839A` | Subtitle labels, secondary text |
| `--color-white` | `#FFFFFF` | Card backgrounds, text on dark |
| `--color-border` | `#DDD6FE` | Subtle borders, separators |
| `--color-gold` | `#D4A853` | Premium accents — guarantee badge, star ratings |
| `--color-dark-section` | `#2D2145` | Pricing card header, dark testimonial areas |

### Gradients

| Token | Value | Usage |
|-------|-------|-------|
| `--gradient-primary` | `linear-gradient(135deg, #7C3AED 0%, #A78BFA 100%)` | Button gradient, accent bars |
| `--gradient-hero` | `linear-gradient(180deg, #F5F3FF 0%, #FFFFFF 100%)` | Hero section background |
| `--gradient-dark` | `linear-gradient(135deg, #2D2145 0%, #1E1B2E 100%)` | Dark sections (results, pricing header) |

### Shadows (recolored from Soulmates red → violet)

| Token | Value |
|-------|-------|
| `--shadow-sm` | `0 2px 8px rgba(124,58,237,0.06)` |
| `--shadow-md` | `0 8px 24px rgba(124,58,237,0.08)` |
| `--shadow-lg` | `0 16px 48px rgba(124,58,237,0.10)` |
| `--shadow-xl` | `0 24px 64px rgba(124,58,237,0.12)` |
| `--shadow-button` | `0 4px 16px rgba(124,58,237,0.25)` |
| `--shadow-button-hover` | `0 8px 32px rgba(124,58,237,0.40)` |

---

## 3. Typography System

Same 4-font system as Soulmates (proven, consistent across Dr. Barry products):

| Role | Font | Weights | Usage |
|------|------|---------|-------|
| Display | Playfair Display | 700, 800, 900, italic | H1, H2, section headings, stat numbers |
| Sans | Inter | 400, 500, 600, 700 | Labels, buttons, nav, meta text |
| Body | Source Serif 4 | 400, 600, italic | Body copy, descriptions |
| Script | Pinyon Script | 400 | Accent word "Energy" in sub-headlines |

### Type Scale

| Element | Size | Weight | Font |
|---------|------|--------|------|
| H1 (hero) | 62px → 28px | 900 | Playfair Display |
| Hero sub | 38px → 20px | 900 italic | Playfair Display |
| Section heading | 40px → 30px | 800 | Playfair Display |
| Body | 20px → 18px | 400 | Source Serif 4 |
| Section label | 13px | 600 | Inter |
| Button | 18px → 16px | 700 | Inter |
| Stat number | 44-120px | 900 | Playfair Display |

---

## 4. Spacing & Layout

Same 8px grid system as Soulmates:

| Container | Max Width |
|-----------|-----------|
| `.container` | 1080px |
| `.container-wide` | 1280px |
| `.container-narrow` | 800px |
| `.container-text` | 680px |

All containers: `padding: 0 24px; margin: 0 auto;`

### Section Padding

| Section Type | Padding |
|--------------|---------|
| Standard section | `100px 0` |
| Hero | `140px 0 80px` (accounts for sticky timer) |
| CTA Banner | `80px 0` |
| Components | `120px 0` |
| Results (dark) | `120px 0` |
| Future pacing | `120px 0` |

---

## 5. Shadow & Radius Tokens

| Token | Value |
|-------|-------|
| `--radius-sm` | `8px` |
| `--radius-md` | `12px` |
| `--radius-lg` | `16px` |
| `--radius-xl` | `24px` |
| `--radius-pill` | `100px` |

---

## 6. Section Map

21 sections mirroring the Soulmates structure:

| # | Section | Background | Key Element |
|---|---------|------------|-------------|
| 0 | Sticky Timer Bar | White | Energy pulse icon (sun/rays), "Special Offer" |
| 1 | Hero | gradient-hero | "Why Your Body Keeps Choosing..." headline |
| 2 | Social Proof Bar | White | Tony Robbins, Jay Abraham, HeartMath, Fortune 500, Billionaires |
| 3 | Problem — Toxic Patterns | White | 73% stat callout, "same wrong person in different body" quote |
| 4 | Bridge — "It's an Energy Problem" | Mist | Reframe from communication → energy |
| 5 | Mechanism — Relationship Sensors | White | Two-column: image + 4 sensor locations |
| 6 | Why Nothing Worked | Mist | 5 failed solutions: therapy, communication, self-help, dating, willpower |
| 7 | Science/Credibility — "40 Years" | White | HeartMath + neurogastroenterology research cards |
| 8 | Dr. Barry Bio | White | Same bio card structure as Soulmates |
| 9 | System — Four Categories | White | 4 Category cards grid + "attract what you ARE" reveal |
| 10 | CTA Banner #1 | Mist (skewed) | Mid-page conversion |
| 11 | Results & Social Proof | gradient-dark | 3 story cards + stats |
| 12 | What You Get — 4 Modules | White | Tab interface, 4 tabs |
| 13 | Bonuses | White (mist blob behind) | Workbook + Assessment Toolkit |
| 14 | Pricing | Mist | $197, value stack totaling $592 |
| 15 | Guarantee | White | 30-Day badge (gold border) |
| 16 | CTA Banner #2 | Mist (skewed) | Post-guarantee conversion |
| 17 | Urgency — Cost of Inaction | White | "Every day sensors stay off..." + dark callout |
| 18 | Future Pacing & Close | Subtle violet gradient | "Start Module 1 tonight..." |
| 19 | FAQ | White | 9 questions, desktop two-column, mobile accordion |
| 20 | Final CTA | Mist (skewed) | "Your Energy Is Ready to Shift" |
| 21 | Footer | Dark | EFS logo, disclaimer, references |

---

## 7. Section-by-Section Spec

### Section 0: Sticky Timer Bar
- Fixed top, z-index 9999
- Energy pulse icon (sun/rays SVG) replaces heart icon from Soulmates
- Label: "Special Offer — Enrollment Closes In:"
- 4 digit boxes (Days, Hrs, Min, Sec) with mist background
- "Enroll Now →" CTA button
- Timer: 7-day evergreen (localStorage persisted)

### Section 1: Hero
- Background: gradient-hero (mist → white)
- Two decorative floating circles (glow + lavender, 4-6% opacity)
- Badge: "New Program — Limited Enrollment" with pulsing dot
- **Version A headline:** "Why Your Body Keeps Choosing the Relationships Your Mind Knows Are Wrong"
- **Version B headline:** "Watch This Short Video to Discover Why Every Relationship Problem Comes Down to Energy"
- Sub-headline with "Energy" in Pinyon Script
- Body paragraph: Dr. Barry intro + Tony Robbins/Jay Abraham + 4-module system
- **Version A:** Hero image (Unsplash, energy/connection)
- **Version B:** Vimeo embed (16:9, dark background placeholder)
- CTA: "Activate My Relationship Sensors →"
- Trust row: Secure Checkout, One-Time Payment, 30-Day Guarantee

### Section 2: Social Proof Bar
- Text logos (no images): Tony Robbins, Jay Abraham, HeartMath Institute, Fortune 500 CEOs, Billionaire Clients
- Label: "Trusted by World-Class Performers & Leaders"

### Section 3: Problem Section
- Stat callout: "73% of adults repeatedly attracted the same wrong person"
- Body copy: 4 "if you..." pain points
- Pull quote: "I Kept Choosing the Same Wrong Person in a Different Body..."
- Emphasis: "Nothing is wrong with you." + sensor shutdown explanation

### Section 4: Bridge
- Skewed mist background
- Heading: "It's Not a Communication Problem. It's an Energy Problem."
- Body: 40+ year career, smart people with terrible radar
- Reveal line: "Your relationship sensors are shut down."

### Section 5: Mechanism Reveal
- Two-column grid: image (left) + copy (right)
- Image with gradient offset border + "4 Sensor Locations" overlay badge
- Copy: 4 sensor locations (Hands, Heart, Gut, Spine) with descriptions
- Callout box: "When these sensors are active, you KNOW."

### Section 6: Why Nothing Worked
- 2x2 grid + 1 spanning bottom (5 cards total)
- Cards: Therapy, Communication Training, Self-Help Books, Dating Advice, Willpower
- Each: image, title, explanation of why it fails
- Revelation text: "Your body's relationship sensor system."

### Section 7: Science Credibility
- Heading: "40+ Years of Research and Real-World Results"
- Tony Robbins + Jay Abraham name-drops
- 2 research cards: HeartMath (heart 100x) + neurogastroenterology (100M gut neurons)
- Million box (dark gradient): "4 Sensors" + explanation

### Section 8: Dr. Barry Bio
- Same card structure as Soulmates
- Left: Dr. Barry photo (energyforsuccess.com asset)
- Right: Credentials, name (56px), bio copy
- Bottom banner (gradient-primary): 40+ Years, 1000s Clients, 4 Sensor Systems, 12 Grand Masters

### Section 9: Four Categories
- Section label: "The Framework"
- 4 category cards in 2x2 grid
- Category 1 (Builders) highlighted with primary border + mist bg
- Revelation: "You attract what you ARE, not what you want."

### Section 10: CTA Banner #1
- "Ready to Reactivate?" + "Start Your Sensor Activation Today"

### Section 11: Results & Social Proof
- Dark gradient background, white text
- 3 story cards (Entrepreneur, Executive, Parent)
- 2 research result boxes: 40+ Years, 1000s Clients

### Section 12: Modules (4 tabs)
- Tab interface with 4 module tabs
- Module 1: Sensor Mapping & Category Classification
- Module 2: Sensor Reactivation Protocol
- Module 3: Reading People & Protecting Your Energy
- Module 4: Building & Sustaining Category 1 Relationships
- Each: jumbotron (SVG icon + title + description) + bullet grid
- Bullet icon: ✦ (diamond four-point star) in primary color

### Section 13: Bonuses
- 2 bonus cards: Workbook ($49 value) + Sensor Assessment Toolkit ($49 value)
- FREE badge (gradient primary circle)

### Section 14: Pricing
- Value stack: 4-Module Program ($397) + RTVTs ($97) + Workbook ($49) + Toolkit ($49) = $592
- Pricing card: dark header ($197), feature list, CTA
- Comparison: couples therapy $2,400-3,600 vs. $197

### Section 15: Guarantee
- 30-Day badge (gold border, gold text)
- Copy: 30 days, do the practices, full refund if no activation signs
- Risk reversal box

### Section 16: CTA Banner #2
- "Your Sensors Are Ready to Come Back Online"

### Section 17: Urgency
- "Every Day Your Sensors Stay Off..."
- Dark callout: "sensors are off... can't feel what you can't detect"
- Cost reframe: "Another year of navigating blind"

### Section 18: Future Pacing
- Subtle violet gradient background
- "What Happens When the Energy Shifts..."
- Progressive narrative: tonight → first week → days → weeks
- Lock-on line: "Your sensors activate. Your Category shifts. Everything changes."

### Section 19: FAQ
- 9 questions
- Desktop: two-column (question left, answer right) with numbered counters
- Mobile: accordion with toggle arrows

### Section 20: Final CTA
- "Your Energy Is Ready to Shift" with "Energy" in Pinyon Script
- Enrollment badge with energy pulse icon

### Section 21: Footer
- EFS logo, disclaimer, references (HeartMath, neurogastroenterology), footer links

---

## 8. Headlines

### Primary Headline (Version A — no video)
> "Why Your Body Keeps Choosing the Relationships Your Mind Knows Are Wrong"

### Sub-headline
> The discovery of "Energy" sensors in your hands, heart, gut, and spine explains the pattern.

### VSL Headline (Version B)
> "Watch This Short Video to Discover Why Every Relationship Problem Comes Down to Energy"

### Alternative Headlines (for testing)
1. "Warning: You May Be Doing to Yourself Exactly What Your Worst Relationship Did to You"
2. "The Four Kinds of People — and the One Kind That Ruins Every Relationship Without Knowing It"
3. "You Can't Communicate Your Way Out of a Bad Relationship. Here's the Biological Reason Why."

---

## 9. Copy Mapping (VSL → Page)

| VSL Timestamp | Page Section(s) |
|---------------|-----------------|
| Opening [0:00-0:45] | Hero section copy |
| Problem Agitation [0:45-2:30] | Problem section + Bridge |
| Unique Mechanism [2:30-4:30] | Mechanism Reveal + Four Categories |
| Proof & Credibility [4:30-6:00] | Results section + Bio |
| The Offer [6:00-7:30] | What You Get + Bonuses + Pricing |
| Close [7:30-8:30] | Urgency + Future Pacing + Final CTA |

---

## 10. Key Differences from Soulmates

| Element | Soulmates | Relationships |
|---------|-----------|---------------|
| Color palette | Red/crimson/pink (Valentine's) | Purple/violet (energy/spiritual) |
| Guarantee | 90-Day | 30-Day |
| Price | $197 | $197 |
| Modules | 8 modules | 4 modules |
| Core mechanism | Heart electromagnetic field / Heart Magnet | Relationship sensors / Four Categories |
| Timer tie-in | Valentine's Day (fixed date) | Generic enrollment deadline (evergreen 7-day) |
| Timer icon | Heart pulse | Energy/sun pulse |
| Hero visual | Couple imagery | Individual → energy connection |
| Script accent word | "Soulmate" | "Energy" |
| Social proof stat | "0 Divorces" hero number | Story-based (3 cards) |
| Dark section content | 0 (divorces) ring + research stats | Story cards + practice stats |
| CTA text | "Start My Soulmate Activation" | "Activate My Relationship Sensors" |
| Bullet icon | ❤ (heart) | ✦ (diamond star) |
| Bio stats | 40+ Years, 100s Couples, 0 Divorces, 12 Masters | 40+ Years, 1000s Clients, 4 Sensors, 12 Masters |
| Divider icon | Heart | Energy (sun/star) |
| Badge | "Valentine's Day Enrollment" | "Limited Enrollment" |
| Section 9 | 5 Components (alternating rows) | 4 Category cards (2x2 grid) |
| Value stack total | $495 | $592 |
| Daily cost reframe | $2.19/day for 90 days | $6.57/day for 30 days |
| Comparison | Dating apps $100+/mo | Couples therapy $2,400-3,600 |

---

## 11. Two Versions

### Version A: `index.html` (No Video)
- Full copy-first page
- Hero: headline + body description + hero image + CTA
- Designed for cold traffic, SEO, direct link sharing

### Version B: `index-vsl.html` (With VSL)
- Identical to Version A EXCEPT:
  - Title tag updated: "Watch This Short Video"
  - Hero headline changed to VSL-specific
  - Hero image replaced with Vimeo embed (16:9)
  - Description paragraph moved below video
- Video embed uses placeholder `[VSL_VIDEO_ID]` — replace with actual Vimeo ID
- Designed for warm traffic, ad landing pages, email traffic

---

## 12. Responsive Breakpoints

5 breakpoints matching Soulmates spec:

| Breakpoint | Target |
|------------|--------|
| > 1024px | Desktop (full layout) |
| 769-1024px | Tablet landscape (reduced font sizes) |
| 481-768px | Tablet portrait / large mobile (single-column grids) |
| 321-480px | Mobile (aggressive font reduction) |
| < 320px | Small mobile (handled by fluid scaling) |

### Key Responsive Behaviors
- All 2-column grids collapse to single column at 768px
- FAQ switches from side-by-side to accordion at 768px
- Module tabs become horizontally scrollable at 768px
- Hero h1: 62px → 48px → 34px → 28px
- Bio grid: 2-column → single column at 768px
- Stats row: horizontal → vertical at 480px
- Timer: wraps to multi-line at 768px with reduced sizing
- Category cards grid: 2x2 → single column at 768px

---

## 13. Accessibility

- **Semantic HTML5:** proper heading hierarchy (h1 > h2 > h3)
- **ARIA attributes:** role="tablist", role="tab", role="tabpanel", aria-selected
- **Focus styles:** browser default maintained
- **Alt text:** descriptive on all images
- **Color contrast:** all text meets WCAG AA (body #4A4558 on #FFFFFF = 7.2:1)
- **`prefers-reduced-motion`:** disables all animations and transitions
- **No autoplay video:** VSL version requires user click to play
- **Keyboard navigable:** tabs, links, buttons all keyboard accessible

---

## 14. JavaScript Behaviors

### Countdown Timer
- Evergreen 7-day timer persisted in localStorage
- Key: `eor_timer_target`
- Falls to 00:00:00:00 when expired (no redirect)
- Updates every 1 second

### Module Tabs
- Click handler on `.module-tab` buttons
- Shows corresponding `.module-panel`
- Manages `active` class and `aria-selected`

### Smooth Scroll
- All `a[href^="#"]` links smooth-scroll with 70px offset (timer height)

### FAQ Accordion (Mobile Only)
- CSS-driven: `max-height: 0` → `max-height: 600px` on `.open`
- `.faq-toggle` arrow rotates 180deg
- Toggle triggered by onclick on `.faq-question`
- Desktop: always visible (no accordion)

---

## 15. Performance Targets

| Metric | Target |
|--------|--------|
| Total page weight | < 500KB (no frameworks) |
| External dependencies | Google Fonts only |
| JavaScript | < 2KB (vanilla, inline) |
| Images | External (Unsplash/Pexels CDN + EFS CDN) |
| First contentful paint | < 1.5s |
| Cumulative layout shift | < 0.1 |

---

## 16. File Structure

```
energy-of-relationships/
├── website/
│   ├── index.html          # Version A — No video
│   └── index-vsl.html      # Version B — With VSL video embed
└── DESIGN-BRIEF-RELATIONSHIPS-SALES-PAGE.md   # This file
```

---

## 17. Deployment

1. Add to existing GitHub repo or create new repo
2. Enable GitHub Pages (main branch, /website root)
3. Preview links:
   - Version A: `https://[username].github.io/energy-of-relationships/website/`
   - Version B: `https://[username].github.io/energy-of-relationships/website/index-vsl.html`

---

## 18. Verification Checklist

- [ ] Both pages render identically except for video presence
- [ ] All 21 sections present and styled
- [ ] Responsive across all 5 breakpoints
- [ ] Countdown timer functional (evergreen, localStorage persisted)
- [ ] Tab navigation for modules works (4 tabs)
- [ ] FAQ accordion works on mobile
- [ ] All CTA buttons link to `[CHECKOUT_URL]` placeholder
- [ ] Purple/violet palette consistently applied (NO red bleed from Soulmates)
- [ ] Accessibility: focus styles, alt text, aria attributes
- [ ] Page weight < 500KB (no framework dependencies)
- [ ] 30-Day guarantee (not 90-day)
- [ ] 4 modules (not 8)
- [ ] Script accent word is "Energy" (not "Soulmate")
- [ ] Timer icon is energy/sun (not heart)
- [ ] Bullet icons are ✦ (not ❤)
- [ ] Bio stats show 4 Sensor Systems (not 0 Divorces)
- [ ] Price is $197 with $592 value stack
- [ ] VSL version has `[VSL_VIDEO_ID]` placeholder
- [ ] Footer references include neurogastroenterology sources
- [ ] Google Fonts loads all 4 font families

---

*Design brief created 2026-02-26. Based on Energy of Soulmates template (Foundr-inspired, single-file HTML).*
