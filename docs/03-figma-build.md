# Kiki: Figma build

**File:** [kiki: sound you can see](https://www.figma.com/design/kFq7cmrDkUUmYZqWJHK0oA)

The file has a single page, `Kiki`, laid out like Paymate's: cover, boards, screen sections, then components. It contains design only. The research lives in [`01-product-plan.md`](01-product-plan.md) and [`02-design-plan.md`](02-design-plan.md).

| Area | What's there |
|---|---|
| `Cover · Kiki` | 1920×1200. Wordmark with the Kiki mark as a lockup, tagline, three phone mockups (doorbell, smoke alarm, Talk), the kiki→bouba glyph strip, and a sticker with the mark |
| `Board · Design principles` | Direction, palette by urgency tier (bound to variables), the Fraunces SOFT-axis type specimen, and 6 principles |
| `Board · Sound Atlas` | The kiki–bouba scale (0–100), 8 acoustic-to-visual mapping rules, and 12 sound-class cards. Each card covers what it sounds like, how it looks, colour, and motion/haptic. This is where each visual language is defended |
| `Screens · Onboarding` | 01 Splash · 02 Sound you can see · 03 The rule · 04 Urgency tiers · 05 Permissions · 06 Pick your sounds · 07 Teach your name · 08 Teach a sound |
| `Screens · Core` | 09 Field (quiet) · 10 Field (doorbell) · 11 Critical: smoke alarm · 12 Out: siren · 13 Talk: kinetic captions · 14 Name called · 15 History · 16 Event detail · 17 Sound Atlas · 18 Atlas detail |
| `Screens · System` | 19 Lock screen + Live Activity · 20 Dynamic Island · 21 Home-screen widgets · 22 Apple Watch + haptic rhythms · 23 Settings |
| `Components & tokens` | 12 parametric sound glyphs, 24 Lucide icons, status bar, home indicator, buttons (primary/secondary/glow/text), toggle, segmented mode control, tab dock, event card, sound tile, timeline row, recording orb, permission row, atlas cell, app icon |

## Foundations
- **Variables:**
  - `kiki/color` has 22 tokens with **Day** and **Sleep** modes. Screens 11, 19 and 20 switch to Sleep through an explicit mode on the frame.
  - `kiki/space` holds spacing and radius tokens.
- **Text styles:** Display, Title, Body, Label and Caps. Headlines use Fraunces Light (wght 300) at `SOFT 100`, in charcoal `#2B2926`. Expressive moments are capped at about wght 520. UI text uses Inter Regular and Medium.
- **Effect styles:** Grain (noise), Soft blur, Card elevation.
- **Frames:** 393×852 (iPhone 16 Pro).

## How the glyphs are made
Each glyph is generated from a polar or parametric path, not drawn by hand:
- star polygons for the kiki end of the scale
- a rose curve for Petal
- jittered polygons for Jag
- a sine ribbon for Flow

Each glyph then gets a vertical gradient (lighter = higher pitch), an inner highlight and a noise grain, and sits on a blurred radial aura. A component's description records its Kiki index and why it looks the way it does.

## Logo: "Kiki, the listener"
- **Component:** `Logo / Mark`, with the variants **Dusk violet** (primary), **Deep rose** and **Ocean**.
- **Board:** `Board · Logo`, showing the primary mark, Sleep mode, the lockup, small sizes, colourways and anatomy.
- **Concept:** pointed ears (kiki) on a soft round body (bouba), so the mark is the design rule itself.
- **Silhouette:** traced from the reference image on its solid core (luminance < 30), not on the blurred fringe. It was then resampled every 6 px and smoothed, with the ear tips and the ear junction pinned. The junction is a shallow, soft angle, not a cut-in V.
- **Shading:** measured from the reference's interior luminance.
  - Light comes from the top-left.
  - A soft lit band runs from the ear junction diagonally down across the left cheek, with a faint crease ridge inside it.
  - Deep shadow sits in the right cheek and the right ear.
  - All shading layers are masked to the body.
- **Edges:** a blurred same-hue fringe (two layers) lets the colour dissolve into the background. A chromatic rim (cyan, blue and magenta offset copies, faded in toward the bottom) sits on the lower-right edge only.
- **Eyes:** white dots at the reference's measured centres and radius.
- **Splash (01):** the mark sits above the wordmark. It fades and springs in, then breathes (×1.035) with a 2.5° tilt over a 4 s cycle.
