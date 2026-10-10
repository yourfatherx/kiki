# Kiki: motion and prototype

## Motion principle
Motion follows the same kiki–bouba rule as form.
- **Kiki moves sharply.** It has a fast attack (spring `QUICK`, about 0.12 s up), then a short settle (`EASE_OUT`, about 0.3 s).
- **Bouba moves softly.** It breathes slowly (`EASE_IN_AND_OUT`, a 4–5 s cycle) and never snaps.
- **Rhythm is the signature.** Each sound's form pulses in the real sound's temporal pattern, and the watch taps the same pattern.
- **Safety.** No element pulses faster than 2 times per second. The WCAG 2.3.1 limit is 3 flashes per second.

All motion is built from Figma Motion manual keyframes on each screen's timeline.

| Screen | What moves | Timing |
|---|---|---|
| 01 Splash | The Kiki mark fades and springs in (`GENTLE`), then breathes (×1.035) with a 2.5° tilt. The wordmark, tagline and footnote rise in | 4 s |
| 02 Sound you can see | Glyphs drift at offset phases and the mist breathes. Headline and body rise in | 5 s |
| 03 The rule | The smoke glyph jabs 3 times while the water ribbon sways. Cards and the Kiki-index scale stagger in | 3 s |
| 04 Urgency tiers | Tier cards stagger in. Critical pulses in T3, Attention rings ding-dong, Ambient drifts | 3 s |
| 05 / 06 | Permission rows stagger in, and sound tiles pop in with a `GENTLE` spring | 1.6–1.8 s |
| 07 Teach your name | The orb breathes and "Maya" swells each time it is heard | 4 s |
| 08 Teach a sound | The orb turns so the progress arc travels. The doorbell glyph rings ding-dong twice. The live dot blinks | 4 s |
| 09 Field, quiet | The resting form breathes (×1.04), the glow swells, and the ambient music drifts and flickers. The listening dot pulses | 4 s |
| 10 Doorbell | Ding (×1.09), then dong (×1.05) 0.6 s later. Three ripples expand and fade like a bell's decay. Title and actions rise in | 2.6 s |
| 11 Smoke alarm | **T3:** three pulses 0.5 s apart, then a pause. The T3 bars light up on the beat, and the mist flares with each pulse | 2.8 s |
| 12 Siren | The spiky ring rotates 360° per wail cycle so the spikes travel. The direction wedge breathes, and the loudness bars light up left to right | 3 s |
| 13 Talk | Caption lines arrive in speaking order, each settling up and in | 2.8 s |
| 14 Name called | "Maya!" lands on a `BOUNCY` spring and the echoes push outward. The card rises in. The haptic bars blink long · short · long | 2.6 s |
| 15 History | The day's sounds settle onto the strip in time order, then rows stagger in | 2.2 s |
| 16 / 18 | The hero glyph replays its rhythm: ding-dong for the doorbell, T3 for Shard Burst | 3 / 2.8 s |
| 17 Atlas | Cells pop in staggered | 2 s |
| 19 Lock screen | The notification drops in on a spring, and the Live Activity glyphs drift | 4 s |
| 20 Dynamic Island | The critical compact glow pulses in T3, and the expanded doorbell rings | 2.8 s |
| 21 Widgets | The resting form breathes, and the last-alert doorbell rings | 4 s |
| 22 Watch | The watch itself **shakes twice** (tap · tap) in sync with the ding-dong, which shows the haptic as motion | 2.6 s |

## Prototype
Open the file in **Present** mode and pick a flow:

| Flow | Starts at | Path |
|---|---|---|
| 1 · Onboarding | 01 Splash | Auto-advances after 2.6 s, then 02 → 03 → 04 → 05 → 06 → 07 → 08 → 09. **Skip** on 02–04 jumps to 05, and back buttons go back |
| 2 · Home: the Field | 09 | The **dock** switches Field / Talk / History / Atlas. **Home/Out** toggles 09 ↔ 12. The ⚙ button opens 23 |
| 3 · From the lock screen | 19 | The notification opens 10 (doorbell) and the Live Activity opens 09 |
| 4 · From the home screen | 21 | The Kiki icon or medium widget opens 09, and the last-alert widget opens 16 |

### Demo triggers
Real sounds can't fire in a prototype, so these taps simulate events:
- **Tap the resting form (09):** the doorbell rings (10).
- **Tap the doorbell glyph (10):** the smoke alarm takes over (11). "I'm safe" returns to 09.
- **Tap Rohan's "Maya, can you pass the dal?" (13):** "Name called" opens (14).
- **10 actions:** "Not a doorbell?" opens event detail (16). History rows and the Smoke alarm Atlas cell drill into 16 and 18.

### Transitions
- Push left for drill-ins.
- Smart Animate for Field state changes.
- Dissolve for tab switches and takeovers.
- Move in from the top for entries from system surfaces.
