# Kiki — Product plan

## Why Kiki
Kiki turns ambient sound into something you can see, for deaf and hard-of-hearing (DHH) people. The design rule comes from the **kiki–bouba effect**. In Köhler's 1929 "takete/maluma" study, and again in Ramachandran & Hubbard's 2001 replication, people matched spiky shapes to sharp sounds and round shapes to soft ones roughly 95% of the time. In Kiki: **sharp sound → spiky form, soft sound → round form.** Each sound class gets its own visual language, and each one has a written reason.

## Problem
- Existing tools, such as iOS Sound Recognition and Android Sound Notifications, turn sound into a **text banner**: "Doorbell". That loses what makes sound useful:
  - urgency
  - loudness and distance
  - rhythm (how many knocks, whether it's still ringing)
  - tone of voice
  - ambient awareness ("the house is quiet" is information too)
- Text has to be read. Shape, colour and motion are taken in at a glance, before reading, from the corner of the eye. That suits a phone on a table across the room.
- Speech captions are flat. Shouting looks the same as whispering, and your own name looks like any other word.

## Audience
**Primary: DHH adults living independently.** The WHO estimates about 430M people with disabling hearing loss, and about 1.5B with some hearing loss.

| Persona | Profile | Main pain | Kiki moment |
|---|---|---|---|
| **Maya, 28** | Deaf from birth, signs (ISL/ASL), lives alone, works remotely | Misses deliveries at the door. Worries about the smoke alarm at night | Doorbell bloom on the phone and watch. Smoke alarm takeover plus a contact alert |
| **Rohan, 66** | Late-deafened (age-related), uses hearing aids, remembers what things sound like | Misses his name being called at the clinic or pharmacy. Lost in group talk | Name detection with kinetic type. Conversation captions with tone |
| **Aisha, 34** | Hard of hearing, new parent | Baby crying in the next room. Kitchen appliance beeps | Baby-cry petal with a room tag. Count of pressure-cooker whistles |

**Secondary:**
- CODA families and caregivers, who get escalation alerts.
- People who can't hear temporarily or by circumstance: noise-cancelling headphones, loud workplaces, people with ear infections.

## Jobs to be done
- "When something needs me, like the door, an alarm or my name, let me notice it **without staring at my phone**."
- "When I come back, tell me **what I missed**."
- "In a conversation, show me **how** something was said, not just what."
- "Never let me miss a **life-safety** sound, even when I'm asleep."

## Use cases (scenario set)
1. Delivery at the door while working → doorbell alert on the phone and a haptic on the watch.
2. Smoke alarm at 3am → full-screen takeover, torch strobe kept under the safe limit, watch haptic, trusted contact told if nobody acknowledges within 60s.
3. Walking outdoors with a siren approaching → spiky red/blue sweep with a direction arrow.
4. Clinic waiting room, "Rohan Sharma?" → name detected, the name appears in large kinetic type.
5. Kitchen: the pressure cooker gives its 3rd whistle → a counter shows "3 whistles". This is an India-specific detail that makes the case study memorable.
6. Baby cries in the nursery while the parent showers → a room-tagged alert from a spare phone used as a "room listener".
7. Coming home → a "While you were away" timeline of the day's sounds.
8. Dinner with family → conversation mode, where type weight and softness carry tone and each speaker has a colour.

## Feature set (MoSCoW)
**Must**
- **Field**, the live canvas on the home screen. It draws the room's soundscape as a generative texture.
- Sound recognition for 12 classes, in 3 urgency tiers. Each class has its own visual, haptic and rhythm.
- Tiered alerts:
  - Critical: full-screen takeover
  - Attention: card plus haptic
  - Ambient: shown on the canvas only
- **Kinetic captions** for speech. Loudness drives weight and size. Calm vs sharp tone drives type softness. Pitch drives baseline. Your own name is highlighted.
- **Name detection** ("Teach Kiki your name").
- Modes: Home / Out / Sleep. These change which sounds alert you.
- History timeline ("What did I miss?").
- Privacy: processing happens on the device, and no audio is stored.

**Should**
- **Teach a sound**: record your own doorbell, microwave or cooker.
- Room listeners: turn an old phone into a listener for one room, which tags each alert with its room.
- Critical escalation to trusted contacts.
- Feedback: "Not a doorbell?" to correct mistakes.
- Lock screen, Live Activity / Dynamic Island, widget, Apple Watch alert.

**Could**
- Sound Atlas, a page explaining "why it looks like this" for each sound.
- Smart-light flash hooks.
- Weekly sound digest.

**Won't (v1)**
- Two-way calling
- Sign-language translation

## Success metrics (for the case study)
- **Glance recognition**: users name the sound class from its form alone in under 1 second, after a 5-minute familiarisation.
- **Zero missed critical events** in a test week.
- False-alarm annoyance score.
- SUS score of 80 or more.
- **Kiki–bouba validation test** with DHH participants. Show the glyph, ask "sharp or soft?" The effect is partly tied to how words are spoken, so we test the mapping with Deaf users instead of assuming it holds. This makes for an honest, strong section in the case study.

## Edge cases to design for
- Several sounds at once → priority stacking. Critical replaces everything, and the others collapse into a stack.
- Wrong detection → one-tap correction.
- Phone in a pocket → watch or haptic only.
- Reduce Motion → static glyphs.
- Colour-blind users → urgency is never shown by colour alone.
- Photosensitivity → no flashing faster than 3 per second (WCAG 2.3.1).
- Battery saver listening.
- Low-confidence detections → shown as "Possibly…".
