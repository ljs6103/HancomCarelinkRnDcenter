# Design System Strategy: The Bioluminescent Frontier

## 1. Overview & Creative North Star
**The Creative North Star: "The Synthetic Organism"**
This design system moves beyond the cold, static nature of traditional high-tech interfaces. It envisions a UI that feels alive—a digital membrane that breathes, glows, and reacts. We are merging the precision of laboratory instrumentation with the vast, immersive depth of deep-space exploration. 

To break the "template" look, we reject rigid, boxed-in grids. Instead, we utilize **intentional asymmetry** and **overlapping glass layers**. Elements should feel as though they are floating in a pressurized fluid, using high-contrast typography scales (Space Grotesk) to anchor the eye against the soft, ethereal glows of the background.

## 2. Colors & Atmospheric Depth
The palette is rooted in the "Deep Space" void, punctuated by "Bioluminescent" accents.

### The "No-Line" Rule
Traditional 1px solid borders are strictly prohibited for defining sections. Structure must be felt, not seen. Define boundaries through:
*   **Tonal Shifts:** Placing a `surface_container_low` card against a `surface` background.
*   **Glow Intersections:** Using a subtle `primary` glow to indicate the start of a new content cluster.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, frosted glass sheets. 
*   **Base:** `surface` (#080f18) serves as the infinite vacuum.
*   **Primary Containers:** Use `surface_container` for main content areas.
*   **Nested Elements:** Use `surface_container_high` for interactive elements within a panel. This creates "Natural Depth" where the UI feels carved out of the darkness rather than printed on top of it.

### The Glass & Gradient Rule
To achieve "High-Tech Bio" prestige, main CTAs and Hero headers must utilize linear gradients. Transition from `primary` (#81ecff) to `primary_container` (#00e3fd) at a 135-degree angle. This mimics the refraction of light through a biological lens.

## 3. Typography: The Editorial Contrast
We pair the technical, geometric personality of **Space Grotesk** with the hyper-functional clarity of **Inter** (Pretendard-compatible).

*   **Display & Headlines (Space Grotesk):** These are your "Technical Spec" markers. Use `display-lg` (3.5rem) for hero moments with tight tracking (-2%). These should feel authoritative and cinematic.
*   **Body & Titles (Inter):** These provide the "Scientific Narrative." `body-md` (0.875rem) is the workhorse. Ensure a line-height of 1.6 for maximum breathability against the dark background.
*   **Labels (Space Grotesk):** Use `label-md` in all-caps with +5% letter spacing for a "HUD" (Heads-Up Display) aesthetic.

## 4. Elevation & Depth: Tonal Layering
In this system, light is the only architect. We do not use structural lines to separate ideas.

*   **The Layering Principle:** Place `surface_container_lowest` elements on top of `surface_container_low` to create a "recessed" look, or `surface_container_highest` to create a "protruding" look.
*   **Ambient Shadows:** Floating modals must use a shadow with a 40px–60px blur, at 8% opacity, tinted with the `primary` color (#81ecff). This simulates the way neon light scatters in a high-tech environment.
*   **The "Ghost Border" Fallback:** If a container requires a border for accessibility, use the `outline_variant` token at **15% opacity**. A 100% opaque border is considered a design failure.
*   **Glassmorphism:** Apply a `backdrop-filter: blur(20px)` to any surface using the `surface_variant` or `surface_container` tokens. This allows the deep space background to bleed through, softening the interface.

## 5. Components

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary_dim`), `lg` (1rem) border radius. No border. Text is `on_primary`.
*   **Secondary:** Ghost style. 1px `outline_variant` (at 20% opacity). On hover, the border glows with `primary` and a subtle inner-shadow.
*   **Tertiary:** Text-only in `primary` color, Space Grotesk `label-md` styling.

### Cards & Lists
*   **Cards:** Forbid divider lines. Use `16` (4rem) vertical spacing between list items. Use a subtle `surface_bright` background shift on hover to indicate interactivity.
*   **Glow-Cards:** For featured bio-data, use a 1px `primary` border at 10% opacity with a 15px `primary` outer glow at 5% opacity.

### Inputs
*   **Text Fields:** `surface_container_lowest` background. The active state should not change the border color to a solid line, but rather trigger a soft `primary` glow (`box-shadow`) around the entire field.

### Specialized Components
*   **Data Scanners:** Vertical scrolling tickers using `label-sm` typography to simulate real-time bio-data processing.
*   **Bio-Glow Progress Bars:** A track of `surface_container_highest` with a progress fill of `primary` that has a `primary_container` outer glow.

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical layouts where text is pushed to one side and imagery/data-viz overlaps the container edges.
*   **Do** use `primary_fixed_dim` for icons to ensure they feel "powered on."
*   **Do** embrace negative space. The `24` (6rem) spacing token is your friend for separating major sections.

### Don't:
*   **Don't** use pure white (#FFFFFF). Use `on_surface` (#e8eefc) to prevent eye strain against the dark background.
*   **Don't** use 1px solid borders at 100% opacity. This shatters the "glassmorphism" illusion.
*   **Don't** use standard drop shadows. If it doesn't look like light refracting through a lens, it doesn't belong.