# FabFilter Pro-R 2: Beginner-Friendly Mixing Guide and Cheat Sheet

Welcome to the plain-English, no-headache guide for **FabFilter Pro-R 2**. Whether you are mixing your very first song or you are a music lover wanting to understand how professional space works, this guide strips away the confusing audio-school math. Inside, you'll find simple analogies, conversational knob explanations, an instant IF/THEN troubleshooting guide, ready-to-use preset recipes, and visual walkthroughs.

---

## Table of Contents
1. [1. The Core Concept: Blue vs. Yellow Curve](#1-the-core-concept-blue-vs-yellow-curve)
2. [2. Knob Cheat Sheet: What Each Control Does](#2-knob-cheat-sheet-what-each-control-does)
3. [3. The Three Reverb Engines](#3-the-three-reverb-engines)
4. [4. Massive IF/THEN Decision Guide](#4-massive-ifthen-decision-guide)
   - [Low End and Bass Cleanup](#low-end-and-bass-cleanup)
   - [Midrange and Clarity Fixes](#midrange-and-clarity-fixes)
   - [Highs, Sibilance and Air Polish](#highs-sibilance-and-air-polish)
   - [Dynamic Reverb and Vocal Pocketing](#dynamic-reverb-and-vocal-pocketing)
   - [The XXX Master Trick: Punchy Bass and Distant Vocal](#the-xxx-master-trick-punchy-bass-and-distant-vocal)
   - [Instrument Rules: Drums, Guitars, Synths and Rooms](#instrument-rules-drums-guitars-synths-and-rooms)
5. [5. Quick Scenario Preset Tables](#5-quick-scenario-preset-tables)
   - [Trap and Melodic Rap: Punchy Bass and Distant Vocal](#trap-and-melodic-rap-punchy-bass-and-distant-vocal)
   - [Modern Pop Lead Vocal](#modern-pop-lead-vocal)
   - [Modern R&B Vocal](#modern-rb-vocal)
   - [Punchy Gated Snare](#punchy-gated-snare)
   - [Ambient and Cinematic Space](#ambient-and-cinematic-space)
6. [6. Practical Case Studies and Curve Evolution](#6-practical-case-studies-and-curve-evolution)
   - [Case Study 01: The XXX Breakthrough (Punchy Bass and Distant Vocal)](#case-study-01-the-xxx-breakthrough-punchy-bass-and-distant-vocal)
   - [Case Study 02: Haunting Cinematic Vocal](#case-study-02-haunting-cinematic-vocal)
   - [Case Studies 03 to 06: Bass Mud Trap to Punchy Fix Evolution](#case-studies-03-to-06-bass-mud-trap-to-punchy-fix-evolution)
   - [Case Studies 07 and 08: Post EQ High-Cut Audit and Balanced Fix](#case-studies-07-and-08-post-eq-high-cut-audit-and-balanced-fix)
   - [Case Study 09: Broad Low-Q Sculpting vs. Resonant Spikes](#case-study-09-broad-low-q-sculpting-vs-resonant-spikes)
   - [Case Study 10: Cathedral Dual-Hill Acoustic Evolution](#case-study-10-cathedral-dual-hill-acoustic-evolution)
7. [7. The 10-Second Solo Diagnostic Workflow](#7-the-10-second-solo-diagnostic-workflow)

---

## 1. The Core Concept: Blue vs. Yellow Curve

The biggest secret to clean mixes in Pro-R 2 is realizing that the two colored curves do two completely different jobs:

```
┌─────────────────────────────────────────────────────────────────────────┐
│ 🔵 BLUE CURVE = THE STOPWATCH (Decay Rate EQ)                           │
│ "How many SECONDS does each sound hang in the air before dying out?"    │
│ • Think of time, NOT loudness.                                          │
│ • Pulling 80 Hz down tells the deep bass: "Fade away in 0.2 seconds!"    │
│ • Lifting 5 kHz up tells airy highs: "Ring out like fairy dust for 4s!" │
│ • It does NOT make the sound louder when it first hits.                 │
└─────────────────────────────────────────────────────────────────────────┘
                                     │
                                     ▼ (creates the echo tail)
┌─────────────────────────────────────────────────────────────────────────┐
│ 🟡 YELLOW CURVE = THE VOLUME SLIDER (Post EQ)                           │
│ "How LOUD or QUIET is each frequency inside the echo itself?"           │
│ • Standard volume equalizer (decibels: -24 dB to +24 dB).               │
│ • Use this to turn down muddy rumble or soften harsh, hissing sizzle.   │
└─────────────────────────────────────────────────────────────────────────┘
```

### The Super-Simple Analogy
Imagine clapping your hands inside an empty stone church:
- **The Blue Curve is like clapping your hand over a vibrating bass drum:** If you grab the drum head immediately, the low bass thump stops ringing instantly, while the bright hand-clap keeps echoing off the stone walls for several seconds. You are controlling **how long** each tone survives.
- **The Yellow Curve is like wearing earplugs that block bass:** Even if the bass thump echoes in the room, the earplug turns down its **volume** so it doesn't overpower your ears.

> [!WARNING]
> **The Beginner's Trap: Never copy the moving graph on your screen!**  
> The moving analyzer shows your raw incoming sound. If your beat has a loud, booming 808 bass at 100 Hz, your eyes might tempt you to lift the Blue Curve there. **Don't do it!** That tells the reverb: *"Every time the bass hits, let it ring out for 5 whole seconds!"* That will turn your clean song into a muddy brown puddle. Wherever your bass hits hardest, you want the Blue Curve **pulled down** so the low echo vanishes quickly!

---

## 2. Knob Cheat Sheet: What Each Control Does

Here is what every major dial does in plain, everyday language:

| Control | What It Does (Plain English) | Sweet Spot Values |
| :--- | :--- | :--- |
| **Space** | **The Room Size:** Controls whether you are standing in a cozy closet (small) or an enormous airport hangar (huge). It sets your main reverb time (0.2s to 10s). | Drums: `0.8–1.5s`<br>Pop Vocals: `1.8–2.5s`<br>Ballads/Ambient: `3.0–6.0s` |
| **Decay Rate** | **The Master Time-Stretcher:** Stretches your reverb tail longer (up to 200%) or cuts it in half (down to 50%) without altering the room shape. | Leave at `100%` unless automating special drops or song build-ups. |
| **Predelay** | **The Polite Pause:** The split-second gap of silence before the echo begins (like shouting across a canyon). This lets your dry vocal or snare punch through right in front of your face before the echo cloud blooms behind it. | Drums: `0–15 ms`<br>Guitars/Keys: `15–35 ms`<br>Lead Vocals: `40–70 ms` |
| **Distance** | **Front-to-Back Staging:** How close the singer stands to the listener. At low settings, they are singing right into your ear; at high settings, they are standing at the back of a distant auditorium. | Lead Vocal: `15–30%`<br>Background Vocals: `50–70%`<br>Cinematic Pads: `60–90%` |
| **Character** | **Wall Texture:** Turned left (-), the walls sound hard and bare like an unfinished concrete basement (chunky, distinct echoes). Turned right (+), the walls sound like polished marble or silky clouds (creamy, chorus-like smoothness). | Retro/Guitars: `-30% to 0%`<br>Lush Vocals/Pads: `+20% to +50%` |
| **Thickness** | **Cloud Density:** How densely packed the sound reflections are. Low settings sound light, airy, and transparent (great for busy songs). High settings sound rich, heavy, and expensive (great for slow ballads). | Busy Mixes: `30–45%`<br>Sparse / Ballads: `60–80%` |
| **Brightness** | **Overall Tone Tilt:** A single dial to make the entire room warmer and darker (left) or crisp, shiny, and modern (right) without touching individual EQ nodes. | Darker/Warmer: `-20% to -10%`<br>Crisp/Airy: `0% to +15%` |
| **Width** | **Stereo Spread:** How wide the echo stretches between your ears. 0% is straight down the middle (mono), 100% is natural room stereo, and 120% wraps around your head in 3D. | Lead Vocal: `90–100%`<br>Backgrounds/FX: `110–120%` |
| **Ducking** | **The Smart Butler:** Automatically turns down the reverb volume while the singer is singing so words stay crystal clear, then gracefully brings the lush echo up the moment they pause to breathe! | Lead Vocals: `20–40%`<br>Full Beat / Master Bus: **Keep at 0%** |
| **Auto Gate** | **The 80s Drum Chop:** Lets a loud drum hit trigger a huge burst of reverb, then instantly slams the door shut the moment the drum hit ends (the classic Phil Collins snare sound). | Snare Drums: `ON`<br>Vocals & Pads: `OFF` |
| **Mix** | **The Wet/Dry Balance:** How much raw sound vs. reverb sound you hear. | Send / Aux Track: **Lock at 100% Wet**<br>Direct on Track: `10–25%` |

---

## 3. The Three Reverb Engines

You can choose your room flavor at the very top of the plugin window:

- **Modern:** Clean, transparent, and ultra-wide. No vintage hiss, no weird artifacts. Use this for modern Pop, Hip Hop, Trap vocals, and R&B.
- **Vintage:** Warm, slightly gritty, and dark with a gentle musical swirl, inspired by legendary 1980s studio hardware units (like the Lexicon 224/480). Perfect for rock guitars, retro synthwave, indie vocals, and warm drum rooms.
- **Plate:** Recreates the sound of heavy vibrating steel plates used in vintage studios. It has zero "room" bounce—just an immediate, bright, shimmering sizzle. Perfect for punchy snare drums and lead vocals that need to cut through thick walls of guitars or synths.
- **IR Import (The Drag-and-Drop Magic):** If you have an audio file (`.wav`) of a real concert hall or vintage gear (an impulse response), just drag and drop it onto Pro-R 2! Pro-R 2 automatically turns it into editable blue and yellow curves so you can reshape real spaces without slowing down your computer.

---

## 4. Massive IF/THEN Decision Guide

### Low End and Bass Cleanup
- **IF your bass sounds like a muddy puddle:**  
  → Grab the **blue curve around 80–120 Hz and pull it down to 15–30%** (Q = 0.8–1.2). This tells low bass echoes to stop in a fraction of a second, keeping your kick and 808 tight and punchy.
- **IF deep sub-bass (under 50 Hz) rumbles like a thunderstorm that robs your mix volume:**  
  → Drag the **blue curve at 30–40 Hz down to 20%**, and switch on a **yellow Post EQ High-Pass Filter at 80–120 Hz** to mute the lowest rumble completely.
- **IF your kick drum loses its punchy chest-thump whenever the reverb is on:**  
  → Carve a narrow **blue notch right at 60–90 Hz down to 15%**. The kick punch stays bone-dry and hard-hitting, while higher percussion splashes into the room.
- **IF the room feels weightless, hollow, or floating with no floor:**  
  → Gently lift the **blue curve at 50–80 Hz to 110–125%** with a wide bell filter (Q = 0.4–0.6). This gives the space a grounded, solid acoustic floor.

### Midrange and Clarity Fixes
- **IF the vocal sounds like it is singing from inside a cardboard box:**  
  → Pull down the **blue curve at 300–500 Hz to 70–80%** (Q = 0.6). That hollow, honky boxiness disappears immediately.
- **IF the singer or guitar sounds washed out, distant, or buried in the mix:**  
  → Give the dry sound a head start! Increase **Predelay to 40–70 ms** so the upfront voice hits first, and dial back the **Distance knob to 20–30%** to step the performer forward.
- **IF the reverb tail feels cold, thin, or robotic:**  
  → Warm it up by lifting the **blue curve at 650–850 Hz to 120–135%** (wide Q = 0.5). This carries the warm chest resonance of the singer's voice into the room.
- **IF strummed acoustic guitars sound cluttered or nasal:**  
  → Keep the blue curve flat around 600 Hz–1.2 kHz, and make a gentle **-3 dB scoop at 800 Hz on the yellow Post EQ**.

### Highs, Sibilance and Air Polish
- **IF harsh 'S', 'T', or cymbal sounds hurt your ears with a sharp sizzle:**  
  → Soften them by dipping the **blue curve at 2.5–4 kHz down to 80–90%** (Q = 0.5–0.7). The harsh sizzle dies quickly instead of ringing out.
- **IF vocals sound dull and lack that expensive, glossy radio shimmer:**  
  → Boost the **blue curve at 6–9 kHz up to 130–150%** (broad Q = 0.5). This creates an ethereal halo of air around the voice without introducing harshness.
- **IF the reverb sounds like somebody threw a thick wool blanket over the speakers:**  
  → Open up your **yellow Post EQ Low-Pass Filter out to 14–16 kHz**, or change it to a gentle high shelf so the top-end air can breathe.
- **IF you hear an annoying metallic whistle ringing on a single note:**  
  → Your blue curve node is pinched too narrow! Widen the bell by setting the Q to **0.3–0.6**. Never boost decay time with a needle-thin notch, or it will whistle like a tea kettle.

### Dynamic Reverb and Vocal Pocketing
- **IF the reverb blurs the words while singing, but sounds great when the singer stops:**  
  → Turn up the **Ducking knob to 25–40%** (when used on a vocal track or dedicated vocal send). The plugin will tuck the reverb out of the way while words are sung, then let the echo blossom into the pauses!
- **IF you are sharing one single reverb across your whole song or beat:**  
  → Keep the internal Ducking knob at 0%. Instead, place a separate compressor (like Pro-C 2) right after Pro-R 2 and sidechain it specifically to your lead vocal.
- **IF your huge stereo reverb disappears or sounds weird on phone speakers (mono):**  
  → Bring the **Width knob back to 85–100%**, and make sure all bass decay below 100 Hz is pulled down below 25%.

### The XXX Master Trick: Punchy Bass and Distant Vocal
*How to put a huge, dreamy cathedral space on a full 2-track beat or sample without turning the 808 bass into a muddy mess:*
1. **Ducking: Set to 0%** (Leaving ducking on makes every 808 bass kick choke and pump the vocal reverb).
2. **Blue Curve 75 Hz Deep Notch:** Pull the decay rate at **75 Hz down to 15%** (Q = 1.2).
3. **Blue Curve Mid/High Shelf:** Boost from **700 Hz all the way up to 7 kHz to 130–145%** (Q = 0.5–0.7).
4. **Yellow Post EQ:** Cut **-14 dB at 75 Hz**, and roll off extreme high fizz with a 12 dB/oct filter at **8.5 kHz**.
5. **Output Gain: Boost to +4.0 dB** to make up for the volume cut from the bass.
- **The Magic Result:** 808 kicks hit clean, dry, and punchy (dying in under 0.25 seconds), while vocals and melodies float inside an expansive 1.75-second cathedral!

### Instrument Rules: Drums, Guitars, Synths and Rooms
- **Punchy Snare Drum:**
  - Space `1.0–1.4s`, Predelay `0–10 ms`, Character `+20%`.
  - Blue curve: Cut below 120 Hz to 20% (no muddy thud), boost 2.5–3.5 kHz to 125% for explosive crack.
- **Tight Drum Room Glue:**
  - Engine: `Vintage`, Space `0.8–1.2s`, Character `-30%` (distinct, gritty room reflections).
  - Blue curve: Cut below 90 Hz to 25%, dip 350 Hz to 80%, roll off above 8 kHz to 75%.
- **Electric Guitar Leads:**
  - Engine: `Plate` or `Modern`, Space `2.2–3.0s`, Predelay `30–45 ms`.
  - Blue curve: Dip 200 Hz to 60%, boost 2.5 kHz to 120% for singing, soulful sustain.
- **Acoustic Guitar Strumming:**
  - Predelay `25 ms`, Distance `40%`, Yellow Post EQ High-Pass at `180 Hz`.
  - Blue curve: Keep 300–700 Hz below 85% to stop boomy wooden resonance buildup.
- **Synth Leads & Arps:**
  - Space `1.8–2.6s`, Width `115%`, Predelay `20 ms`.
  - Blue curve: Cut below 150 Hz to 20%, boost 5–8 kHz to 140% for wide stereo sparkle.
- **Ambient / Cinematic Pads:**
  - Space `5.0–9.0s`, Distance `70%`, Thickness `75%`.
  - Blue curve: Lift 700 Hz to 135%, lift 5.5 kHz to 160%, yellow HPF at 80 Hz to prevent low-end mud buildup.

---

## 5. Quick Scenario Preset Tables

### Trap and Melodic Rap: Punchy Bass and Distant Vocal
*Tight, dry 808 kick punch with a floating, dreamy space for melodic vocals.*

| Parameter | Setting | Target Sound / Role |
| :--- | :--- | :--- |
| **Engine** | Modern | Clean, crisp, non-muddy stereo wash |
| **Space** | 1.75 s | Compact cathedral depth |
| **Predelay** | 35 ms | Keeps lead vocals and snare hits upfront |
| **Distance** | 38% | Pushes the vocal space gently behind dry drums |
| **Character / Thickness** | 50% / 55% | Smooth diffusion with moderate body |
| **Width / Ducking** | 100% / 0% | Full stereo; zero dynamic pumping |
| **Decay Rate (Blue)** | • 30 Hz: 25%<br>• 75 Hz: 15% (Q=1.2)<br>• 200 Hz: 55%<br>• 700 Hz: 115%<br>• 3.5 kHz: 130%<br>• 6.8 kHz: 140% | Kills 808/kick bass tail in <0.25s while letting vocal notes linger |
| **Post EQ (Yellow)** | • 75 Hz: -14 dB (Bell, Q=1.2)<br>• 500 Hz: -2.5 dB<br>• 8.5 kHz: -8 dB (12 dB/oct LPF) | Eliminates sub energy and harsh digital splash |
| **Output** | +4.0 dB | Makeup gain for heavy low-frequency cuts |

---

### Modern Pop Lead Vocal
*Glossy, upfront radio polish that stays out of the singer's way.*

| Parameter | Setting | Target Sound / Role |
| :--- | :--- | :--- |
| **Engine** | Modern | Pristine top end with zero grain |
| **Space** | 2.0 – 2.4 s | Polished commercial tail length |
| **Predelay** | 50 – 70 ms | Critical for keeping syllables sharp and intelligible |
| **Distance** | 20% | Intimate, forward vocal placement |
| **Character / Thickness** | +30% / 45% | Smooth diffusion with lean, transparent density |
| **Width / Ducking** | 100% / 25% | Natural stereo; tail tucks in while vocal sings |
| **Decay Rate (Blue)** | • 100 Hz: 30%<br>• 400 Hz: 85%<br>• 2.8 kHz: 95% (tames harshness)<br>• 7.5 kHz: 135% (sheen) | Cleans mud, softens harsh sibilants, adds luxury air |
| **Post EQ (Yellow)** | • HPF: 150 Hz (18 dB/oct)<br>• Bell: -2.5 dB @ 450 Hz<br>• LPF: 15 kHz (6 dB/oct gentle slope) | Modern open top end with clean low-mids |
| **Output** | 0.0 dB | Standard balanced level |

---

### Modern R&B Vocal
*Lush, warm, velvety chest tone with an enveloping stereo halo.*

| Parameter | Setting | Target Sound / Role |
| :--- | :--- | :--- |
| **Engine** | Plate or Modern | Rich, warm musical decay |
| **Space** | 2.5 – 3.2 s | Deep, emotive ballad room |
| **Predelay** | 40 – 55 ms | Keeps breath and diction clear |
| **Distance** | 30% | Cozy, intimate singer proximity |
| **Character / Thickness** | +40% / 70% | Silk-smooth diffusion with rich, dense body |
| **Width / Ducking** | 105% / 30% | Expansive stereo sides; ducked during phrases |
| **Decay Rate (Blue)** | • 80 Hz: 35%<br>• 750 Hz: 135% (vocal chest warmth)<br>• 3 kHz: 105%<br>• 8 kHz: 125% | Maximizes emotional chest warmth without mud |
| **Post EQ (Yellow)** | • HPF: 130 Hz (12 dB/oct)<br>• Bell: -2 dB @ 350 Hz<br>• LPF: 12 kHz (12 dB/oct) | Warm, rounded, non-fatiguing top end |
| **Output** | -1.0 dB to 0.0 dB | Balanced level matching |

---

### Punchy Gated Snare
*Explosive 80s burst that cuts off instantly, keeping the groove tight.*

| Parameter | Setting | Target Sound / Role |
| :--- | :--- | :--- |
| **Engine** | Vintage | Classic gritty 80s hardware character |
| **Space** | 1.4 – 1.8 s | Big hall burst before the gate chops it |
| **Predelay** | 0 – 5 ms | Instant impact locked to snare hit |
| **Distance** | 15% | Direct, in-your-face room explosion |
| **Character / Thickness** | -20% / 60% | Coarse, punchy reflections |
| **Auto Gate** | **ON** | Automatically clamps the tail when snare finishes |
| **Decay Rate (Blue)** | • 100 Hz: 30%<br>• 1.5 kHz: 120%<br>• 3.2 kHz: 140% (snare crack)<br>• 10 kHz: 75% | Maximizes explosive upper-mid crack; kills low boom |
| **Post EQ (Yellow)** | • HPF: 140 Hz (18 dB/oct)<br>• LPF: 9.5 kHz (18 dB/oct) | Recreates classic filtered 80s console sound |
| **Output** | +1.5 dB | Punchy impact compensation |

---

### Ambient and Cinematic Space
*Monumental, infinite stone atmosphere for film trailers, pianos, and pads.*

| Parameter | Setting | Target Sound / Role |
| :--- | :--- | :--- |
| **Engine** | Modern | Colossal, clean acoustic scale |
| **Space** | 5.0 – 8.0 s | Massive cathedral decay envelope |
| **Predelay** | 30 – 50 ms | Separates initial note from huge atmospheric bloom |
| **Distance** | 55 – 70% | Deep, distant soundstaging |
| **Character / Thickness** | +40% / 75% | Glass-smooth, ultra-dense reflection body |
| **Width / Ducking** | 115% / 0% | Massive wraparound stereo image; zero ducking |
| **Decay Rate (Blue)** | • 35 Hz: 65%<br>• 750 Hz: 135%<br>• 3.5 kHz: 140%<br>• 5.5 kHz: 160% (stone wall ring)<br>• 14 kHz: 100% | Recreates monumental stone church reflection formants |
| **Post EQ (Yellow)** | • HPF: 85 Hz (12 dB/oct)<br>• High Shelf: -4 dB @ 9 kHz<br>• Out: -5.0 dB | Headroom protection against massive multi-second tails |
| **Output** | -5.0 dB to -6.0 dB | Trims output to prevent bus clipping |

---

## 6. Practical Case Studies and Curve Evolution

Key mixing techniques and curve designs from our production analysis are detailed below with practical takeaways.

---

### Case Study 01: The XXX Breakthrough (Punchy Bass and Distant Vocal)
- **Settings:** Blue Decay Rate EQ notched down to 15% at 75 Hz; high frequencies boosted to 140% above 5 kHz.
- **Takeaway:** Cutting decay time at 75 Hz down to 15% while boosting upper frequencies to 140% allows heavy 808 bass to punch bone-dry, while vocals float in a massive cathedral.

---

### Case Study 02: Haunting Cinematic Vocal
- **Settings:** Two broad, gentle Blue Decay hills at 750 Hz and 5.5 kHz (Q = 0.4).
- **Takeaway:** Two gentle, wide hills at 750 Hz and 5.5 kHz recreate the cold, eerie echo of an ancient stone chapel while keeping the lead voice intimate and warm.

---

### Case Studies 03 to 06: Bass Mud Trap to Punchy Fix Evolution

#### Step 1: The Trap (100 Hz Decay Peak)
- **Problem:** Boosting decay at 100 Hz makes bass notes ring for over 4.5 seconds, turning the entire song into an unintelligible muddy swamp.

#### Step 2: Intermediate Attempt (Twin Resonant Spikes)
- **Problem:** Shortening the room size still sounds bad if you leave sharp decay spikes at 100 Hz and 7 kHz; narrow peaks always ring like an irritating whistle.

#### Step 3: The Inversion (Carving the Bass Decay Notch)
- **Fix:** Flipping the 100 Hz boost into a deep decay cut immediately brings back the kick drum's tight, punchy chest thump.

#### Step 4: Fine-Tuning (Punchy Bass with High Shimmer)
- **Result:** The sweet spot pairs a fast low-end decay with a bright, shimmering 7 kHz tail, creating modern radio gloss with zero mud.

---

### Case Studies 07 and 08: Post EQ High-Cut Audit and Balanced Fix

#### The Problem: Choked High Cut
- **Audit:** Even if your blue decay curve is perfect, aggressively cutting highs on the yellow Post EQ will suffocate your reverb and make it sound dull and dark.

#### The Fix: Balanced Open Air
- **Adjustment:** Opening the yellow high-cut filter past 14 kHz and gently notching 130 Hz restores open, airy shimmer and clean vocal separation.

---

### Case Study 09: Broad Low-Q Sculpting vs. Resonant Spikes
- **Principle:** Always use wide, gentle decay curves (Q = 0.3–0.6); sharp, narrow spikes sound like artificial digital whistling rather than natural room acoustics.

---

### Case Study 10: Cathedral Dual-Hill Acoustic Evolution
- **Principle:** Real historic stone buildings resonate across two broad zones—warm midrange at 700 Hz and airy stone reflections at 5.5 kHz—giving you authentic acoustic scale.

---

## 7. The 10-Second Solo Diagnostic Workflow

Whenever you are setting up your reverb, never guess with your eyes. Follow this quick 3-step ear test:

1. **Solo your Reverb track** (or temporarily set the Mix knob to 100% Wet).
2. **Hit Stop during playback** and listen closely to what hangs in the silence:
   - **Does the tail sound thumpy or muddy?** → Pull down the Blue Curve at **80–120 Hz to 15–30%**.
   - **Does the tail sound like a hollow cardboard box?** → Pull down the Blue Curve at **300–500 Hz to 70–80%**.
   - **Does the tail sound harsh or whistle in your ears?** → Dip the Blue Curve at **2.5–4 kHz** or widen your Q to 0.5.
   - **Does the tail sound dark, dead, or muffled?** → Lift the Blue Curve at **6–9 kHz to 135%**, and open the yellow Post EQ filter out to 15 kHz.
   - **Does the room sound thin and floating with no floor?** → Gently nudge the Blue Curve at **50–80 Hz up to 115%**.
3. **Unsolo your Reverb track** and bring up your track fader until the space feels natural in the full mix!
