# Design System Document: The Editorial Developer
 
## 1. Overview & Creative North Star: "The Digital Curator"
This design system is built to bridge the gap between technical precision and editorial elegance. The Creative North Star is **The Digital Curator**: a philosophy where the interface disappears to let the work breathe, treating every portfolio entry like a high-end gallery installation.
 
We move beyond the "bootstrap" look by embracing **intentional asymmetry**—offsetting headings from body text and using expansive whitespace as a functional element rather than a void. The goal is a "Quiet Luxury" aesthetic: expensive-feeling, highly legible, and devoid of unnecessary decorative clutter.
 
## 2. Colors & Tonal Depth
The palette is a sophisticated range of warm neutrals and slate-toned primaries. Instead of using lines to separate ideas, we use "Tonal Sculpting."
 
### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders are prohibited for sectioning. Boundaries must be defined solely through background color shifts.
*   **Example:** A `surface-container-low` section sitting on a `surface` background provides all the separation the eye needs.
 
### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the `surface-container` tiers to create depth:
*   **Base Layer:** `surface` (The gallery wall)
*   **Section Layer:** `surface-container-low` (The display plinth)
*   **Active Component Layer:** `surface-container-highest` (The spotlighted item)
 
### The "Glass & Gradient" Rule
To ensure the "Frontend Developer" persona shines through, use **Glassmorphism** for floating elements (like Navigation Bars or Tooltips). 
*   **Implementation:** Use semi-transparent versions of `surface` with a `backdrop-filter: blur(20px)`.
*   **Signature Texture:** Main CTAs should use a subtle linear gradient from `primary` to `primary_dim` (135° angle) to add "soul" and a tactile, premium finish.
 
## 3. Typography: The Editorial Contrast
We use a high-contrast pairing to distinguish between "Information" (Sans) and "Narrative" (Serif).
 
*   **Display & Headlines (Manrope - Geometric Sans):** Used for navigation, UI labels, and section titles. It communicates the "Developer" side—precision, logic, and modernism.
    *   *Scale Example:* `display-lg` (3.5rem) for high-impact project titles.
*   **Body & Titles (Newsreader - Serif):** Used for case study narratives, "About Me" sections, and storytelling. It communicates the "Designer" side—humanity, history, and craft.
    *   *Scale Example:* `body-lg` (1rem) with a generous `line-height` (1.6) for readability.
 
**Hierarchy Note:** Use `label-md` in all-caps with `0.1em` letter-spacing for category tags to create an authoritative, architectural feel.
 
## 4. Elevation & Depth
In this system, depth is felt, not seen. We avoid heavy dropshadows in favor of **Tonal Layering**.
 
*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section. This creates a "soft lift" that feels integrated into the page.
*   **Ambient Shadows:** If an element must float (e.g., a modal or mobile menu), use the following: `box-shadow: 0 20px 40px rgba(49, 51, 52, 0.06);`. The shadow color must be a tinted version of `on-surface`, never pure black.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline-variant` token at **15% opacity**. 100% opaque borders are forbidden.
 
## 5. Components
 
### Buttons
*   **Primary:** Background `primary` gradient to `primary_dim`, text `on-primary`. Radius: `md` (0.375rem).
*   **Secondary:** No background. `Ghost Border` (15% opacity `outline`) with `primary` text.
*   **Tertiary (Editorial Link):** `Newsreader` (Serif) text with a 1px underline that sits 4px below the baseline. On hover, the underline increases to 2px thickness.
 
### Cards & Case Study Previews
*   **Rule:** Forbid divider lines.
*   **Structure:** Use vertical whitespace (referencing the spacing scale) to separate the image from the metadata. Use `surface-container-low` as the card background to subtly lift it from the `surface` background.
 
### Input Fields
*   **Style:** Minimalist underline style. Only the bottom border is visible using `outline-variant`. On focus, the border transitions to `primary` and thickens to 2px.
*   **Labels:** Always `label-sm` in `Manrope` (Sans) to maintain the technical feel.
 
### Chips (Tech Stack Tags)
*   **Style:** `surface-container-high` background with no border. Text uses `label-md` in `on-surface-variant`. Use `rounded-full` for a softer, organic counterpoint to the geometric headings.
 
### Signature Component: The "Floating Narrative"
*   A side-scrolling or pinned container for "Technical Implementation" notes. Use `surface-container-lowest` with a `backdrop-blur`, placed asymmetrically over project imagery.
 
## 6. Do's and Don'ts
 
### Do:
*   **Embrace the Offset:** Align headlines to the left but indent body text to create a modern, editorial rhythm.
*   **Use the Primary Color Sparingly:** The accent (`primary` / `secondary` range) should be a "surgical" strike—used only for CTAs, active states, or key highlights.
*   **Respect the "Newsreader" Serif:** Use it for long-form reading. It’s the "voice" of the designer.
 
### Don't:
*   **Don't Use Pure Black:** Even in Dark Mode, use `inverse_surface` or `on_background` to keep the palette soft and premium.
*   **Don't Use Borders to Grid the Layout:** If the layout feels messy, increase whitespace rather than adding lines.
*   **Don't Center-Align Everything:** Center-alignment is the mark of a template. Use purposeful left-alignment or asymmetric balancing.