# CLAUDE.md — Frontend Website Rules

## ⚡ Always Do First
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.
- **Run the Pre-Build Design Brief** (see section below) before writing a single line of HTML. No exceptions.

---

## 🎯 Pre-Build Design Brief — Ask Every Time

Before starting any website, ask the user these questions. Present them clearly, wait for answers, then use the responses to drive every design decision. Do not skip this step. Do not assume defaults. The answers shape layout, hero style, color, typography, and section structure.

### BLOCK 1 — Purpose & Audience
1. **What is this website for?** (portfolio, product launch, service, event, editorial, e-commerce, landing page, other)
2. **Who is the primary audience?** (age range, mindset, sophistication — e.g. "creative professionals 25–40", "parents of young kids", "enterprise CTOs")
3. **What is the ONE action you want visitors to take?** (book a call, buy, sign up, read, explore, contact)

### BLOCK 2 — Emotion & Tone
4. **Pick 2–3 words that describe how this site should FEEL.** Examples: bold / quiet / playful / urgent / luxurious / raw / clinical / warm / rebellious / serene / authoritative / surprising
5. **What should visitors think within the first 3 seconds?** (e.g. "this is premium", "these people get me", "I need this now", "this is different")
6. **Any brands, sites, or things (not websites) that share the right vibe?** (films, magazines, cars, spaces — anything goes)

### BLOCK 3 — Layout Direction
7. **Pick a layout personality:**
   - **Editorial** — magazine-style, big type, asymmetric columns, images break the grid
   - **Spatial** — lots of white space, minimal, one idea per screen
   - **Dense** — rich with content, layered, lots of visual texture
   - **Kinetic** — movement-first, scroll-driven reveals, animation is the experience
   - **Brutalist** — raw, typographic, intentionally unconventional
   - **Hybrid** — mix two of the above (specify which)

8. **Hero style — pick one:**
   - **Typographic dominance** — oversized headline owns the screen, minimal imagery
   - **Split screen** — two distinct zones in tension (text vs. image, dark vs. light)
   - **Immersive background** — full-bleed video, gradient, or texture behind everything
   - **Asymmetric editorial** — text and image collide off-axis, intentional imbalance
   - **Kinetic / scroll-triggered** — hero animates in on load or reacts to cursor/scroll
   - **Deconstructed** — broken grid, overlapping layers, floating elements
   - **Statement + negative space** — one powerful line, lots of silence around it

9. **What should NOT be on this site?** (e.g. "no stock photos", "no dark mode", "no carousels", "nothing that looks like Squarespace")

### BLOCK 4 — Aesthetic Constraints
10. **Color instinct** — pick one direction:
    - Monochromatic with one strong accent
    - Two-tone high contrast (e.g. black + one bold color)
    - Muted/earthy palette
    - Vivid / saturated
    - Dark/moody
    - Light/airy
    - Let me (Claude) decide based on the emotion words above

11. **Typography instinct** — pick one:
    - Serif-forward (editorial, literary, premium)
    - Sans-serif only (clean, modern, systematic)
    - Display/expressive pairing (big personality headline + clean body)
    - Monospace or technical (code-adjacent, brutalist)
    - Let me (Claude) decide

Use these answers as a design brief. Reference them throughout. If a layout choice would contradict the stated emotion or hero style — change it.

---

## 🦸 Hero Section — Non-Negotiable Standards

The hero is not a banner. It is the argument for why someone should stay.

### Hero Inspiration Sources
Study these before designing any hero:
- **Awwwards SOTD heroes** → https://www.awwwards.com/websites/ — benchmark for layout ambition
- **Siteinspire** → https://siteinspire.com — restraint, spatial intelligence, typographic confidence
- **Godly** → https://godly.website — scroll-driven and kinetic hero references
- **Lapa Ninja** → https://www.lapa.ninja — startup/product hero clarity
- **Minimal Gallery** → https://minimal.gallery — negative space mastery

### Hero Principles
- The hero must have a **clear visual hierarchy**: something must dominate — type, image, or motion. Never three things fighting equally.
- **Oversized typography is always on the table.** `clamp(4rem, 10vw, 9rem)` as a starting point for display headings. Large enough that it feels intentional, not accidental.
- **No centered h1 + subtitle + button as the default.** That layout must be earned. Default to something more considered.
- Every hero must pass the **3-second test**: cover everything except the hero — someone should know the site's purpose, personality, and invitation immediately.
- Hero backgrounds: choose one intentional treatment — layered radial gradients with SVG grain, a full-bleed image with `mix-blend-mode` overlay, a geometric CSS-drawn environment, a looping subtle animation, or pure typographic texture. Never a flat solid color with no thought.
- Scroll cue: include a subtle scroll indicator or visual invitation downward (animated chevron, masked text reveal, parallax offset) unless the hero is explicitly full-screen and self-contained.
- **On load animation is standard for heroes.** Staggered fade+translate for headline words, delayed for subtext, further delayed for CTA. Use Intersection Observer or GSAP. Never a static dump.

### Hero Layout Options — Pick One Per Project (Rotate, Never Repeat the Default)
| Style | When to Use |
|---|---|
| **Full-bleed split** — image left, type right (or reversed), hard edge between | Strong brand photography, portfolio, product |
| **Typographic takeover** — headline fills 60–80% of viewport height, body text minimal | Agencies, bold brands, editorial |
| **Layered depth** — multiple z-plane elements, text in front of image in front of background | Luxury, immersive experiences |
| **Scrolljack intro** — hero locks while content reveals sequentially | Storytelling, product launch, narrative |
| **Floating asymmetric** — headline and visual overlap off-axis, neither centered | Creative studios, unconventional brands |
| **Video environment** — subtle looping video texture behind type | Hospitality, events, experiential brands |
| **Deconstructed grid** — text fragments, overflowing images, intentional tension | Avant-garde, art, culture |
| **Statement + silence** — one short powerful line, 80% white/dark space | Minimalist luxury, consulting, personal brand |

---

## 🚫 Anti-Generic Layout System

The 3×2 card grid is over. So is the centered hero + alternating text-image rows + 3-column icon grid. These are defaults, not designs.

### Banned Default Layouts
- ❌ 3-column equal card grid for features/services
- ❌ Alternating text-left / image-right rows with no spatial variation
- ❌ Icon + title + 2-line description repeated 6 times
- ❌ Full-width CTA banner (white text, colored background, centered button)
- ❌ Footer with 4 equal columns of links
- ❌ Testimonials as a carousel of identical quote cards

### Approved Alternatives
- ✅ **Asymmetric bento** — variable-span CSS Grid tiles. Large anchor tile (2×2 or 3×2) + smaller satellites. Reference: bentogrids.com
- ✅ **Editorial horizontal scroll section** — content that slides laterally, breaking vertical expectation
- ✅ **Stacked scroll narrative** — each feature/service gets its own full-width moment with scroll-triggered reveal
- ✅ **Text-image overlap** — type and visual share the same space, z-layered, not side by side
- ✅ **Numbered editorial list** — 01, 02, 03... with large type, ruled lines, and expanding detail on hover
- ✅ **Marquee/ticker section** — scrolling text band for social proof, clients, or key values
- ✅ **Masonry with intentional sizing** — varying heights, editorial rhythm, not uniform rows
- ✅ **Diagonal or angled section breaks** — `clip-path: polygon()` dividers instead of straight horizontal rules
- ✅ **Sticky sidebar narrative** — left column stays fixed while right column scrolls through content
- ✅ **Full-screen section per feature** — each point gets a full viewport moment (no cramming)

### Layout Vocabulary (Use Actively)
- `grid-template-areas` with named zones — never anonymous column spans
- `subgrid` to align nested elements across parent tracks
- `aspect-ratio` to lock proportions, not fixed heights
- `clip-path` for non-rectangular section shapes
- `position: sticky` within grid areas for parallax-adjacent effects
- `min()`, `max()`, `clamp()` for all sizing — no hardcoded px dimensions

---

## Animation Stack
Animations should enhance the experience — not break it. **Default to less.** Only layer in complexity once the base page is stable and screenshotted.

### Tier 1 — Always Safe (use freely)
- **CSS transitions** on `transform` and `opacity` only — for hovers, focus states, and simple reveals.
- **CSS `@keyframes`** — for looping effects (shimmer, pulse, float). Self-contained, no JS dependency.
- **Intersection Observer (vanilla JS)** — trigger class-based entrance animations on scroll. Simple, no library needed. Add a class like `.is-visible` and let CSS handle the transition.

### Tier 2 — Use When Needed (introduce one at a time)
- **GSAP core** (via CDN) — for timeline-based sequences and staggering. Only add ScrollTrigger once core animations are confirmed working.
- **GSAP ScrollTrigger** — scroll-driven pinning, scrub, and section reveals. Add after Tier 1 is stable.
- **Motion One** (via CDN) — lightweight micro-interactions. Use instead of GSAP when only simple element animations are needed.

### Tier 3 — Only When Explicitly Requested
- **Lenis smooth scroll** — only add if the user asks for smooth scroll inertia. Can conflict with ScrollTrigger if misconfigured.
- **Splitting.js** — character/word splitting for text reveals. Only when kinetic typography is a stated goal.
- **Native CSS scroll-driven animations** (`animation-timeline: scroll()`) — powerful but limited browser support. Only use if modern-only browsers are confirmed.

### Animation Principles
- **Build stable first, animate second.** Never add animations before layout and content are confirmed working.
- Animate only `transform` and `opacity`. Never layout properties.
- Never use `transition-all`.
- Use spring-style easing: `cubic-bezier(0.16, 1, 0.3, 1)` or GSAP's `power3.out`.
- Stagger sibling elements — never animate them in unison.
- Always wrap GSAP ScrollTrigger init in `window.addEventListener('load', ...)` to avoid timing issues.
- Use `will-change: transform` sparingly and only on actively animating elements.
- If an animation causes layout shift or jank, remove it — a still page beats a broken one.

---

## Layout & CSS Stack
Modern layout should feel intentional and spatial — not a stack of divs with margin-top.

- **CSS Grid with named areas and subgrid** — for editorial, asymmetric, and magazine-style layouts.
- **CSS `clamp()` for fluid typography and spacing** — no breakpoint jumps. Everything scales continuously.
- **Container queries** (`@container`) — component-level responsiveness.
- **Logical properties** (`margin-inline`, `padding-block`) — future-proof spacing.
- **`oklch()` color space** — perceptually uniform color derivation.
- **`color-mix()`** — blend colors natively.
- **CSS custom properties with `@property`** — typed, animatable variables.
- **CSS nesting** — component styles without a preprocessor.
- **`@layer`** — explicit cascade control.
- **`backdrop-filter`** — frosted glass surfaces.
- **SVG `feTurbulence` noise filter** — grain and texture directly in CSS/SVG.
- **`mix-blend-mode`** — color treatment layers over images.
- **View Transitions API** — page-level morphing transitions.

---

## Visual Depth System
Every design must have a layering system. Surfaces should not all sit at the same z-plane.

- **Base layer:** main background, flat or subtle gradient
- **Elevated layer:** cards, panels — slight background lift + shadow
- **Floating layer:** modals, tooltips, sticky nav — strong shadow, blur backdrop
- **Shadows:** never `box-shadow: 0 4px 6px rgba(0,0,0,0.1)`. Use layered shadows with color tinting:
```css
box-shadow:
  0 1px 2px oklch(30% 0.2 250 / 0.08),
  0 4px 12px oklch(30% 0.2 250 / 0.12),
  0 16px 40px oklch(30% 0.2 250 / 0.08);
```

---

## Typography Stack
- Pair a **display/serif** (e.g. Playfair Display, Fraunces, Instrument Serif) with a **clean sans** (e.g. Inter, DM Sans, Geist).
- Use **variable fonts** where available — animate `font-weight` and `font-variation-settings`.
- Large headings: `letter-spacing: -0.03em`, `line-height: 1.05`
- Body: `line-height: 1.7`, `max-width: 65ch`
- Fluid scale: always use `clamp()`, never fixed px at breakpoints.
- Load from Google Fonts CDN or Bunny Fonts.

---

## Reference Images
- If a reference image is provided: **do not copy it literally.** Absorb the spatial logic and visual hierarchy, then express it originally.
- Screenshot your output, compare against reference, fix mismatches, re-screenshot. At least 2 comparison rounds.

---

## Local Server
- **Always serve on localhost** — never screenshot a `file:///` URL.
- Start the dev server: `node serve.mjs` (serves the project root at `http://localhost:3000`)
- `serve.mjs` lives in the project root. Start it in the background before any screenshots.

## Screenshot Workflow
- Puppeteer is installed at `C:/Users/nateh/AppData/Local/Temp/puppeteer-test/`.
- **Always screenshot from localhost:** `node screenshot.mjs http://localhost:3000`
- Screenshots saved to `./temporary screenshots/screenshot-N.png` (auto-incremented).
- After screenshotting, read the PNG with the Read tool — analyze it directly.
- When comparing: be specific about spacing, font size/weight, colors (exact hex), alignment, border-radius, shadows.

---

## Output Defaults
- Single `index.html` file, all styles inline, unless user says otherwise
- Tailwind CSS via CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- GSAP via CDN (Tier 2 only): `<script src="https://cdn.jsdelivr.net/npm/gsap@3/dist/gsap.min.js"></script>`
- Placeholder images: `https://placehold.co/WIDTHxHEIGHT`
- Mobile-first responsive

---

## Brand Assets
- Always check the `brand_assets/` folder before designing.
- If a logo is present, use it. If a color palette is defined, use those exact values — do not invent brand colors.

---

## Anti-Generic Guardrails
- **Colors:** Never use default Tailwind palette. Derive from `oklch()`.
- **Shadows:** Never flat `shadow-md`. Always layered, color-tinted, multi-stop.
- **Gradients:** Layer multiple radial gradients. Add SVG noise grain for texture.
- **Animations:** Staggered, spring-eased, scroll-triggered. Never uniform or instant. Never before layout is stable.
- **Interactive states:** Every clickable element needs hover, focus-visible, and active states.
- **Images:** Gradient overlay + `mix-blend-mode` treatment. Never raw `<img>` drops.
- **Spacing:** Fluid tokens via `clamp()`.
- **Layout:** At least one CSS Grid named-area layout per page. No all-flexbox pages.

---

## Hard Rules
- ❌ Do not start building before running the Pre-Build Design Brief
- ❌ Do not use the default centered h1 + subtitle + CTA hero without explicit approval
- ❌ Do not use 3-column equal-card grids for features or services
- ❌ Do not copy reference images or inspiration sites literally
- ❌ Do not stop after one screenshot pass
- ❌ Do not use `transition-all`
- ❌ Do not use default Tailwind blue/indigo as primary color
- ❌ Do not use flat single-stop shadows
- ❌ Do not animate layout properties — only `transform` and `opacity`
- ❌ Do not use fixed px font sizes — always `clamp()`
- ❌ Do not add animations before layout and content are stable and screenshotted
- ✅ A still, polished page beats an animated, broken one