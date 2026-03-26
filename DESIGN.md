# Design System Specification: The Quiet Authority

## 1. Overview & Creative North Star
The objective of this design system is to move beyond the "SaaS Template" look and into the realm of **The Quiet Authority**. Inspired by high-end editorial layouts and premium fintech interfaces, this system treats white space as a structural element rather than a void. 

To achieve an "Elite Enterprise" feel, we reject the rigid, boxed-in nature of traditional dashboards. Instead, we utilize **Intentional Asymmetry** and **Tonal Depth**. By overlapping cards slightly or using exaggerated margins for "Display" typography, we create a sense of bespoke craftsmanship. The interface shouldn't just be "clean"—it should feel curated, like a gallery space where every pixel has permission to exist.

---

## 2. Color & Surface Architecture
We move away from the "line-drawn" web. In this system, boundaries are felt, not seen.

### The "No-Line" Rule
1px solid borders are strictly prohibited for sectioning or defining layout. Boundaries must be defined solely through background color shifts or subtle tonal transitions.
- **Base Environment:** The global background is `surface` (#f8f9fa).
- **Surface Nesting:** Hierarchy is achieved by stacking surface tiers.
    - **Level 1 (Base):** `surface` (#f8f9fa)
    - **Level 2 (Sectioning):** `surface-container-low` (#f3f4f5)
    - **Level 3 (Primary Content/Cards):** `surface-container-lowest` (#ffffff)
- **Glassmorphism:** For floating navigation or modal overlays, use `surface-container-lowest` at 80% opacity with a `20px` backdrop-blur. This ensures the "Elite" feel by maintaining context of the layers beneath.

### Signature Textures
Avoid flat primary blocks for large areas. Use a subtle linear gradient for primary CTAs or hero states:
- **Primary Gradient:** From `primary` (#091426) to `primary_container` (#1e293b) at a 135° angle. This adds a "weighted" feel to the interaction points.

---

## 3. Typography
We use **Inter** as our typographic backbone, treated with an editorial eye.

- **Display & Headline:** Use `display-lg` and `headline-lg` with a slightly tighter letter-spacing (-0.02em) to create a high-fashion, authoritative look. These should be `on_surface` (#191c1d).
- **The "Mono" Exception:** Use monospaced fonts (e.g., Inter Tight or a dedicated Mono) exclusively for currency, timestamps, and data points. This signals "Enterprise Precision" amidst the "Lifestyle" aesthetic of the sans-serif body.
- **Hierarchy through Scale:** Do not rely on bolding everything to show importance. Use the contrast between `display-sm` (2.25rem) and `label-md` (0.75rem) to guide the eye.

---

## 4. Elevation & Depth
Traditional drop shadows are too "heavy" for this system. We use **Ambient Occlusion** logic.

- **The Layering Principle:** Place a `surface-container-lowest` (#ffffff) card on a `surface-container-low` (#f3f4f5) background. This creates a soft, natural lift without a single shadow.
- **Ambient Shadows:** When a float is required (e.g., a dropdown or active card), use a diffused shadow: `0 4px 20px -2px rgba(25, 28, 29, 0.06)`. Note the use of the `on-surface` color for the shadow tint rather than pure black.
- **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., input focus), use `outline-variant` (#c5c6cd) at 40% opacity. 100% opacity borders are forbidden.

---

## 5. Components

### Buttons
- **Primary:** Solid `primary` (#091426) with `on_primary` (#ffffff) text. Use `xl` (1.5rem) or `lg` (1.0rem) rounded corners.
- **Secondary:** `secondary_container` (#82f5c1) with `on_secondary_container` (#00714e). This emerald-on-mint look provides a "high-end fintech" feel for growth-related actions.
- **Interaction:** On hover, primary buttons should shift slightly to the gradient texture mentioned in Section 2.

### Cards & Lists
- **The "No-Divider" Rule:** Forbid the use of 1px divider lines between list items. Use vertical white space (`spacing-4` or `spacing-6`) or a very subtle background hover state (`surface-container-high`) to separate content.
- **Corner Radius:** All cards must use `lg` (1rem / 16px) or `md` (0.75rem / 12px) corners. 

### Input Fields
- Avoid the "box" look. Use `surface-container-low` as a subtle fill for the input area with no border. Upon focus, transition the background to `surface-container-lowest` (pure white) and add a "Ghost Border."

### The "Silent" Data Table
In an enterprise context, tables are often cluttered. This system uses:
- **Leading Margin:** A wide 24px left-padding on the first column.
- **Hover-Highlight:** Instead of row lines, use a `surface-container-highest` background on row hover with a `md` (12px) corner radius on the row itself.

---

## 6. Do’s and Don'ts

### Do
- **Do** use `spacing-12` (3rem) and `spacing-16` (4rem) to separate major sections. The system thrives on "breathing room."
- **Do** use thin linear icons (Lucide style) with a `1.5px` or `2px` stroke weight.
- **Do** use `primary_fixed_dim` (#bcc7de) for subtle supporting text that needs more "soul" than standard gray.

### Don't
- **Don't** use pure #000000 black. Use `primary` (#091426) for "Black" and `on_surface` (#191c1d) for standard text.
- **Don't** use standard "Blue" for links. Use the Emerald `secondary` (#006c4a) or keep it `primary` with an underline.
- **Don't** cram content. If a card feels full, increase the page height rather than shrinking the elements.