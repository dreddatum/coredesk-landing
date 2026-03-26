# Design System: Industrial Precision & The Bento-Professional Framework

## 1. Overview & Creative North Star: "The Kinetic Blueprint"
This design system is built for the high-stakes environment of enterprise industrial operations. Our Creative North Star is **"The Kinetic Blueprint."** We are moving away from decorative UI and toward a "Hardware-Software Synthesis"—where the interface feels like an illuminated glass control panel integrated into a matte titanium chassis.

Instead of standard enterprise layouts, we utilize a **Bento-Professional** grid: a modular, hyper-efficient arrangement of data "containers" that prioritize information density without sacrificing visual clarity. We break the monotony of the grid through **Functional Asymmetry**—using varied container heights and monospaced data blocks to guide the eye toward critical anomalies and operational metrics.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a "Deep Matte" aesthetic. We utilize a monochromatic base to ensure that our **Hardware Blue** (#3b82f6) acts as a high-precision laser, cutting through the dark to highlight actionable data.

### The "No-Line" Rule
Standard 1px solid borders for sectioning are strictly prohibited for structural layout. True premium design relies on **Tonal Separation**. Boundaries must be defined by the shift between `surface-container-lowest` (#0e0e10) and `surface-container` (#1f1f21). 

### Surface Hierarchy & Nesting
Treat the UI as a series of physical, nested plates.
- **Base Layer:** `background` (#131315).
- **Secondary Workspaces:** `surface-container-low` (#1b1b1d).
- **Interactive Modules (Bento Cells):** `surface-container` (#1f1f21).
- **Active/Hovered States:** `surface-container-high` (#2a2a2c).

### The "Glass & Gradient" Rule
While the core style is flat, we introduce **Optical Depth** through Glassmorphism for floating utility panels (e.g., Command Palettes). Use `surface` colors at 80% opacity with a `20px` backdrop blur. 
*Note: Use subtle gradients only for the `primary` to `primary_container` transition in high-priority CTA buttons to simulate a "backlit" hardware effect.*

---

## 3. Typography: The Technical Editorial
We use a high-contrast typographic scale to separate "Narrative" from "Data."

*   **Display & Headlines (Inter/SF Pro):** Used for high-level status and section headers. Keep tracking tight (-0.02em) to maintain an authoritative, editorial feel.
*   **Monospaced Data (Geist Mono/SF Mono):** All numerical values, timestamps, and industrial IDs must use monospaced fonts. This ensures that columns of changing numbers do not "jitter" and remain perfectly aligned for rapid scanning.
*   **Labeling:** Use `label-sm` (0.6875rem) in `on_surface_variant` (#c2c6d6) for all metadata. This creates a clear visual hierarchy between the *label* and the *value*.

---

## 4. Elevation & Depth: Tonal Layering
We do not use drop shadows to indicate height; we use light.

*   **The Layering Principle:** Depth is achieved by "stacking." A `surface-container-highest` card placed on a `surface-container-low` background creates a natural elevation.
*   **Ambient Glow:** For floating modals, use a shadow with a `40px` blur, `0%` spread, and a color of `primary` at `8%` opacity. This mimics the ambient light of a screen in a dark control room.
*   **The "Ghost Border" Fallback:** Where accessibility requires a container edge (e.g., in high-density tables), use the `outline_variant` (#424754) at **15% opacity**. It should be felt, not seen.

---

## 5. Components & Primitive Styling

### Buttons: The "Hardware Switch"
*   **Primary:** Background `primary_container` (#4d8eff), `on_primary_container` text. Corners: `4px` (md). No shadow.
*   **Secondary:** Ghost style. `Ghost Border` (15% outline_variant) with `on_surface` text.
*   **States:** Hovering a button should never change its color drastically—instead, shift the background to the next `surface-container` tier.

### Bento Cards & Lists
*   **Forbid Dividers:** Do not use horizontal lines to separate list items. Use a `1px` (0.2rem) vertical gap from the spacing scale to let the background bleed through, or use alternating `surface-container-low` and `surface-container-lowest` backgrounds.
*   **Padding:** Use a strict `1.1rem` (spacing.5) internal padding for all Bento cells to maintain "Industrial Breathing Room."

### Data Inputs
*   **Field Style:** Background `surface_container_lowest` (#0e0e10). 
*   **Focus State:** A `1px` border of `primary` (#adc6ff). No "outer glow." The change must be sharp and instantaneous.

### Industrial Sparklines (Special Component)
In place of abstract icons, use **Miniature Sparklines**. These 48x16px data visualizations provide immediate context for a metric's trend without needing a full chart.

---

## 6. Do’s and Don’ts

### Do:
*   **Use Mono for Numbers:** Always. Precision is the priority.
*   **Lean into Asymmetry:** If a data block is more important, let it span 2 columns in the Bento grid while others span 1.
*   **Respect the 4px Radius:** Sharp corners (4px–6px) communicate industrial rigour. Avoid "pill" shapes unless they are functional tags.

### Don't:
*   **Don't Use Pure White:** Never use #FFFFFF. The highest light value should be `on_surface` (#e4e2e4) to prevent eye strain in dark industrial environments.
*   **Don't Use "Organic" Icons:** Avoid rounded, playful, or abstract iconography. If an icon is needed, use "Technical Line Icons" with 1.5px stroke weights and sharp joins.
*   **No Standard Grids:** Avoid the "3-column card row" cliché. Use the spacing scale to create intentional gaps and clusters of information.