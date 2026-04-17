```markdown
# The Design System: Editorial Precision & Calm Luxury

## 1. Overview & Creative North Star: "The Digital Curator"
This design system is built on the intersection of **heritage hospitality** and **technical precision**. Our Creative North Star is **"The Digital Curator."** 

Unlike standard landing pages that feel like a collection of blocks, this system treats the interface as a high-end gallery. We break the "template" look by utilizing intentional asymmetry, expansive negative space (breathing room), and a "Bento-Grid" logic that feels meticulously engineered rather than randomly placed. The goal is to evoke the quiet confidence of a Capella Hotel suite paired with the obsessive functional clarity of a high-end productivity tool like Linear.

---

## 2. Colors & Surface Architecture
The palette is rooted in a **Deep Anthracite** ecosystem, moving away from pure blacks to allow for "internal glow" and depth.

### The Palette
- **Background (`#131313`):** The canvas. A deep, soulful anthracite.
- **Primary Indigo (`#bdc2ff`):** Used sparingly for "moments of intent"—CTAs and active states.
- **On-Surface (`#e5e2e1`):** An off-white, warm-tinted linen for high-readability and elegance.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections. Conventional dividers feel "cheap" and structural. Instead, define boundaries through:
1. **Background Shifts:** Transition from `surface` to `surface-container-low`.
2. **Negative Space:** Use the Spacing Scale (specifically `16` and `20`) to create "islands" of content.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine paper or frosted glass. Use the `surface-container` tiers to create nested depth:
- **Base Level:** `surface` (#131313)
- **Section Insets:** `surface-container-low` (#1c1b1b) for subtle grouping.
- **Interactive Cards:** `surface-container-high` (#2a2a2a) to suggest a physical "lift."

### The "Glass & Gradient" Rule
To escape the "flat" look, apply `backdrop-blur` (12px–20px) to floating navigation or modal elements using semi-transparent surface colors. Use a subtle linear gradient on `primary` buttons (transitioning from `#bdc2ff` to `#818cf8`) to provide a "lit from within" quality.

---

## 3. Typography: Editorial Authority
The typography system relies on the tension between the timeless **Playfair Display** (notoSerif tokens) and the hyper-modern **Inter**.

- **Display & Headlines (Playfair Display):** These are our "hero" moments. Use `display-lg` for value propositions. Increase letter-spacing slightly on `headline-sm` to create an airy, premium feel.
- **Body & Titles (Inter):** These provide the "technical precision." Use `body-md` for general descriptions. Inter provides the structural reliability that balances the romanticism of the Serif.
- **Labels (Inter + Monospace weight):** For technical specs (e.g., square footage, floor numbers), use `label-md` in uppercase with `0.05em` letter-spacing.

---

## 4. Elevation & Depth
We reject heavy drop shadows. We communicate hierarchy through **Tonal Layering**.

### The Layering Principle
Depth is achieved by "stacking." Place a `surface-container-highest` element inside a `surface-container-low` parent. This creates a soft, natural lift without requiring a shadow.

### Ambient Shadows
If an element must float (e.g., a "Book a Viewing" float-bar):
- **Shadow:** 0px 20px 40px rgba(0, 0, 0, 0.4).
- **Tint:** Infuse the shadow with a hint of `primary` to make it feel integrated into the dark environment.

### The "Ghost Border" Fallback
Where containment is required for UX clarity, use a **Ghost Border**:
- **Token:** `outline-variant` (#454653) at **15% opacity**.
- **Rule:** Never use 100% opaque borders for decorative framing.

---

## 5. Components

### Buttons (The "Jewelry" of the UI)
*   **Primary:** Indigo background (`primary`), `on-primary` text. No border. Soft `sm` or `md` corners.
*   **Secondary (Ghost):** `outline-variant` border at 20% opacity. Text in `on-surface`.
*   **Tertiary:** Text-only in `primary` with a 1px underline that expands on hover.

### Bento Cards
*   **Style:** No borders. Use `surface-container-low`.
*   **Spacing:** Use `spacing-8` for internal padding.
*   **Content:** Forbid divider lines. Use vertical white space (`spacing-4`) to separate the image from the description.

### Input Fields
*   **Surface:** `surface-container-lowest`. 
*   **Border:** A "Ghost Border" that transitions to 100% `primary` opacity on focus.
*   **Label:** Use `label-sm` in `on-surface-variant`.

### Signature Component: The "Feature Bento"
A grid of varying sizes (1x1, 2x1, 1x2) using `surface-container-low`. Each card should have a subtle internal glow (a radial gradient from the top-left corner, 5% opacity `primary`).

---

## 6. Do’s and Don’ts

### Do:
- **Use "Asymmetric Balance":** Place a large `display-lg` heading on the left and a small `body-md` paragraph on the right with ample white space between.
- **Embrace the Grid:** Use the Bento-grid logic for technical specifications (amenities, floor plans).
- **Subtle Motion:** All transitions (hover, entry) should be slow and "weighted" (e.g., `cubic-bezier(0.2, 0, 0, 1)` over 400ms).

### Don't:
- **No Pure Black:** Never use `#000000`. It kills the "calm luxury" and feels harsh.
- **No Dividers:** Avoid horizontal rules (`<hr>`). If you feel you need a divider, you actually need more white space.
- **No High-Contrast Borders:** Standard 1px solid white/grey borders are strictly prohibited. They interrupt the eye and break the "curated" flow.
- **No Default Shadows:** Never use the default "Drop Shadow" preset in your design tool. Always hand-tune for extreme diffusion.