# Build Journal

## August 15, 2026 — Radix XII Slide Rule

    Note: This journal entry was written entirely by AI, summarizing our prompting session this morning. We did all this in just under one hour.

Today we turned the original rudimentary base-12 canvas demo into **Radix XII**, an interactive SVG slide rule inspired by classic Keuffel & Esser instruments.

### Rebuilding the instrument

We replaced the small two-scale canvas with a responsive, SVG-rendered instrument. The new rule received engraved-style graduations, fixed rails, a movable centre slide, metal end fittings, screws, a transparent glass cursor, and a draggable hairline. Everything remains contained in one dependency-free HTML file.

The interaction model was expanded to support:

- Pointer and touch dragging for the centre slide and cursor
- Mouse-wheel and arrow-key fine adjustment
- Shift-arrow cursor adjustment
- Reset controls and double-click reset
- Live dozenal readouts for the multiplicand, multiplier, and product

### Building the scale set

We progressively expanded the mathematical capabilities from the original C/D pair to seven scales:

- **K** — a fixed three-cycle scale for cubes and cube roots
- **A** — a fixed two-cycle scale for squares and square roots
- **B** — the corresponding movable two-cycle scale
- **CI** — a reversed `1/x` reciprocal scale, rendered in muted red
- **C** — the primary movable multiplier and divisor scale
- **D** — the primary fixed value and result scale
- **L** — a linear scale from `0` to `1` for base-12 logarithms

The scale geometry was generated in JavaScript using base-12 logarithms. We verified the multiplication transforms, reciprocal direction, K-scale cube relationship, and D/L logarithm alignment with deterministic test cases.

We also adopted ASCII dozenal notation throughout:

- `X` = dek
- `E` = el
- `10` = twelve

### Refining the physical illusion

Several small changes made the SVG feel more like a real instrument:

- Tightened the paired horizontal baselines between adjacent scales
- Removed redundant separator and slide-border lines
- Added a dark open channel beneath the movable slide, matching the background behind the rule
- Matched the top and bottom fixed rails with a light blue-grey enamel
- Lightened the centre slide and reduced its grain so it reads as a separate component
- Shifted all scale identifiers slightly right to clear the left end fitting
- Moved the original maker label away from the C scale, then removed it when the K scale needed the space

### Establishing the visual identity

The initial green-and-gold direction evolved into a cleaner naval-instrument palette:

- Midnight-blue field
- Cool white and blue-grey enamel
- Blue-steel hardware
- Muted red for the CI scale and product readout
- Cobalt blue for the cursor hairline

The background combines a soft radial glow with a faint repeating CSS texture. The rule itself uses a separate SVG grain pattern made from tiny dots and scratches.

The working name **Duodecima** was replaced with the leaner **Radix XII**. Its title treatment was refined from a large serif with a red italic accent into a condensed technical sans-serif wordmark. `XII` now uses a restrained ice-blue accent.

Scale labels received their own technical sans-serif stack with tabular figures and consistent baselines, improving the alignment of `1`, `X`, `E`, and `10`.

### Help and documentation

Following the pattern used by the base-12 clock, we added a fixed `?` button that opens a native modal legend. The dialog briefly explains every scale, includes the dozenal digit key, supports keyboard focus and Escape, and can be dismissed with its close button or by clicking the backdrop.

The slide-rule README and repository README were updated alongside the implementation so the scale list, controls, notation, and project name remain accurate.

### Where we landed

Radix XII is now a responsive, tactile-looking, seven-scale dozenal slide rule with real logarithmic relationships, modern interaction controls, accessible help, and a visual identity of its own. What began as a 100-pixel canvas experiment ended the day as a fairly epic slide-rule concoction.
