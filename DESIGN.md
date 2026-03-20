# Design System Document: High-End Hospitality & Technical Precision

## 1. Overview & Creative North Star: "The Digital Concierge"

This design system is built on the philosophy of **The Digital Concierge**. It rejects the cluttered, "bubbly" aesthetics of mainstream travel platforms in favor of the high-utility, high-aesthetic precision found in elite productivity software. We are blending the cold, crisp efficiency of a technical tool with the warm, atmospheric invitingness of a premium physical space.

To achieve this, we move beyond the "grid-and-border" template. We utilize **Intentional Asymmetry**—where large-scale typography might sit flush-left against a vast expanse of negative space—and **Tonal Layering**, where depth is felt through color shifts rather than seen through lines. The result is a UI that feels less like a website and more like a high-end editorial lookbook.

---

## 2. Colors & Surface Logic

Our palette is rooted in deep obsidian tones, punctuated by "Electric Indigo" accents that guide the eye without overwhelming the content.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or layout containment. Structural boundaries must be defined solely through background color shifts. For example, a `surface_container_low` section sitting on a `surface` background creates a clear but sophisticated division.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use the Material surface tiers to create "nested" depth:
- **Base Layer:** `surface` (#0e0e0e) for the primary background.
- **Sectioning:** Use `surface_container_low` (#131313) for large content blocks.
- **Floating Interactive Elements:** Use `surface_container_high` (#1f2020) for cards and modals to provide a subtle "lift."

### The "Glass & Gradient" Rule
To elevate the experience from "dark mode" to "premium experience," use **Glassmorphism** for navigation bars and floating action menus. 
- Use a semi-transparent `surface_container` with a `backdrop-filter: blur(20px)`.
- **Signature Textures:** Main CTAs should utilize a subtle linear gradient from `primary` (#c2c1ff) to `primary_container` (#332dbc) at a 135-degree angle to provide a "soul" that flat hex codes cannot achieve.

---

## 3. Typography: Editorial Authority

We use **Inter** exclusively. The power of this system lies in the high-contrast scale between `display` and `body` styles.

*   **Display (lg/md):** Used for property titles or hero statements. Letter spacing should be set to `-0.02em` to create a "tight," professional feel.
*   **Headline (sm/md):** Used for section headers. Always pair these with ample white space (Scale 16 or 20) above the text to let the heading breathe.
*   **Body (md):** Our workhorse. Use `on_surface_variant` (#acabaa) for secondary descriptions to maintain a clear hierarchy against `on_surface` titles.
*   **Label (sm):** Set in `uppercase` with `0.05em` letter spacing for small metadata (e.g., "SQ FT," "MAX GUESTS") to mimic high-end architectural drawings.

---

## 4. Elevation & Depth: Tonal Layering

We convey hierarchy through light and atmosphere, not structural scaffolding.

*   **The Layering Principle:** Place a `surface_container_lowest` (#000000) element inside a `surface_container_low` (#131313) wrapper to create a "sunken" effect for input fields or code-like snippets.
*   **Ambient Shadows:** For floating modals, use a shadow with a 40px-60px blur and 6% opacity. The shadow color must be tinted with `primary` (#c2c1ff) rather than pure black to simulate the way light interacts with dark surfaces.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline_variant` (#484848) at **15% opacity**. Never use 100% opaque borders; they shatter the "Digital Concierge" atmosphere.
*   **Glassmorphism:** Apply to elements that exist *above* the content (e.g., sticky headers). This allows the property photos to bleed through the UI, softening the interface and integrating it with the photography.

---

## 5. Components

### Buttons
*   **Primary:** Gradient of `primary` to `primary_container`. Corner radius `md` (0.375rem). No border.
*   **Secondary:** `surface_container_highest` background with `on_surface` text. Subtle `Ghost Border` on hover.
*   **Tertiary:** Text-only using `primary_dim`. High-focus on the `label-md` typography.

### Input Fields
*   **Styling:** Forbid 100% opaque borders. Use `surface_container_lowest` for the field background with a `sm` (0.125rem) radius. On focus, transition the background to `surface_container_high` and add a subtle `primary` glow.

### Cards & Lists
*   **Rule:** Forbid the use of divider lines. Separate list items using the **Spacing Scale 2** (0.7rem) of vertical white space or a subtle background hover shift to `surface_container_low`.
*   **Cards:** Use `surface_container` for the card body. Images should have a `DEFAULT` (0.25rem) corner radius to feel precise and "tech-forward."

### Booking Specifics (App Context)
*   **The Availability Calendar:** Use a "No-Line" grid. Dates are separated by negative space. Selected dates use a `primary` background with `on_primary` text. Out-of-range dates use `on_surface_variant` at 30% opacity.
*   **Atmospheric Overlays:** When displaying property galleries, use a `surface_dim` overlay with 40% opacity to ensure `display-lg` text remains legible while maintaining the mood of the photo.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical margins. If the left margin is 5.5rem (Scale 16), try a right margin of 8.5rem (Scale 24) for hero sections to create an editorial feel.
*   **Do** prioritize `primary` (#c2c1ff) for interactive states only. It is a "light source" in our dark environment; use it sparingly.
*   **Do** use `surface_bright` (#2c2c2c) for subtle hover states on dark buttons to indicate interactivity without changing the hue.

### Don't
*   **Don't** use sharp 90-degree corners. Even a `sm` (0.125rem) radius softens the "tech" feel and makes the listing feel "welcoming."
*   **Don't** use pure white (#ffffff) for long-form body text. Use `on_surface` (#e7e5e4) to reduce eye strain against the deep black background.
*   **Don't** ever use a 1px solid divider. If you feel you need a line, use a 4rem (Scale 12) gap of empty space instead.