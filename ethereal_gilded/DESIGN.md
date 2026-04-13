# Design System Document: The Editorial Excellence Framework

## 1. Overview & Creative North Star: "The Gilded Curator"

The objective of this design system is to transcend the "service platform" aesthetic and arrive at a "digital gala" experience. We are moving away from the rigid, boxed-in layouts of standard event management tools toward a high-end editorial feel. 

**Creative North Star: The Gilded Curator**
The interface acts as a silent, sophisticated concierge. We achieve this through **Intentional Asymmetry**—placing large-scale serif typography off-center to create a sense of movement—and **Expansive Negative Space**. By allowing elements to "breathe" beyond traditional grid boundaries, we signal exclusivity. The brand doesn't need to crowd the screen; it owns the space it occupies.

---

## 2. Colors & Tonal Depth

Our palette is rooted in the interplay between the warmth of `primary` (#735c00) and the stark authority of `on_background` (#1c1b1b).

### The "No-Line" Rule
**Prohibition:** 1px solid borders for sectioning are strictly forbidden. 
**Implementation:** Define boundaries through background shifts. A `surface_container_low` section should sit against a `surface` background to create a "zone" without a hard edge. This creates a seamless, fluid transition between content blocks.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of fine, heavy-weight paper.
- **Layer 0 (Base):** `surface` (#fcf9f8) for the main canvas.
- **Layer 1 (Nesting):** Use `surface_container_low` for large content areas.
- **Layer 2 (Focus):** Use `surface_container_lowest` (#ffffff) for floating cards to create a subtle "pop" against the off-white base.

### The "Glass & Gradient" Rule
To evoke the "Aura" in the brand name, use `surface_tint` at 5-10% opacity with a `backdrop-blur` (20px+) for navigation bars and floating overlays. 
- **Signature Texture:** Apply a subtle linear gradient (45deg) from `primary_container` (#d4af37) to `primary` (#735c00) on high-impact CTAs. This mimics the light-catching quality of real metallic gold.

---

## 3. Typography: The Editorial Voice

We utilize a high-contrast pairing to balance heritage with modernity.

- **Display & Headlines (`notoSerif`):** These are our "hero" elements. Use `display-lg` for impactful statements. Letter-spacing should be slightly tightened (-2%) to feel bespoke and authoritative.
- **Body & Labels (`manrope`):** A technical, clean sans-serif that ensures the interface remains functional and professional.
- **The Hierarchy Strategy:** Large `display` type should often be paired with `label-md` in all-caps (tracked out 10%) to create a rhythmic, magazine-style layout.

---

## 4. Elevation & Depth

### The Layering Principle
Avoid structural lines. If a card needs to stand out, do not outline it. Place a `surface_container_lowest` card on a `surface_container_high` background. This "Tonal Layering" creates depth that feels organic rather than synthetic.

### Ambient Shadows
Where physical lift is required (e.g., a modal or primary action card), use the following shadow spec:
- **X: 0, Y: 20px, Blur: 40px**
- **Color:** `on_surface` at **6% opacity**. 
The goal is an "ambient glow" rather than a drop shadow.

### The "Ghost Border" Fallback
If accessibility requirements demand a container boundary, use a **Ghost Border**:
- **Token:** `outline_variant` (#d0c5af)
- **Opacity:** 20%
- **Weight:** 1px

---

## 5. Components

### Buttons
- **Primary:** Gradient-fill (`primary_container` to `primary`), `xl` (1.5rem) border-radius. No border. Text: `title-sm` in `on_primary`.
- **Secondary:** Transparent background with a `Ghost Border`. Text in `primary`.
- **Tertiary:** Text-only in `secondary`, underlined only on hover.

### Cards & Lists
- **The "No-Divider" Mandate:** Forbid horizontal lines between list items. Use 24px of vertical white space (`spacing-6`) or alternating `surface_container` tints to separate entries.
- **Radius:** All cards must use `xl` (1.5rem) roundedness to soften the charcoal and gold's intensity.

### Input Fields
- **Style:** Underline-only or subtle `surface_container_high` fills. 
- **State:** On focus, the underline transitions from `outline_variant` to `primary` (Gold) with a soft 4px outer glow of `primary_fixed`.

### Signature Component: The "Exclusive Modal"
A full-screen overlay using `surface` at 95% opacity with a heavy blur. Content is centered with `display-md` headings, creating a focused, high-end "entry" experience for the user.

---

## 6. Do's and Don'ts

### Do:
- **Do** use asymmetrical margins. (e.g., 10% left margin, 20% right margin) to create editorial interest.
- **Do** use `primary` (Gold) sparingly as an accent—it is a jeweler’s touch, not a wall paint.
- **Do** leverage `surface_container_lowest` (#FFFFFF) to create "light" in the layout.

### Don't:
- **Don't** use pure black (#000000). Always use `on_background` (#1c1b1b) for a softer, premium charcoal feel.
- **Don't** use standard `md` or `sm` border radii. This brand is "soft-luxury"—stick to `lg` and `xl`.
- **Don't** use icons with heavy fills. Use light-stroke (1px or 1.5px) icons to match the `manrope` typography weight.

### Accessibility Note:
While we prioritize aesthetics, ensure `primary` text on `surface` meets AA contrast ratios. If the metallic gold is too light for small labels, fallback to `on_surface_variant` (#4d4635) for readability.