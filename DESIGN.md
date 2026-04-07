# Design System Strategy: The Editorial Curator

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Editorial Curator."** 

We are moving away from the "software-as-a-service" aesthetic of rounded rectangles and generic grids. Instead, we are treating the interface as a high-end digital publication. This system leverages the friction between a warm, traditional cream background and a futuristic, vibrant lime accent. The goal is to create a signature experience through intentional asymmetry, massive typographic contrast, and a rejection of traditional UI "lines." 

We don't use borders to separate ideas; we use space, shifts in tonal temperature, and bold alignment. The design should feel "architectural"—stable and professional, yet punctuated by sharp, electric moments of modernism.

---

## 2. Colors
Our palette is a study in high-contrast sophistication. The warmth of the cream base prevents the interface from feeling clinical, while the lime green provides an aggressive, confident energy.

### Core Palette
- **Surface (Background):** `#fefdf1` — Our "canvas." All layouts begin here.
- **On-Surface (Primary Text):** `#373830` — A deep, warm charcoal. Use this instead of pure black for a softer, premium editorial feel.
- **Primary (Accent):** `#566d00` — The signature lime. To be used sparingly and surgically.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or containment. Boundaries must be defined solely through background color shifts. 
- Use `surface-container-low` (`#fbfaed`) to define a section against the main `surface`.
- Use `surface-container-highest` (`#e9e9da`) for footer areas or high-contrast sidebars.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine paper. 
- **Tier 1:** `surface` (The base sheet).
- **Tier 2:** `surface-container` (Nested content areas).
- **Tier 3:** `surface-bright` (For cards or elements that need to "pop" forward).

### Signature Textures & Glass
To elevate the experience, floating navigation or modal overlays must use **Glassmorphism**:
- **Token:** `surface` at 80% opacity + 20px backdrop-blur.
- **Gradients:** For primary CTAs, use a subtle linear gradient from `primary` (`#566d00`) to `primary-container` (`#d5f967`) at a 135-degree angle. This adds a "lithographic" depth that flat color lacks.

---

## 3. Typography
The typography is the voice of the brand. We pair the brutalist, bold energy of **Epilogue** with the modern, precise functionalism of **Manrope**.

- **Display & Headlines (Epilogue):** Set with tight letter-spacing (-0.02em) and heavy weights. This is our "Editorial" voice. 
    - *Display-LG (3.5rem):* Reserved for hero moments. Use asymmetrical placement.
    - *Headline-SM (1.5rem):* Used for section starts, always in `on-surface`.
- **Body & Titles (Manrope):** Set with generous leading (1.5x) for maximum readability. 
    - *Body-LG (1rem):* The workhorse for all long-form content.
    - *Label-MD (0.75rem):* Always uppercase with +0.05em letter-spacing for a "technical" look.

The hierarchy communicates authority: huge, bold statements followed by clean, quiet data.

---

## 4. Elevation & Depth
We convey hierarchy through **Tonal Layering** rather than traditional structural shadows.

- **The Layering Principle:** Depth is achieved by "stacking." A card using `surface-container-lowest` (`#ffffff`) placed on a `surface-container` (`#f5f4e7`) background creates a natural, soft lift.
- **Ambient Shadows:** When an element must float (e.g., a primary dropdown), use a "shadow-tint."
    - **Specs:** `0px 24px 48px rgba(55, 56, 48, 0.06)`. Note the color is a transparent version of our `on-surface` charcoal, not black.
- **The "Ghost Border" Fallback:** If a border is required for accessibility, use `outline-variant` (`#babaaf`) at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons: The "Sharp Accent"
- **Primary:** High-contrast `primary` background with `on-primary` (white) text. Radius: `md` (0.375rem). No shadow.
- **Secondary:** `surface-container-high` background with `on-surface` text.
- **Tertiary:** Text-only in `primary` green, but with a 2px underline that only appears on hover.

### Cards & Lists: The "Whitespace" Container
- **Rule:** Forbid the use of divider lines. 
- Separate list items using a 16px or 24px vertical gap. 
- For cards, use a slight background shift to `surface-container-low` rather than a border. 

### Input Fields: The "Minimalist Entry"
- Underline-only style or a very subtle `surface-container-highest` background. 
- The label should use `label-sm` in `on-surface-variant`, moving to `primary` green when the field is active.

### Signature Component: The "Editorial Quote"
- A large-scale component using `display-sm` (Epilogue) with a 4px left-accent bar in `primary` lime green. This anchors the page and breaks the flow of standard body text.

---

## 6. Do's and Don'ts

### Do:
- **Do** use intentional white space. If a layout feels "full," it is likely over-designed.
- **Do** use asymmetrical layouts (e.g., a 2-column grid where one column is 33% and the other is 66%).
- **Do** use the `primary` green for high-intent actions only (CTAs, success states, active navigation).

### Don't:
- **Don't** use 100% opaque black. Always use the `on-surface` charcoal (`#373830`).
- **Don't** use "Standard" drop shadows. If it looks like a default UI kit, it has failed.
- **Don't** use divider lines to separate content sections. Use a 120px - 160px vertical spacer or a change in surface color.
- **Don't** use the `primary` green for large background areas; it will overwhelm the "Sophisticated" vibe. It is a scalpel, not a bucket.