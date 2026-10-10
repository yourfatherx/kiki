# Kiki — Design plan

## 1. The Kiki mapping system (the core rule)
Each measurable property of a sound maps to one visual property. Every mapping is backed by research on how people link senses together (Spence 2011; Marks 1974).

| Acoustic property | Visual property | Reason |
|---|---|---|
| **Sharpness** (attack time, spectral centroid) | **Spikiness**: number of points, spike depth, corner radius (the "Kiki index" from 0 = round to 100 = spiky) | The kiki–bouba effect itself |
| **Pitch** | **Lightness and height**. High pitch is lighter, higher and smaller | Pitch–lightness and pitch–height links are among the most reliable cross-sense pairings |
| **Loudness** | **Size, plus grain density** | Loudness–size pairing |
| **Urgency** (class tier) | **Hue temperature and saturation**: critical is hot vermilion, attention is warm amber/coral, ambient is cool and muted | Warning-colour conventions. Always paired with shape, motion, label and haptic |
| **Rhythm / repetition** | **Pulse tempo of the form**, matching the real pattern (T3, ding-dong, knock count) | The pattern becomes recognisable without reading |
| **Duration** | **How long the form persists, and its trail** | Continuous sounds linger; transients fade |
| **Direction / room** | **Where the form sits on the canvas, plus an arrow or room tag** | Spatial cue |
| **Speech** | **Kinetic type** (variable font: weight, width and softness) | Speech carries language, so its form is letters |

**Parametric generator:** every glyph is one polar "superformula" shape whose settings come from the table above. The system is generative rather than illustrated, so it can be explained and extended.

## 2. Sound Atlas: 12 classes, each with its reason

| Tier | Sound | Glyph name | Form (Kiki index) | Colour | Motion / haptic | Reason |
|---|---|---|---|---|---|---|
| Critical | Smoke / CO alarm | **Shard Burst** | 12-point star, deep spikes (95) | Vermilion | Pulses in the T3 pattern: 3 beats, then a pause | A piercing ~3kHz tone is the sharpest sound in the home. The motion copies the standard T3 alarm rhythm |
| Critical | Siren | **Sweep** | Spiky ring, spikes travel around it (85) | Red ↔ blue | Rotates in time with the wail/yelp; arrow shows direction | Pitch glide becomes rotation. Red/blue matches the light bar people already pair with sirens |
| Critical | Glass break | **Shatter** | Scattered broken shards (100) | Ice white/cyan | One burst outward | Sudden, broad, high-frequency noise. Literally fractured |
| Attention | Doorbell | **Chime Bloom** | Two rings with crisp edges (35) | Brass amber | Two ripples, high then low, with a long fade | A bell strikes sharply, then rings round. "Ding-dong" becomes two rings at two heights |
| Attention | Knock | **Taps** | Heavy rounded pebbles, one per knock (25) | Wood ochre | Count is kept; haptic taps the same number | A dull, low-pitched hit reads as heavy and blunt. The count carries meaning (a gentle knock vs pounding) |
| Attention | Your name | **Name** (kinetic type) | Type itself | Your accent colour | Name grows to fill the screen | The information is linguistic, so the form is the word |
| Attention | Baby cry | **Petal** | Petals with soft points (55) | Rose | Swells with the cry's rhythm | High-pitched and urgent but made of tones, so it sits between kiki and bouba |
| Attention | Appliance beep / whistle | **Beacon** | Small clean dots or a rising whistle spike (60) | Mint | Beeps become dots; whistles are counted | A pure tone gives a simple, exact shape. The whistle counter is for cooking |
| Ambient | Dog bark | **Jag** | Blob with a jagged edge (65) | Ochre-grey | Short bursts | Rough, sudden, mid-pitch |
| Ambient | Water running | **Flow** | Smooth ribbon (5) | Water blue | Keeps flowing | Steady, soft noise is the most bouba-like sound |
| Ambient | Music | **Orbit** | Round orbs that pulse to the beat (15) | Violet | Beat-synced | Tonal, rhythmic, pleasant |
| Ambient | Room tone / rain / traffic | **Mist** | Grain field with no edge (0) | Muted lavender-grey | Slow drift | Diffuse sound has no shape. This is the Field's background |

## 3. Visual direction (from the references)
- **Popcorn (refs 1 and 4)**:
  - grainy, misty generative textures on a soft off-white canvas
  - editorial serif headlines
  - pill segmented controls (Local / Regional / Global → **Home / Out / Sleep**)
  - grid of textured feature tiles (→ sound selection grid)
  - black primary CTA
- **AI orb (ref 2)**:
  - glassy sphere with a progress arc → **"Teach a sound / Listening…"** screens
  - large bold heading, soft grey secondary button ("Remind me" → "Ring your doorbell now")
- **Lóvi (ref 3)**:
  - friendly blurred blob character → Kiki's resting "quiet room" blob
  - glowing blurred CTA button for the main action during onboarding

## 4. Foundations
- **Canvas**: warm off-white `#F4F2EE` with film grain. Cards are `#ECEAE6` with a 28px radius. Text ink is `#141414`. Sleep mode uses a near-black `#0E0E12` canvas.
- **Tier colours**:
  - Critical: Vermilion `#FF4A1C`
  - Attention: Amber `#F5A524`, Coral `#FF7A59`, Rose `#F27BA6`, Mint `#5ED3B0`
  - Ambient: Lavender `#B9B4E8`, Water `#7FB2F0`, Violet `#9A7BF0`
  - Each colour gets a soft gradient ramp for textures
- **Type**:
  - **Fraunces** for headlines and kinetic captions. Its variable **SOFT** axis literally rounds the letters, so bouba/kiki applies to the type as well. Soft speech is drawn with SOFT=100 and sharp or shouted speech with SOFT=0 and heavier weight.
  - **Inter** for the UI.
  - The defence: the type follows the same rule as the shapes.
- **Texture recipe in Figma**: blurred ellipses with radial and angular gradients, plus layer blur, a Noise effect for grain, and the parametric glyph vector on top.
- **Grid**: iPhone 16 Pro, 393×852. 20px margins, 8pt spacing. Corner radii of 28 for cards and 999 for pills.
- **Accessibility**:
  - Every alert is coded 4 ways: shape, motion, label and haptic.
  - Text contrast meets AA.
  - Touch targets are at least 44pt.
  - Reduce Motion variants.
  - No flashing faster than 3 per second.

## 5. Components
- Status bar / Dynamic Island
- Segmented control (Home/Out/Sleep)
- Primary button (black) and glow button
- Sound tile (textured, toggle)
- Event card (glyph, label, room, time)
- Critical takeover sheet
- Caption line (speaker colour, variable type)
- Timeline row
- Glyph set (12)
- Tab bar (Field · Talk · History · Atlas)
- Permission row
- Recording orb with progress arc

## 6. Screen list (iPhone 16 Pro)

**Onboarding (8)**
1. Splash: kiki/bouba shapes morph into the wordmark.
2. "Sound you can see."
3. "Sharp sounds look sharp. Soft sounds look soft." (the rule)
4. Urgency tiers explained.
5. Permissions: mic, notifications, critical alerts, on-device privacy.
6. Pick the sounds that matter: a tile grid like Popcorn's plan grid, with Home/Out/Sleep.
7. Teach Kiki your name (recording orb).
8. Teach a sound: "Ring your doorbell now" (orb with progress arc).

**Core (10)**

9. Field, quiet: the resting blob in mist, "Listening · Home".
10. Field with a doorbell event: Chime Bloom plus an event card.
11. Critical takeover, smoke alarm: Shard Burst with "I'm safe / Call 112 / Alert contacts".
12. Out mode with a siren: Sweep plus a direction arrow.
13. Talk: kinetic conversation captions with speaker colours.
14. Name called: the name fills the screen.
15. History: "While you were away" timeline.
16. Event detail plus "Not a doorbell?" correction.
17. Sound Atlas grid.
18. Atlas detail: "Why it looks like this", the reason shown inside the app.

**System surfaces (4)**

19. Lock screen notification and Live Activity.
20. Dynamic Island compact/expanded.
21. Widget.
22. Apple Watch alert.

**Settings (1)**

23. Modes, haptics, flash, trusted contacts, accessibility, privacy.

## 7. Figma file structure
Paymate (`K3ZNiJvWJCw9DErGj6aJ8t`) has one design-only page, laid out as:
- `Cover · PayMate`: 1920×1200, three phone mockups, wordmark, sticker
- `Board · Design principles`: direction, palette, type, 6 principle cards
- `Components & tokens` section: Lucide icons
- `Screens` section: 390×844 frames named `01 · Welcome` …, each with a `Label · …` text above

Kiki uses the same layout ideas but is not a copy. **Research stays out of Figma** (it lives in `/docs`), as it did for Paymate. The page is called `Kiki`, with:
- `Cover · Kiki`: 1920×1200. Three phones (Field, smoke takeover, Talk) on a grainy mist background, with the wordmark made of kiki and bouba shapes.
- `Board · Design principles`: the direction paragraph, the mapping rule (acoustic → visual table), palette by tier, type (Fraunces SOFT axis demo), and 6 principle cards. The principles:
  - "Sharp sounds look sharp"
  - "Urgency is never colour alone"
  - "Rhythm is the signature"
  - "Speech becomes type"
  - "Quiet is information"
  - "Nothing leaves the phone"
- `Board · Sound Atlas` (new compared with Paymate): the 12 glyphs on a kiki–bouba scale from 0 to 100, each with an acoustic note, colour, motion, haptic and its reason. **This is where each visual language is defended.**
- `Components & tokens` section: colour/type/effect variables, Lucide icons (same set as Paymate), status bar, tab dock, buttons, segmented control, sound tile, event card, caption line, timeline row, recording orb, and the glyph components.
- `Screens` sections, labelled with `Label · NN Name` like Paymate:
  - `Screens · Onboarding` (01–08)
  - `Screens · Core` (09–18)
  - `Screens · System` (19–23)
- Frames are **393×852**, the iPhone 16 Pro size, chosen because the references use Dynamic Island. Paymate used 390×844.
