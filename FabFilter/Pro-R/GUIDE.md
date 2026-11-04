# FabFilter Pro-R 2: Essential Mixing Guide and Cheat Sheet

A clear, beginner friendly mixing guide to **FabFilter Pro-R 2**. Strips away confusing audio school math to give you a clear understanding of the dual curves, a practical filter and band adjustment guide, a knob by knob cheat sheet matching the exact plugin interface sequence from left to right, easy sound examples, the three reverb engines, and an instant IF/THEN mixing decision engine.

---

## Table of Contents
1. [1. The Core Concept: Blue vs. Yellow Curve](#1-the-core-concept-blue-vs-yellow-curve)
2. [2. Curve Filter Guide: Bands, Shapes, Gains & Q Factors](#2-curve-filter-guide-bands-shapes-gains-q-factors)
   - [The Golden Rule of Q Factor (Filter Width)](#the-golden-rule-of-q-factor-filter-width)
   - [Blue Curve: Decay Rate EQ (Time in Seconds)](#blue-curve-decay-rate-eq-time-in-seconds)
   - [Yellow Curve: Post EQ (Volume in Decibels)](#yellow-curve-post-eq-volume-in-decibels)
3. [3. Quick Reference Knob Sequence & Sweet Spots](#3-quick-reference-knob-sequence-sweet-spots)
4. [4. Knob by Knob Deep Dive: Controls & Sound Examples](#4-knob-by-knob-deep-dive-controls-sound-examples)
   - [1. Predelay (0 ms to 500 ms)](#1-predelay-0-ms-to-500-ms)
   - [2. Character (0% to 100%)](#2-character-0-to-100)
   - [3. Thickness (-100% to +100%)](#3-thickness--100-to-100)
   - [4. Distance (0% to 100%)](#4-distance-0-to-100)
   - [5. Space (0.20 s to 10.00 s)](#5-space-020-s-to-1000-s)
   - [6. Decay Rate (25% to 400%)](#6-decay-rate-25-to-400)
   - [7. Brightness (-100% to +100%)](#7-brightness--100-to-100)
   - [8. Auto Gate (0 ms to 1000 ms)](#8-auto-gate-0-ms-to-1000-ms)
   - [9. Width (0% to 120%)](#9-width-0-to-120)
   - [10. Ducking (0% to 100%)](#10-ducking-0-to-100)
   - [11. Freeze (Infinite Sustain)](#11-freeze-infinite-sustain)
   - [12. Mix (0% to 100%)](#12-mix-0-to-100)
5. [5. The Three Reverb Engines](#5-the-three-reverb-engines)
6. [6. IF/THEN Mixing Decisions](#6-ifthen-mixing-decisions)
   - [Low End & Bass Cleanup](#low-end-bass-cleanup)
   - [Midrange & Vocal Clarity](#midrange-vocal-clarity)
   - [Highs, Sibilance & Air Polish](#highs-sibilance-air-polish)
   - [Dynamics & Stereo Placement](#dynamics-stereo-placement)
7. [7. The 10 Second Solo Diagnostic Workflow](#7-the-10-second-solo-diagnostic-workflow)
8. [8. Pro-R 2 Master Keyboard Shortcuts (Windows vs. macOS)](#8-pro-r-2-master-keyboard-shortcuts-windows-vs-macos)

---

## 1. The Core Concept: Blue vs. Yellow Curve

The secret to clean mixes in Pro-R 2 is realizing that the two colored curves do two completely different jobs:

- **The Yellow Line (Post EQ) = A Normal Equalizer (Loudness in Decibels):** It is literally a standard volume equalizer sitting right at the output of the reverb. Its main job in a mix is cleaning your audio: removing heavy bass rumble, scooping out muddy low mid boxiness, and boosting or shaping high frequencies so the reverb sits cleanly behind your dry tracks. When you raise or lower the yellow line, you are simply turning the volume up or down on that frequency inside the echo.
- **The Blue Line (Decay Rate EQ) = A Time Equalizer (Lifespan in Seconds):** It does not change loudness. It controls how many seconds each frequency survives in the room before dying out.

```
┌─────────────────────────────────────────────────────────────────────────┐
│ 🔵 BLUE CURVE = THE STOPWATCH (Decay Rate EQ)                           │
│ "How many SECONDS does each frequency hang in the air before dying?"    │
│ • Controls TIME, not initial loudness.                                  │
│ • Pulling 80 Hz down tells deep bass: "Fade away in 0.2 seconds!"       │
│ • Lifting 5 kHz tells airy highs: "Ring out smoothly for 4 seconds!"    │
│ • Does NOT change the volume of the initial hit.                        │
└─────────────────────────────────────────────────────────────────────────┘
                                     │
                                     ▼ (reverb tail is generated)
┌─────────────────────────────────────────────────────────────────────────┐
│ 🟡 YELLOW CURVE = THE VOLUME SLIDER (Post EQ)                           │
│ "How LOUD or QUIET is each frequency inside the echo itself?"           │
│ • Standard frequency equalizer (-24 dB to +24 dB).                      │
│ • Use this to filter out sub mud or soften piercing sibilance.          │
└─────────────────────────────────────────────────────────────────────────┘
```

> [!NOTE]
> **The Golden Summary:** The **Yellow line** decides how **loud** each tone is inside the echo, while the **Blue line** decides how many **seconds** each tone hangs in the air before dying out.

> [!WARNING]
> **The Analyzer Trap:** Never boost the Blue Curve just because you see energy on the real time analyzer! If your track has a heavy 808 or kick at 80 Hz, boosting the Blue Curve there forces the sub bass to ring out for seconds, creating a muddy mess. Pull the Blue Curve **down** in the low end so bass reflections vanish immediately.

---

## 2. Curve Filter Guide: Bands, Shapes, Gains & Q Factors

FabFilter Pro-R 2 allows **up to 6 bands (points)** on each curve (6 points for Decay Rate EQ and 6 points for Post EQ). However, professional mixers rarely max them out: **3 to 4 bands** is the sweet spot. Real rooms absorb sound across broad musical octaves, so using 3 to 4 gentle bands mirrors natural acoustics and keeps your sound completely transparent.

### The Golden Rule of Q Factor (Filter Width)
- **Always use a wide Q factor between 0.4 and 0.7.**
- **The Tea Kettle Trap:** Never boost decay with a narrow, sharp needle peak (high Q). Sharp spikes force internal delay lines to loop on a single pitch, producing an annoying metallic whistle like a boiling tea kettle. Broad curves keep the tail smooth and musical.

---

### Blue Curve: Decay Rate EQ (Time in Seconds)
Controls how many seconds each frequency zone hangs in the air relative to the main Space dial:

| Band | Role | Filter Shape | Frequency | Decay Setting | Q Factor | How to Adjust |
| :---: | :--- | :---: | :---: | :---: | :---: | :--- |
| **1** | **Sub and Bass** | Low Shelf or Bell | `60 – 100 Hz` | `20% to 40%` *(fast)*<br>`100% to 125%` *(warm)* | `0.5 – 0.7` | Pull down for fast trap and modern 808s so kick drums punch clean; lift slightly for slow acoustic ballads to give the room an acoustic floor. |
| **2** | **Midrange Boxiness** | Bell | `350 – 500 Hz` | `70% to 80%` *(dip down)* | `0.5 – 0.7` | Scoop down to cut decay by 20% to 30%. This eliminates hollow cardboard box resonance without thinning your dry vocal or guitar tone. |
| **3** | **Melodic Presence** | Bell | `1.5 – 3 kHz` | `125% to 145%` *(lift up)* | `0.4 – 0.6` | Boost up where human ears are most sensitive. Extends tail sustain behind flute leads, guitar solos, and pop vocal diction. |
| **4** | **Treble Air** | High Shelf or Bell | `8 – 12 kHz` | `60% to 80%` *(natural air)*<br>`115% to 130%` *(modern gloss)* | `0.5 – 0.7` | Pull down to replicate natural room absorption and eliminate digital sizzle; lift gently for airy commercial pop sheen. |

---

### Yellow Curve: Post EQ (Volume in Decibels)
Controls the actual volume level of each frequency inside the reverb sound itself.

> [!IMPORTANT]
> **The Primary Mixing Purpose of Post EQ (Audio Cleanup & High Polish):**
> In audio mixing (the core foundation of the famous Abbey Road reverb technique), the **Yellow Post EQ** is primarily used as an audio cleaning tool rather than a color effect. Because reverb reflections continuously bounce and multiply acoustic energy, a reverb tail left without EQ will quickly drown your mix in heavy clutter. The three main tasks of Post EQ are:
> 1. **Removing Heavy Bass:** Cutting deep sub bass and low frequencies below 80 to 120 Hz so kick drums, 808s, and basslines retain punch and mix headroom without triggering mud.
> 2. **Cleaning Muddy Frequencies:** Scooping out low mid clutter between 300 and 600 Hz where vocal resonance, acoustic guitar bodies, and snare rings collide into a boxy mess.
> 3. **Boosting & Shaping High Frequencies:** Gently lifting presence (2 to 5 kHz) and smooth air (8 to 12 kHz) to give the reverb tail an expensive, glossy halo that lets lead melodies cut through without masking the dry source.

| Band  | Role                |      Filter Shape      |   Frequency    |            Gain Setting            |             Q or Slope              | How to Adjust                                                                                               |
| :---: | :------------------ | :--------------------: | :------------: | :--------------------------------: | :---------------------------------: | :---------------------------------------------------------------------------------------------------------- |
| **1** | **Sub & Low End**   |   Low Shelf or Low Cut | `80 – 120 Hz`  | `-6 dB to -10 dB` *(tight / clean)*<br>`-2 dB to -4 dB` *(warm / deep)* | `Q = 0.3 – 0.7`<br>*(or 12 dB/oct for Low Cut)* | Pull down to eliminate sub rumble and keep drums and bass punchy; use a lighter cut when you want rich acoustic body and weight on ballads. |
| **2** | **Low Mids & Mud**  |          Bell          | `300 – 600 Hz` | `-2 dB to -4 dB` *(mud scoop)*<br>`+2 dB to +4 dB` *(acoustic body)* |             `0.5 – 0.8`             | Dip down at 500 Hz to prevent hollow boxy clutter between rhythm and vocals; or boost around 270 Hz to add warm wooden resonance to acoustic guitars and breathy vocals. |
| **3** | **Lead & Vocal Presence** | Bell or High Shelf | `1.5 – 3 kHz` | `+2 dB to +5 dB` *(vocal forward)*<br>`+6 dB to +10 dB` *(bold presence)* |             `0.4 – 0.7`             | Lift moderately to give vocals and instruments clear projection on the soundstage; push higher for bold, singing lead presence that cuts right through. |
| **4** | **Treble & Air**    | High Cut or High Shelf | `10 – 14 kHz`  | `-2 dB to -6 dB` *(smooth / velvety)*<br>`+1 dB to +3 dB` *(glossy air)* | `Q = 0.5 – 0.7`<br>*(or 12 dB/oct for High Cut)* | Roll off or filter with High Cut to tame harsh vocal sibilance ("S" and "T" sounds) and splashy cymbals; lift gently with High Shelf for expensive radio sheen. |

---

### Curve & Band Modifiers (Windows vs. macOS)
- **Spawn Band:** Click and drag directly on either the **Blue Curve** (Decay Rate EQ) or **Yellow Curve** (Post EQ).
- **Adjust Band Q (Bandwidth):** Scroll mouse wheel over the dot, or hold **`Ctrl`** (Windows) / **`Command` (`⌘`)** (macOS) and drag vertically.
- **Constrain Movement (Axis Lock):** Hold **`Alt`** (Windows) / **`Option` (`⌥`)** (macOS) while dragging to lock movement strictly to horizontal (frequency) or vertical (gain/decay).
- **Fine Adjustment:** Hold **`Shift`** while dragging (Windows & macOS).
- **Toggle Band Bypass:** Hold **`Alt`** (Windows) / **`Option` (`⌥`)** (macOS) and click a band dot.
- **Reset to Default:** Hold **`Ctrl`** (Windows) / **`Command` (`⌘`)** (macOS) and click a dot or knob.
- **Delete Band:** Select the dot and press `Delete` or `Backspace`.

---

## 3. Quick Reference Knob Sequence & Sweet Spots

The controls below follow the **exact left to right physical layout** across the Pro-R 2 interface:

| # | Knob / Control | Interface Range | What It Does | Sweet Spot Values |
| :---: | :--- | :---: | :--- | :--- |
| **1** | **Predelay** | `0 – 500 ms` | The split second pause before the echo begins | Drums: `0–15 ms`<br>Guitars: `15–35 ms`<br>Lead Vocals: `30–70 ms` |
| **2** | **Character** | `0% – 100%` | Wall texture and chorus swirl | Acoustic/Drums: `0%–20%`<br>Lead Vocals: `25%–45%`<br>Synths/Pads: `50%–80%` |
| **3** | **Thickness** | `-100% to +100%` | Reflection density: light mist vs. dense soup | Busy Beats: `-20% to +20%`<br>Lead Vocals: `+20% to +45%`<br>Slow Ballads: `+50% to +80%` |
| **4** | **Distance** | `0% – 100%` | Performer distance from front to back of room | Lead Vocals: `10%–25%`<br>Rhythm Guitars: `30%–50%`<br>Backing Vocals: `60%–85%` |
| **5** | **Space** | `0.20 s – 10.00 s` | Room size model and baseline decay length | Drums: `0.6s–1.2s`<br>Lead Vocals: `1.6s–2.4s`<br>Ambient/Ballads: `3.0s–6.0s+` |
| **6** | **Decay Rate** | `25% – 400%` | Multiplier ring scaling decay time across the room | Default: `100%`<br>Tight Mixes: `80%–95%`<br>Automated Drops: `150%–300%` |
| **7** | **Brightness** | `-100% to +100%` | Wall absorption: warm wood vs. shiny tile | Warm Mixes: `-25% to -5%`<br>Drums/Snares: `-10% to +10%`<br>Pop Vocals: `+5% to +20%` |
| **8** | **Auto Gate** | `0 – 1000 ms` | 80s dynamic tail cutoff for punchy hits | Snares/Toms: `ON (120–250 ms)`<br>Vocals & Pads: `OFF` |
| **9** | **Width** | `0% – 120%` | Left to right soundstaging and stereo panoramic spread | Lead Vocals: `85%–100%`<br>Backing Vocals/Pads: `105%–120%`<br>Mono Bass: `0%` |
| **10** | **Ducking** | `0% – 100%` | Automatically lowers reverb while singer sings | Lead Vocals: `25%–45%`<br>Lead Guitars/Synths: `20%–35%`<br>Master Bus: `0%` |
| **11** | **Freeze** | On / Off | Infinite sustain holding current tail indefinitely | Creative transitions and ambient drone pads |
| **12** | **Mix** *(+ Lock)* | `0% – 100%` | Wet/Dry balance with global preset lock | Aux Send Bus: **Lock at 100%**<br>Direct Insert: `10%–25%` |

---

## 4. Knob by Knob Deep Dive: Controls & Sound Examples

### 1. Predelay (0 ms to 500 ms)
- **What It Does:** The courtesy pause before the echo begins. Think of shouting across an open canyon: your voice shouts first, and a split second later, the distant canyon walls echo back.
- **Sound Example:** 
  - At `0 ms`, the echo starts instantly over every consonant. The singer's mouth feels smeared with reverb, like singing underwater.
  - At `50 ms`, the singer's upfront syllables hit crisp, dry, and right in your face; then, a warm echo cloud blooms in the pause between words.
- **Sweet Spots:**
  - *Drums & Snares:* `0–15 ms` (keeps snare punch tight without creating a sloppy double flam).
  - *Guitars & Keys:* `15–35 ms` (retains pick clarity before the acoustic body rings).
  - *Lead Vocals:* `30–70 ms` (essential for upfront clarity and lyrical intelligibility).
  - *Rhythmic Sync:* Click the note icon above the knob to lock predelay to `1/32` or `1/64` note of your song tempo.

### 2. Character (0% to 100%)
- **What It Does:** Controls wall texture and diffusion swirl. At `0%`, the walls are smooth, stiff acoustic panels (clean, steady, and uncolored). As you turn it toward `100%`, reflections begin to move, shimmer, and swirl with rich chorus modulation (inspired by vintage 1980s Lexicon hardware).
- **Sound Example:**
  - At `0%–20%`, an acoustic guitar or classical piano rings out completely pure with zero pitch wavering.
  - At `60%–80%`, a pop vocal or synth pad turns into a floating, shimmering, dreamy cloud that sounds expensive and lush.
- **Sweet Spots:**
  - *Acoustic Instruments & Drums:* `0%–20%` (preserves pitch accuracy and clean decay).
  - *Pop & R&B Lead Vocals:* `25%–45%` (silky sheen without detuning the singer).
  - *Synths, Pads & Ambient Guitars:* `50%–80%` (dreamy, swirling chorus wash).

### 3. Thickness (-100% to +100%)
- **What It Does:** Controls reflection density (think light mist vs. thick soup). Turning left into negative values makes reflections sparse and transparent. Turning right into positive values packs reflections tightly together and adds subtle harmonic saturation and body.
- **Sound Example:**
  - In a fast, crowded 100-track beat, low or negative thickness (`-20% to +20%`) keeps the reverb airy and transparent so it never muddies the kick or bass.
  - On a slow, emotional ballad with just a singer and piano, turn thickness up to `+50% to +80%` to fill the empty room with rich, dense acoustic warmth.
- **Sweet Spots:**
  - *Fast Beats & Busy Drums:* `-20% to +20%` (clears clutter and keeps mix transparent).
  - *Lead Vocals in Full Mix:* `+20% to +45%` (balanced body without swallowing other instruments).
  - *Slow Ballads & Solo Instruments:* `+50% to +80%` (rich, heavy, expensive density).

### 4. Distance (0% to 100%)
- **What It Does:** Sets perceived front to back stage depth, defining where the musician stands relative to the listener.
- **Sound Example:**
  - At `10%`, the singer is standing 2 inches from the mic, singing directly into your ear.
  - At `80%`, the singer is standing 60 feet away at the very back wall of a cathedral while you listen from the front row.
- **Sweet Spots:**
  - *Lead Vocals & Snare:* `10%–25%` (keeps the lead upfront and in the listener's face).
  - *Rhythm Guitars & Keys:* `30%–50%` (comfortable natural stage depth).
  - *Backing Vocals, Pads & Strings:* `60%–85%` (pushes background layers behind leads for 3D depth).

### 5. Space (0.20 s to 10.00 s)
- **What It Does:** Sets the physical room size and baseline decay length. Pro-R 2 automatically blends room geometry, wall shapes, and decay time simultaneously. Click the room icons around the knob to jump from a small vocal booth all the way to an enormous cathedral.
- **Sound Example:**
  - At `0.6s`, it sounds like clapping in a tight closet (dry, boxy acoustic glue).
  - At `2.0s`, it sounds like a spacious studio live room.
  - At `6.0s`, it sounds like a cavernous gothic church with notes hanging in the air for ages.
- **Sweet Spots:**
  - *Tight Drum Rooms & Percussion:* `0.6s–1.2s` (adds glue without washing out groove).
  - *Pop & Rap Lead Vocals:* `1.6s–2.4s` (commercial radio standard depth).
  - *Ballads, Pianos & Ambient Space:* `3.0s–6.0s+` (grand emotional scale).

### 6. Decay Rate (25% to 400%)
- **What It Does:** The master time multiplier dial located on the upper right ring of the Space knob. It multiplies the decay time without changing the physical room dimensions. *(Note: Pro-R 2 expanded this range to 400%).*
- **Sound Example:**
  - You love the intimate sound of a wooden recording studio (`Space = 1.6s`), but you want a special breakdown where the echo suddenly lingers twice as long, turn Decay Rate up to `200%` (`3.2s` tail) without turning the room into a giant cathedral!
- **Sweet Spots:**
  - *Default / General Mixing:* Keep at `100%` (let the Space knob set the core room time).
  - *Tightening Up Spaces:* `80%–95%` (shaves off excess tail length).
  - *Automated Builds & Drops:* Automate from `100%` up to `200%–350%` right before a beat drops.

### 7. Brightness (-100% to +100%)
- **What It Does:** Controls high frequency absorption and wall reflectivity. Turning left into negative values simulates thick velvet curtains, carpet, and soft wood that soak up high treble (dark and warm). Turning right simulates shiny bathroom tiles, polished marble, and steel plates that reflect crisp, sizzling treble.
- **Sound Example:**
  - If your vocalist's microphone has harsh, sharp "S" and "T" sounds that hurt your ears when echoed, turn Brightness down to `-20% to -10%` to soften the sizzle.
  - If a synth or vocal sounds dull and submerged, turn it to `+10% to +20%` for an instant glossy radio sheen.
- **Sweet Spots:**
  - *Warm, Natural Mixes (Rock, Folk, Jazz):* `-25% to -5%` (avoids abrasive high end buildup).
  - *Drums & Snares:* `-10% to +10%` (retains snappy crack without harsh splash).
  - *Modern Pop & EDM Vocal Gloss:* `+5% to +20%` (adds expensive high end air).

### 8. Auto Gate (0 ms to 1000 ms)
- **What It Does:** Delivers the classic 1980s Phil Collins drum explosion. When a drum hits, the gate snaps open to release a huge blast of room reverb, then instantly slams shut into dead silence. Pro-R 2 automatically calculates the threshold for you.
- **Sound Example:**
  - On a snare drum, you get a massive crack and burst that suddenly cuts off like a knife, leaving complete silence for the kick drum and bass to hit cleanly without any muddy spillover.
- **Sweet Spots:**
  - *Punchy Snares & Toms:* Auto Gate `ON`, Hold Time = `120 ms – 250 ms` (or tempo synced to `1/16` or `1/8` note).
  - *Rhythmic Synth Stutters:* Tempo synced `1/16` note.
  - *Vocals & Ambient Pads:* Keep `OFF` (allows natural tail decay).

### 9. Width (0% to 120%)
- **What It Does:** Controls left to right soundstaging and stereo panoramic spread across speakers or headphones. Think of it like acoustic soundstaging: `0%` collapses the reverb into a narrow mono center column, `100%` delivers a natural, true stereo soundstage, and `120%` uses psychoacoustic widening to stretch the room far beyond your physical speakers or headphones. *(Pair with Distance: Distance handles front to back depth, while Width handles left to right soundstaging).*
- **Sound Example:**
  - At `90%`, a lead vocal reverb sits focused in the center of the soundstage, ensuring the vocal sounds solid on phone speakers.
  - At `120%`, background harmonies and synth pads spread to the ultra wide outer edges of the soundstage, carving out a wide open hole right down the middle for the lead vocal and kick drum!
- **Sweet Spots:**
  - *Lead Vocals & Center Snares:* `85%–100%` (focused center soundstage with great mono compatibility).
  - *Backing Vocals, Pianos, Pads & FX:* `105%–120%` (wraps around the wide soundstage; clears the center).
  - *Bass & Sub Frequencies:* Always filter bass out with Post EQ or keep mono (`0%`).

### 10. Ducking (0% to 100%)
- **What It Does:** Automatically dips reverb volume while the primary sound is active, keeping vocals intelligible. The split second the singer pauses to take a breath, the reverb blossoms up to fill the silence.
- **Sound Example:**
  - On a fast rap verse, ducking at `30%` keeps every fast word punchy and bone dry. The moment the verse finishes, a gorgeous, lush reverb tail blooms out into the chorus without touching a volume fader.
- **Sweet Spots:**
  - *Lead Vocals (Pop, Rap, R&B):* `25%–45%` (automatic vocal clarity and pocketing).
  - *Lead Guitars & Synth Solos:* `20%–35%` (clears fast runs, blooms on sustained end notes).
  - *Drum Bus or Master Mix:* Keep at `0%` (ducking on full mixes creates weird pumping).

### 11. Freeze (Infinite Sustain)
- **What It Does:** Instantly locks and holds the current reverberation buffer indefinitely. Click once to latch on or off, or click and hold for momentary bursts.
- **Sound Example:**
  - Hit Freeze on the final word of a vocal chorus or a piano chord, and it instantly transforms into an endless, dreamy ambient synthesizer pad for the song's breakdown.
- **Sweet Spots:**
  - Automate on bridge sections, song transitions, or dramatic ambient drops.

### 12. Mix (0% to 100%)
- **What It Does:** Blends the raw dry input with the wet reverb tail. The golden padlock icon below the knob locks the mix ratio so browsing presets never alters your track levels.
- **Sound Example:**
  - If you put Pro-R 2 on an Aux/Send bus track, lock it at `100% Wet` so your channel send fader controls how deep the space is. If you insert Pro-R 2 directly on a track, set it to `10% to 25%`.
- **Sweet Spots:**
  - *Aux Send / Return Bus:* **Lock at 100% Wet**.
  - *Direct Insert (Channel Strip):* `10%–25%` for subtle acoustic depth; `30%–50%` for washed out atmospheric effects.

---

## 5. The Three Reverb Engines

Selected via the style dropdown located directly above Character and Thickness:

- **Modern:** Clean, transparent, and ultra wide. Free of vintage hiss or coloration. Ideal for modern pop, rap, EDM, and pristine lead vocals.
- **Vintage:** Warm, gritty, and dark with musical chorus swirl inspired by classic 1980s studio hardware (Lexicon 224/480). Great for rock guitars, synthwave, and drums.
- **Plate:** Immediate, dense metallic sizzle with zero room bounce. Cuts through thick walls of guitars and synths; excellent on snare drums and upfront vocals.
- **IR Import:** Drag and drop any `.wav` impulse response directly onto Pro-R 2. The engine analyzes the space and turns it into fully adjustable Blue and Yellow curves.

---

## 6. IF/THEN Mixing Decisions

### Low End & Bass Cleanup
- **IF the mix becomes boomy or muddy:**  
  → Pull down the **Blue Curve at 80–120 Hz to 15–30%** (Q = 0.8–1.2). Low echoes die in under 0.3s, keeping 808s and kick drums punchy and dry.
- **IF sub bass rumbles under 50 Hz:**  
  → Set the **Yellow Post EQ Low Shelf (or Low Cut) to 80–120 Hz** with a -6 dB to -10 dB cut to eliminate unnecessary sub rumble from eating headroom.
- **IF the room feels thin or hollow with no floor:**  
  → Gently nudge the **Blue Curve at 50–80 Hz up to 110–125%** with a wide bell (Q = 0.4–0.6) for a grounded acoustic weight.

### Midrange & Vocal Clarity
- **IF vocals sound honky or like they're inside a cardboard box:**  
  → Scoop the **Blue Curve at 300–500 Hz down to 70–80%** (Q = 0.6) to clear boxy resonance.
- **IF the lead vocal gets buried or pushed too far back:**  
  → Increase **Predelay to 40–70 ms** so the upfront syllables punch first, and lower **Distance to 20–30%**.
- **IF the tail feels thin, cold, or sterile:**  
  → Lift the **Blue Curve at 650–850 Hz to 120–135%** (Q = 0.5) to capture the natural chest warmth of the vocal.

### Highs, Sibilance & Air Polish
- **IF 'S' and 'T' sounds create harsh, piercing sizzle:**  
  → Dip the **Blue Curve at 2.5–4 kHz down to 80–90%**. Sibilant echoes decay quickly instead of smearing.
- **IF the reverb whistles like a tea kettle:**  
  → Your Blue Curve node is too narrow! Widen your bandwidth by setting **Q to 0.3–0.6**. Never boost decay with narrow spikes.
- **IF vocals lack glossy, expensive radio air:**  
  → Boost the **Blue Curve at 6–9 kHz to 130–145%** (broad Q = 0.5) and open the **Yellow Post EQ High Cut out to 15 kHz**.

### Dynamics & Stereo Placement
- **IF words get blurred during fast phrases:**  
  → Turn up **Ducking to 25–40%**. The reverb clears out while the artist sings, then blooms in breaths and pauses.
- **IF stereo reverb loses punch on phone speakers (mono):**  
  → Keep **Width at 85–100%** and ensure bass decay below 100 Hz is pulled down below 25%.

---

## 7. The 10 Second Solo Diagnostic Workflow

Never set reverb purely with your eyes. Use this 3-step ear test:

1. **Solo the Reverb Aux Track** (or set Mix to 100% Wet).
2. **Hit Stop during playback** and listen to the decaying tail in silence:
   - *Muddy boom?* → Pull down **Blue Curve at 80–120 Hz**.
   - *Boxy honk?* → Pull down **Blue Curve at 300–500 Hz**.
   - *Harsh sizzle or whistle?* → Dip **Blue Curve at 2.5–4 kHz** and widen Q.
   - *Dull or muffled?* → Lift **Blue Curve at 6–9 kHz** and open the Post EQ filter past 14 kHz.
3. **Unsolo the Reverb Track** and bring the fader up until the space sits naturally behind the dry signal.

---

## 8. Pro-R 2 Master Keyboard Shortcuts (Windows vs. macOS)

| Functionality | Windows Shortcut | macOS Shortcut | What It Does |
| :--- | :--- | :--- | :--- |
| **Fine Adjustment** | `Shift + Drag` / `Wheel` | `Shift + Drag` / `Wheel` | Fine-tunes knobs, sliders, and EQ bands in micro-increments. |
| **Reset to Default** | `Ctrl + Click` | `Command (⌘) + Click` | Instantly resets any knob, parameter, or EQ band to baseline default. |
| **Direct Text Entry** | `Double-Click` | `Double-Click` | Type exact numbers (`2.5 s` space, `35 ms` predelay, `1/16` tempo sync). |
| **Spawn Blue / Yellow Band**| Click & drag curve | Click & drag curve | Spawns a Decay Rate EQ (Blue) or Post EQ (Yellow) filter point. |
| **Adjust Band Q (Bandwidth)**| `Ctrl + Drag vertical` / `Wheel` | `Command (⌘) + Drag vertical` / `Wheel` | Widens or narrows filter bandwidth without altering gain or frequency. |
| **Axis-Lock Movement** | `Alt + Drag` | `Option (⌥) + Drag` | Constrains movement strictly to horizontal (frequency) or vertical (gain/time). |
| **Toggle Band Bypass** | `Alt + Click` band dot | `Option (⌥) + Click` band dot | Mutes individual EQ bands without deleting them. |
| **Delete EQ Band** | `Delete` or `Backspace` | `Delete` (Backspace) | Deletes selected EQ points cleanly. |
| **Freeze Reverb Buffer** | Single-Click or Hold button | Single-Click or Hold button | Click once to latch infinite sustain; click and hold for momentary burst. |
| **Lock Mix Ratio** | `Click` golden padlock icon | `Click` golden padlock icon | Keeps Wet/Dry balance locked when auditioning different room presets. |
| **Predelay Tempo Sync** | `Click` note icon above knob | `Click` note icon above knob | Snaps predelay timing to DAW musical intervals (1/32, 1/16, dotted). |
