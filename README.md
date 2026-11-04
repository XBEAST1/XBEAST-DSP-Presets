# XBEAST DSP Presets

Curated audio DSP presets, tuning profiles, and engineering guides for cross-platform sound optimization and mastering.

---

## Repository Structure

```
XBEAST-DSP-Presets/
├── README.md
│
├── EasyEffects/
│   ├── XBEAST (Headphones) - Balanced.json
│   ├── XBEAST (Headphones) - Punchy Bass.json
│   ├── XBEAST (Headphones) - Heavy Bass.json
│   ├── XBEAST (Headphones) - Extreme Sub-Bass.json
│   ├── XBEAST (IEMs) - Balanced.json
│   ├── XBEAST (IEMs) - Punchy Bass.json
│   ├── XBEAST (IEMs) - Heavy Bass.json
│   ├── XBEAST (IEMs) - Extreme Sub-Bass.json
│   └── XBEAST (Speakers) - Rich Clarity.json
│
├── Equalizer APO + Peace/
│   ├── XBEAST (Headphones) - Balanced.peace
│   ├── XBEAST (Headphones) - Punchy Bass.peace
│   ├── XBEAST (Headphones) - Heavy Bass.peace
│   ├── XBEAST (Headphones) - Extreme Sub-Bass.peace
│   ├── XBEAST (IEMs) - Balanced.peace
│   ├── XBEAST (IEMs) - Punchy Bass.peace
│   ├── XBEAST (IEMs) - Heavy Bass.peace
│   ├── XBEAST (IEMs) - Extreme Sub-Bass.peace
│   └── XBEAST (Speakers) - Rich Clarity.peace
│
├── Equalizer314/
│   ├── XBEAST (Headphones) - Balanced.json
│   ├── XBEAST (Headphones) - Punchy Bass.json
│   ├── XBEAST (Headphones) - Heavy Bass.json
│   ├── XBEAST (Headphones) - Extreme Sub-Bass.json
│   ├── XBEAST (IEMs) - Balanced.json
│   ├── XBEAST (IEMs) - Punchy Bass.json
│   ├── XBEAST (IEMs) - Heavy Bass.json
│   ├── XBEAST (IEMs) - Extreme Sub-Bass.json
│   └── XBEAST (Speakers) - Rich Clarity.json
│
├── SoundSource/
│   └── Presets.plist
│
└── FabFilter/
    ├── Pro-Q/
    │   ├── presets/
    │   │   ├── Headphones/
    │   │   │   ├── XBEAST - Balanced.ffp
    │   │   │   ├── XBEAST - Punchy Bass.ffp
    │   │   │   ├── XBEAST - Heavy Bass.ffp
    │   │   │   └── XBEAST - Extreme Sub-Bass.ffp
    │   │   ├── IEMS/
    │   │   │   ├── XBEAST - Balanced.ffp
    │   │   │   ├── XBEAST - Punchy Bass.ffp
    │   │   │   ├── XBEAST - Heavy Bass.ffp
    │   │   │   └── XBEAST - Extreme Sub-Bass.ffp
    │   │   └── Speakers/
    │   │       └── XBEAST - Rich Clarity.ffp
    │   ├── screenshots/
    │   └── GUIDE.md
    │
    ├── Pro-R/
    │   ├── presets/
    │   └── GUIDE.md
    │
    └── Pro-L/
        ├── presets/
        │   └── XBEAST.ffp
        └── GUIDE.md
```

---

## Directory Overview

### 1. EasyEffects (Linux)
System-wide parametric equalization and dynamics processing for Linux via **EasyEffects** (PipeWire audio pipeline):
- **Over-Ear Headphones Profiles (`.json`):**
  - **`XBEAST (Headphones) - Balanced.json`**, **`Punchy Bass.json`**, **`Heavy Bass.json`**, **`Extreme Sub-Bass.json`**: Tuned with ear-cup presence offsets (`+0.2 dB` to `+2.7 dB`) to maintain crisp vocal articulation over powerful low-end excursions.
- **In-Ear Monitor (IEM) Profiles (`.json`):**
  - **`XBEAST (IEMs) - Balanced.json`**, **`Punchy Bass.json`**, **`Heavy Bass.json`**, **`Extreme Sub-Bass.json`**: Calibrated for direct ear-canal insertion with protective treble tuning matching the Tier 2A master specification.
- **Built-in Speaker Profile (`.json`):**
  - **`XBEAST (Speakers) - Rich Clarity.json`**: Specifically voiced for laptop (MacBook) and mobile phone speakers. Adds clean mid-bass punch at 64 Hz while enhancing vocal intelligibility and presence across 500 Hz – 4 kHz without overdriving miniature speaker drivers.
- **Technical Architecture & Signal Chain:**
  - **Chain Order:** `equalizer#0` → `limiter#0`.
  - **Filter Topology:** 10-band parametric EQ ($Q = 1.00$). Band 0 (32 Hz) is `Low-shelf`, Bands 1–8 are `Bell`, and Band 9 (16,000 Hz) is `High-shelf` (LSP dual-mono).
  - **Headroom & Dynamic Protection:** Integrated digital preamp attenuation (`-9 dB` to `-22 dB`) paired with an active fast-response brickwall limiter (`Herm Thin` mode) to guarantee pristine transient fidelity with zero digital clipping.
  - **Limiter Sidechain Routing (Fixing Limiter Glitches):** All presets have `external-sidechain` enabled on the limiter so it tracks EQ excursions with maximum precision. In EasyEffects, PipeWire can occasionally unbind the sidechain source when loading new presets; if the limiter ever behaves inconsistently or bugs out, open the **Limiter** settings in EasyEffects and ensure the **External Sidechain** input is explicitly routed/selected to **Equalizer** (`equalizer#0`).
- **How to Install into EasyEffects:**
  - Copy the `.json` preset files into your EasyEffects output preset directory:
    - **Native / Package install:** `~/.config/easyeffects/output/`
    - **Flatpak install:** `~/.var/app/com.github.wwmm.easyeffects/config/easyeffects/output/`
  - In EasyEffects, open the **Presets** menu and select the profile matching your listening gear.

### 2. Equalizer APO + Peace (Windows)
System-wide parametric equalization curves for Windows (stored directly in `Equalizer APO + Peace/` for loading in Peace GUI):
- **Over-Ear Headphones Profiles (`.peace`):**
  - **`XBEAST (Headphones) - Balanced.peace`**, **`Punchy Bass.peace`**, **`Heavy Bass.peace`**, **`Extreme Sub-Bass.peace`**: Calibrated with ear-tuned presence offsets (`+0.2 dB` to `+2.7 dB`) and standardized mathematical headroom preamps (`-9 dB`, `-11 dB`, `-14 dB`, and `-22 dB`) to guarantee 100% clean, distortion-free sound across all drivers, DACs, and audio capture apps.
- **In-Ear Monitor (IEM) Profiles (`.peace`):**
  - **`XBEAST (IEMs) - Balanced.peace`**, **`Punchy Bass.peace`**, **`Heavy Bass.peace`**, **`Extreme Sub-Bass.peace`**: 10-band static profiles matching the Tier 2A master specification with unified headroom preamps (`-9 dB` to `-22 dB`).
- **Built-in Speaker Profile (`.peace`):**
  - **`XBEAST (Speakers) - Rich Clarity.peace`**: Voiced for Windows laptops and desktop speakers with a `0 dB` listening preamp for maximum volume.
- **How to Install into Peace GUI:**
  - Copy the `.peace` files into your Equalizer APO configuration directory:
    ```
    C:\Program Files\EqualizerAPO\config
    ```
  - Open **Peace GUI**, and your profiles will be automatically available in the preset list.

#### Windows "Hidden Limiter" vs. Screen Recording Distortion
- **The Windows "Hidden Limiter" (`CAudioLimiter`):** Windows 10 and 11 feature an internal limiter (`CAudioLimiter` inside the WASAPI shared audio engine in `audiodg.exe`). When an EQ boost pushes peaks above `0 dBFS`, Windows automatically ducks the volume to prevent immediate, harsh square-wave clipping in your headphones. However, this causes **unwanted volume pumping** (vocals ducking every time heavy bass hits) and squashes dynamic punch.
- **Why Screen Recordings & Streams Distort:** Recording applications (OBS Studio, Discord screen sharing, GeForce Experience / ShadowPlay, Xbox Game Bar, and Audacity loopback) tap into Windows' digital audio stream directly via WASAPI loopback. If your preamp is set too high (e.g. `-2 dB` instead of `-9 dB`), the digital signal exceeds 0 dBFS. While your headphones might sound acceptable due to Windows' limiter, **the screen recording captures the clipped digital stream, resulting in harsh crackling, buzz, and severe distortion on your recorded videos and streams.**
- **Standardized Headroom Solution:** To ensure pristine recordings, crystal-clear streams, and uncompressed dynamics, all Peace presets use standardized mathematical preamps (`-9 dB` to `-22 dB`).

#### How to Increase Volume if Hardware is Maxed Out
If your Windows volume slider and headphone amplifier are already maxed out and you need extra volume strictly for listening to quiet tracks:

> [!TIP]
> **Recommended Method: Add a Toggleable Preamp Block in Equalizer APO**  
> Rather than editing individual Peace presets, add a dedicated Preamp block directly in Equalizer APO:
> 1. Open **Equalizer APO Configuration Editor** (`C:\Program Files\EqualizerAPO\Editor.exe`).
> 2. Ensure `Include: peace.txt` is present in the processing list.
> 3. Click the green **`+`** icon $\rightarrow$ **Basic filters** $\rightarrow$ **Preamp (Preamplification)**.
> 4. Set the preamp slider to your desired boost (e.g. **`+6.0 dB`** or **`+8.0 dB`**).
> 5. **Instant One-Click Control:**
>    - **For everyday listening:** Leave the block's power button **ON** (green) to enjoy maximum volume.
>    - **Before recording your screen or streaming (OBS / Discord):** Click the power button **OFF** (grayed out) with one click to instantly restore clean, distortion-free headroom for your recordings!
>    - **Why this beats the Peace slider:** An Equalizer APO Preamp block never gets reset when you switch Peace presets, and the live peak meter at the bottom shows you in real time if your audio is pushing into the red clipping zone.

### 3. Equalizer314 (Android)
System-wide parametric equalization profiles for **Equalizer314** (open-source Android equalizer powered by Android's native `DynamicsProcessing` architecture):
- **Over-Ear Headphones Profiles (`.json`):**
  - **`XBEAST (Headphones) - Balanced.json`**, **`Punchy Bass.json`**, **`Heavy Bass.json`**, **`Extreme Sub-Bass.json`**: Tuned with ear-cup presence offsets (`+0.2 dB` to `+2.7 dB`) to maintain crisp vocal articulation over powerful low-end excursions.
- **In-Ear Monitor (IEM) Profiles (`.json`):**
  - **`XBEAST (IEMs) - Balanced.json`**, **`Punchy Bass.json`**, **`Heavy Bass.json`**, **`Extreme Sub-Bass.json`**: Calibrated for direct ear-canal insertion with protective treble tuning matching the Tier 2A master specification.
- **Built-in Speaker Profile (`.json`):**
  - **`XBEAST (Speakers) - Rich Clarity.json`**: Specifically voiced for mobile phone speakers and Android tablets calibrated with a `0 dB` preamp for full listening loudness.
- **Technical Specifications:**
  - **Filter Topology:** 10 parametric bands ($Q = 1.00$). Band 1 is `LOW_SHELF`, Bands 2–9 are `BELL`, and Band 10 is `HIGH_SHELF`.
  - **Headroom Protection:** Integrated digital preamp attenuation (`-9 dB` on Balanced, `-11 dB` on Punchy Bass, `-14 dB` on Heavy Bass, and `-20 dB` on Extreme Sub-Bass) matching peak filter boosts to guarantee zero `0 dBFS` clipping across Android's audio pipeline.
- **How to Import into Equalizer314:**
  1. Download or copy the desired `.json` files to your Android device (e.g., your device's `Download/` folder).
  2. Launch **Equalizer314** and open the **Presets** menu (or tap the preset icon on the main interface).
  3. Select **Import**, choose the `.json` profile corresponding to your listening gear (Headphones or IEMs), and apply.

### 4. SoundSource (macOS)
System-wide audio control on macOS via Rogue Amoeba's **SoundSource**:
- **`Presets.plist`**: Custom EQ presets file containing 7 universal 10-Band EQ profiles aligned with Tier 2 static specifications:
  - **Over-Ear Headphones:** `XBEAST (Headphones) - Balanced`, `Punchy Bass`, and `Heavy Bass`.
  - **In-Ear Monitors (IEMs):** `XBEAST (IEMs) - Balanced`, `Punchy Bass`, and `Heavy Bass`.
  - **Built-in Speakers:** `XBEAST (Speakers) - Rich Clarity` (specifically tuned for MacBook and laptop speakers).
  - *(Note: Extreme Sub-Bass is omitted from SoundSource as its +20 dB boost exceeds the ±12 dB maximum slider limit of the 10-Band EQ).*
- **How to Install into SoundSource:**
  1. **Quit SoundSource completely** (from the menu bar: SoundSource icon → Settings/Gear icon → "Quit SoundSource", or via Terminal: `killall SoundSource`) so in-memory settings do not overwrite your changes on exit.
  2. Copy `Presets.plist` into your SoundSource Application Support directory:
     ```
     ~/Library/Application Support/SoundSource/
     ```
  3. Relaunch **SoundSource**, and select your desired profile from the 10-Band EQ preset menu.

### 5. FabFilter Suite (Audiophile & Production Guides)
Beginner-friendly, jargon-free engineering guides and presets for the FabFilter plugin suite:
- **Master Signal Chain Sequence:** `FabFilter Pro-Q` (Tone / Spectral Dynamic EQ) ──► `(Optional) FabFilter Pro-R 2` (Spatial Ambience) ──► `FabFilter Pro-L 2` (True Peak Ceiling Limiter).
- **[Pro-Q](FabFilter/Pro-Q/GUIDE.md)**: Beginner's guide to massive bass, dynamic precision, and clean sound. Covers the "Water Glass" headroom principle, 32-bit float vs DAC fixed-point limits, why 8–10 bands is optimal for IEMs (avoiding 16–32 band phase smearing & pre-ringing), Spectral Dynamics mechanics (surgically taming sibilance, harsh plate reverbs, and boomy drops without dulling presence), and real-time live DSP routing chains for SoundSource (macOS) and Equalizer APO (Windows).
- **[Pro-R 2](FabFilter/Pro-R/GUIDE.md)**: Concise, practical guide to professional reverb space. Breaks down the Blue vs. Yellow curve ("The Stopwatch vs. The Volume Slider"), a practical curve filter guide (ideal band counts, shapes, gains, and Q factors), all interface controls sequenced left to right, and the 10 second solo ear test.
- **[Pro-L 2](FabFilter/Pro-L/GUIDE.md)**: Beginner's guide to loud, punchy, and distortion-free sound. Explains what a limiter does, how **Attack** (drum punch vs. flatness) and **Release** (waveform buzz vs. volume pumping) work when turning them up or down, the 5 essential settings (Ceiling, Gain sweet spot, Modern style, Lookahead, and 4x Oversampling), and a 5-scenario problem solver.

---

## Tested Hardware & Audiophile Chain

These profiles and FabFilter presets have been tested and calibrated on the following reference hardware:

| Component | Hardware | Architecture & Sonic Characteristics |
| :--- | :--- | :--- |
| **DAC / Amp** | **JCALLY JM98MAX** | Cirrus Logic **CS43198** 32-bit DAC paired with an **SGM8262** dual operational amplifier. Delivers ~195 mW @ 32Ω with ~0.65Ω output impedance, 125 dB SNR, and 0.0003% THD+N. Supports PCM decoding up to 32-bit/384 kHz and native DSD256. |
| **In-Ear Monitors (IEMs)** | **KZ Castor Improved Bass Edition** | Stacked dual dynamic driver configuration with a 10mm dual-magnetic composite driver dedicated to 20–200 Hz low frequencies alongside an 8mm driver handling midrange and treble. Built with an integrated 2-way electronic crossover, independent acoustic chambers, and 4-stage hardware tuning dip switches. |
| **Over-Ear Headphones** | **HyperX Cloud III** | Closed-back circumaural headphones utilizing angled 53mm dynamic drivers with neodymium magnets. Features a 64Ω nominal impedance and a 10 Hz – 21 kHz frequency response within sealed acoustic ear-cup enclosures. |

---

## Optimal Audio Settings: Sample Rate & Bit Depth Guide

To achieve the cleanest sound reproduction, lowest system latency, and zero distortion across Windows, macOS, Linux, and Android, configure your operating system sound settings and DAC with the following values:

### 1. Sample Rate: 44.1 kHz vs. 48 kHz (Which is Best?)

- **The Universal Winner for Everything (Gaming + Music + Daily Use): `48 kHz (48,000 Hz)`**
  - **Why 48 kHz Wins for Daily Use:** All modern PC games, game engines (Unreal, Unity), YouTube videos, movies, Netflix, Discord calls, and operating system audio engines (Windows WASAPI, macOS CoreAudio, Linux PipeWire) operate natively at **48 kHz**.
  - **The Real-Time Resampling Problem:** If your operating system or DAC is set to 44.1 kHz, every game, video, and Discord stream must be downsampled in real-time by the OS mixer, which can introduce micro-aliasing, buffer crackles, or latency.
  - **What about 44.1 kHz Music?** Standard CD audio and music streams (Spotify, standard Apple Music) are recorded at 44.1 kHz. However, modern OS resamplers convert 44.1 kHz up to 48 kHz with complete mathematical transparency (completely inaudible). Running your system at **48 kHz** guarantees flawless, glitch-free audio across games and media simultaneously.
  - **When to use 44.1 kHz:** Only when using a dedicated "Exclusive Mode" / bit-perfect music player (like Foobar2000, Tidal Exclusive, or Audirvana) playing 44.1 kHz lossless audio exclusively with no background games or apps running.
  - **What about 96 kHz or 192 kHz?** Avoid setting your operating system to 96 kHz or 192 kHz for everyday listening. Human hearing tops out at 20 kHz (48 kHz cleanly reproduces up to 24 kHz). Ultra-high sample rates consume 2x–4x more CPU power, increase USB DAC buffer latency, and can paradoxically increase high-frequency intermodulation distortion on analog headphone amplifiers without providing any audible improvement.

---

### 2. Bit Depth: 16-bit vs. 24-bit vs. 32-bit (Which is Best?)

- **The Winner: `24-bit` or `32-bit` (Select the highest setting your DAC supports — Never use 16-bit)**
  - **16-bit (96 dB Dynamic Range):** Fine for unedited raw CD listening at 100% volume, but leaves **zero digital headroom**. When you apply negative digital preamp trims, aggressive EQ boosts, or lower your software volume slider, you cut into the 16 bits and push quantization distortion closer to the audible threshold.
  - **24-bit (144 dB Dynamic Range):** Provides **48 dB of extra clean digital headroom**—well below the thermal noise floor of human hearing and physical DAC chips (the best DAC chips on earth max out around 125–130 dB SNR). You can apply heavy EQ boosts and digital preamp cuts with zero signal degradation or hiss.
  - **32-bit (Float / Integer):** Internal DSP engines (FabFilter, Equalizer APO, PipeWire, EasyEffects) perform all filtering in **32-bit floating point** (>1,500 dB dynamic range). Setting your DAC driver to 24-bit or 32-bit allows the processed DSP signal to pass directly to the hardware without truncation or rounding errors.

---

### Quick Reference: Recommended Settings

| Use Case | Recommended Sample Rate | Recommended Bit Depth | Engineering Rationale |
| :--- | :---: | :---: | :--- |
| **All-Round Universal**<br>*(Gaming, Music, YouTube, Discord, Movies)* | **`48 kHz`** | **`24-bit` or `32-bit`** | **The Best Overall.** Matches native game engines, video streams, and OS audio mixers with zero downsampling friction and maximum DSP headroom. |
| **Dedicated Audiophile Music**<br>*(Exclusive Mode Bit-Perfect Players)* | **`44.1 kHz`**<br>*(or Match Source)* | **`24-bit` or `32-bit`** | Matches original CD Red Book sample rate 1:1 without OS mixer intervention. |

---

## Open-Source Calibration: Tuning Limiter Gain for Your Gear

Because this repository is open source and designed for everyone, **you must calibrate the Limiter Gain (Pro-L 2) to match your specific audio hardware**.

### Why Calibration Is Necessary
1. **Pre-Amp Headroom in Pro-Q:** All `XBEAST` Pro-Q presets intentionally pull down the EQ Output slider by **`-8 dB to -15 dB`** to prevent digital clipping when applying heavy sub-bass boosts.
2. **Restoring Volume in Pro-L 2:** Pro-L 2 sits directly after Pro-Q to safely boost the track back up to commercial loudness.
3. **Hardware Differences:**
   - **High-Sensitivity IEMs** (low impedance, high dB/mW sensitivity like multi-driver IEMs): Need very little voltage to get extremely loud. Pushing the limiter gain too high can make them uncomfortably loud or expose DAC noise floor. A conservative boost of **`+4 dB to +8 dB`** is typically the sweet spot.
   - **Over-Ear Headphones & Planars** (higher impedance like 50Ω–300Ω, larger dynamic diaphragms): Require more voltage drive to move air. They will typically require **`+8 dB to +12 dB`** (or more) of Pro-L 2 Gain to restore full, punchy commercial listening loudness.
   - **DAC / Amp Power:** Dedicated DAC dongles and desktop headphone amps output much more voltage (1.5V – 2.0V+ RMS) than basic laptop/phone headphone jacks (0.5V – 1.0V RMS). The more powerful your DAC/Amp, the less software digital gain you need in Pro-L 2.

### 4-Step Calibration Procedure
1. **Set Physical Volume:** Set your hardware DAC volume knob or operating system volume slider to a normal, comfortable middle level.
2. **Check Pro-L 2 Basics:** Ensure **Ceiling** is at **`-0.1 dBTP` to `0.0 dBTP`** for everyday listening (or **`-1.0 dBTP`** if mastering/exporting audio for streaming), **Style** is set to **`Modern`**, **`1:1 True Peak`** is **ON**, and **Oversampling** is set to **`4x`**.
3. **Adjust the Gain Slider:** Slowly push the Pro-L 2 **Gain slider** upward until the music reaches your ideal loudness.
4. **Watch the Top Red Meter:** On the loudest bass hits and drops, the red gain reduction meter at the top of Pro-L 2 should dip by **`1 dB to 3 dB`** (the sweet spot). If it is constantly dipping by `6 dB+`, pull the Gain slider back down slightly to keep your transients dynamic and punchy.

---

## Preset Architecture & Listening Tiers

The presets in this repository are structured across two dimensions: **Sound Signature Curves** (bass level) and **DSP Platform Tiers** (active spectral dynamics vs. universal static).

### 1. Sound Signature Curves

| Category | Presets | Sonic Character & Target |
| :--- | :--- | :--- |
| **Everyday & Audiophile** | **`Balanced`**, **`Punchy Bass`** | Controlled sub-bass and dynamic kick-drum punch. Vocal-forward and clean across all genres. |
| **High-Excursion Bass** | **`Heavy Bass`**, **`Extreme Sub-Bass`** | Deep sub-bass wall and infrasonic car-subwoofer rumble (+12 dB to +20 dB boost). |
| **Built-in Speakers** | **`Rich Clarity`** | Voiced for MacBook and smartphone speakers. Punches 64 Hz kick body and boosts 500 Hz – 4 kHz vocal clarity while respecting small driver excursion. |

---

### 2. DSP Platform Tiers: Active Spectral Dynamics vs. Universal Static

To ensure the best possible sound across all platforms from desktop VST hosts to mobile equalizers and dedicated hardware DACs:

#### Tier 1: FabFilter Suite (Master Gold Standard)
- **The Ultimate Experience:** Hosted via **SoundSource** (macOS) or **Equalizer APO VST** (Windows).
- **Master Signal Chain Sequence:**
  ```
  Audio Source ──► [1] FabFilter Pro-Q ──► [2] (Optional) FabFilter Pro-R 2 ──► [3] FabFilter Pro-L 2 ──► Hardware DAC
                    (Tonal Shaping / EQ)         (Subtle Spatial Ambience)           (True Peak Limiter & Ceiling)
  ```
  - **1. Pro-Q (First):** Shapes the tone, applies bass boosts, scoops mud, and spectrally tames harsh resonance peaks. Must sit first so its negative output headroom trim (`-9 dB` to `-22 dB`) creates clean digital headroom before other processing.
  - **2. Pro-R 2 (Middle - Optional):** Injects subtle room acoustics or spatial width. Placed after Pro-Q so reverb reflections are applied to a clean, sculpted signal rather than boomy low-end mud.
  - **3. Pro-L 2 (Last - Mandatory):** The final unbreakable safety guardrail (`-1.0 dBTP`). Safely restores full commercial listening loudness via its Gain slider and prevents DAC clipping. *(Equalizing after a limiter causes instant digital distortion).*
- **Active Real-Time Spectral Dynamics:** Powered by Pro-Q's intelligent spectral dynamic processing on **Band 8 (4 kHz)** and **Band 9 (8 kHz)**. Rather than bluntly pulling down the entire frequency bell when triggered, Spectral mode splits the band into dense micro-frequency bins to surgically suppress only the exact piercing resonance (like harsh vocal "S" sibilance or cymbal bite), leaving the surrounding musical warmth and air completely untouched.
- **Preset Locations:** Ready-to-load `.ffp` files are provided in [`presets/IEMS/`](FabFilter/Pro-Q/presets/IEMS/), [`presets/Headphones/`](FabFilter/Pro-Q/presets/Headphones/), and [`presets/Speakers/`](FabFilter/Pro-Q/presets/Speakers/).

##### Tier 1A: In-Ear Monitors (IEMs Pro-Q Reference)
*Engineered for in-ear monitors to tame close-proximity ear-canal resonances with active spectral dynamic collars across all four profiles ($Q = 1.00$):*

| Band / Role | Frequency | Filter Shape | Q Factor | Balanced | Punchy Bass | Heavy Bass | Extreme Sub-Bass |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Output**<br>*(Headroom)* | — | **Output Trim** | — | $\mathbf{\color{#8b5cf6}-9.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-11.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-14.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-22.0\text{ dB}}$ |
| **1**<br>*(Sub-Bass)* | **32 Hz** | Low Shelf | `1.00` | $\mathbf{\color{#d97706}+2.6\text{ dB}}$ | $\mathbf{\color{#d97706}+4.3\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+15.0\text{ dB}}$ |
| **2**<br>*(Bass Core)* | **64 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+6.9\text{ dB}}$ | $\mathbf{\color{#d97706}+9.0\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+20.0\text{ dB}}$ |
| **3**<br>*(Upper Bass)* | **125 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+5.7\text{ dB}}$ | $\mathbf{\color{#d97706}+6.5\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+17.0\text{ dB}}$ |
| **4**<br>*(Low Mids)* | **250 Hz** | Peak / Bell | `1.00` | `+1.3 dB` | `+1.3 dB` | `+1.3 dB` | `+1.3 dB` |
| **5**<br>*(Mud Scoop)* | **500 Hz** | Peak / Bell | `1.00` | `-2.2 dB` | `-2.2 dB` | `-2.2 dB` | `-2.2 dB` |
| **6**<br>*(Core Mids)* | **1,000 Hz** | Peak / Bell | `1.00` | `-1.5 dB` | `-1.5 dB` | `-1.5 dB` | `-1.5 dB` |
| **7**<br>*(Upper Mids)* | **2,000 Hz** | Peak / Bell | `1.00` | `+2.3 dB` | `+2.3 dB` | `+2.3 dB` | `+2.3 dB` |
| **8**<br>*(Lower Treble)* | **4,000 Hz** | Peak / Bell | `1.00` | `+2.7 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-10.0\text{ dB}}$)* | `+2.7 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-8.0\text{ dB}}$)* | `+2.7 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-4.0\text{ dB}}$)* | `+2.7 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-2.0\text{ dB}}$)* |
| **9**<br>*(Upper Treble)* | **8,000 Hz** | Peak / Bell | `1.00` | `+3.0 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-4.5\text{ dB}}$)* | `+3.0 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-3.0\text{ dB}}$)* | `+3.0 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-1.0\text{ dB}}$)* | `+3.0 dB` |
| **10**<br>*(Air)* | **16,000 Hz** | High Shelf | `1.00` | `+3.8 dB` | `+3.8 dB` | `+3.8 dB` | `+3.8 dB` |

##### Tier 1B: Over-Ear Headphones (Headphones Pro-Q Reference)
*Engineered for over-ear headphones where earcups naturally diffuse treble. Features gentle spectral dynamic ducking on Balanced and Punchy Bass, and pure static treble on Heavy and Extreme Sub-Bass ($Q = 1.00$):*

|        Band / Role         |   Frequency   |  Filter Shape   | Q Factor |                            Balanced                            |                          Punchy Bass                           |                Heavy Bass                 |             Extreme Sub-Bass              |
| :------------------------: | :-----------: | :-------------: | :------: | :------------------------------------------------------------: | :------------------------------------------------------------: | :---------------------------------------: | :---------------------------------------: |
| **Output**<br>*(Headroom)* |       —       | **Output Trim** |    —     |            $\mathbf{\color{#8b5cf6}-9.0\text{ dB}}$            |           $\mathbf{\color{#8b5cf6}-11.0\text{ dB}}$            | $\mathbf{\color{#8b5cf6}-14.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-22.0\text{ dB}}$ |
|   **1**<br>*(Sub-Bass)*    |   **32 Hz**   |    Low Shelf    |  `1.00`  |            $\mathbf{\color{#d97706}+2.6\text{ dB}}$            |            $\mathbf{\color{#d97706}+4.3\text{ dB}}$            | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+15.0\text{ dB}}$ |
|   **2**<br>*(Bass Core)*   |   **64 Hz**   |   Peak / Bell   |  `1.00`  |            $\mathbf{\color{#d97706}+6.9\text{ dB}}$            |            $\mathbf{\color{#d97706}+9.0\text{ dB}}$            | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+20.0\text{ dB}}$ |
|  **3**<br>*(Upper Bass)*   |  **125 Hz**   |   Peak / Bell   |  `1.00`  |            $\mathbf{\color{#d97706}+5.7\text{ dB}}$            |            $\mathbf{\color{#d97706}+6.5\text{ dB}}$            | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+17.0\text{ dB}}$ |
|   **4**<br>*(Low Mids)*    |  **250 Hz**   |   Peak / Bell   |  `1.00`  |                           `+1.3 dB`                            |                           `+1.3 dB`                            |                 `+1.3 dB`                 |                 `+1.3 dB`                 |
|   **5**<br>*(Mud Scoop)*   |  **500 Hz**   |   Peak / Bell   |  `1.00`  |                           `-2.2 dB`                            |                           `-2.2 dB`                            |                 `-2.2 dB`                 |                 `-2.2 dB`                 |
|   **6**<br>*(Core Mids)*   | **1,000 Hz**  |   Peak / Bell   |  `1.00`  |                           `-1.5 dB`                            |                           `-1.5 dB`                            |                 `-1.5 dB`                 |                 `-1.5 dB`                 |
|  **7**<br>*(Upper Mids)*   | **2,000 Hz**  |   Peak / Bell   |  `1.00`  |                           `+2.3 dB`                            |                           `+2.3 dB`                            |                 `+2.3 dB`                 |                 `+2.3 dB`                 |
| **8**<br>*(Lower Treble)*  | **4,000 Hz**  |   Peak / Bell   |  `1.00`  | `+2.7 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-7.0\text{ dB}}$)* | `+2.7 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-5.0\text{ dB}}$)* |                 `+2.7 dB`                 |                 `+2.7 dB`                 |
| **9**<br>*(Upper Treble)*  | **8,000 Hz**  |   Peak / Bell   |  `1.00`  | `+3.0 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-3.0\text{ dB}}$)* | `+3.0 dB`<br>*(Spectral Dyn: $\mathbf{\color{#0096c7}-3.0\text{ dB}}$)* |                 `+3.0 dB`                 |                 `+3.0 dB`                 |
|     **10**<br>*(Air)*      | **16,000 Hz** |   High Shelf    |  `1.00`  |                           `+3.8 dB`                            |                           `+3.8 dB`                            |                 `+3.8 dB`                 |                 `+3.8 dB`                 |

- **Spectral Dynamic Range Mechanics (Bands 8 & 9):**
  - **Why Spectral Dynamics:** Traditional dynamic EQ pulls down the whole bell curve as a single unit when triggered. Pro-Q's **Spectral Mode** breaks the band down into hundreds of micro-frequency bins, only reducing the exact piercing harmonic (like a harsh vocal whistle or cymbal spike) while leaving adjacent frequencies untouched for unmatched clarity.
  - **In-Ear Monitors:** Static baselines remain constant at `+2.7 dB` and `+3.0 dB` while spectral dynamic range collars scale from `-10.0 dB` on *Balanced* down to `-2.0 dB` on *Extreme Sub-Bass*.
  - **Over-Ear Headphones:** Static baselines remain at `+2.7 dB` and `+3.0 dB`. Spectral dynamic ducking is tuned gentler on *Balanced* (`-7.0 dB` / `-3.0 dB`) and *Punchy Bass* (`-5.0 dB` / `-3.0 dB`), while *Heavy Bass* and *Extreme Sub-Bass* run fully static to prevent low-end acoustic masking from swallowing vocal presence.
  - **Translation to Tier 2 Static Presets:** Because standalone equalizers (Peace, EasyEffects, Equalizer314) do not have VST spectral engines, Tier 2 translates these active spectral collars into safe, fixed static cuts (`-2.6 dB` / `-0.8 dB` on IEM Balanced) to prevent ear fatigue.

##### Tier 1C: FabFilter Pro-L 2 Reference Settings (`XBEAST.ffp`)
*Configured as the final master guardrail to catch inter-sample peaks, preserve punch, and restore commercial loudness with zero clipping:*

| Parameter                        |                         Setting Value                         | Purpose & Acoustic Rationale                                                                                     |
| :------------------------------- | :-----------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------- |
| **Limiting Style**               |                         **`Modern`**                          | Smart algorithm designed for heavy 808s and modern transients; prevents low-end pumping.                         |
| **Lookahead**                    |                         **`1.0 ms`**                          | Pre-anticipates sudden peaks to curve gain down smoothly, preventing transient click distortion.                 |
| **Attack**                       |                          **`82 ms`**                          | Balances punchy kick drum and snare snap without squashing initial transient impact.                             |
| **Release**                      |                         **`450 ms`**                          | Prevents waveform chopping and bass buzz on deep 808s while avoiding unnatural volume pumping.                   |
| **Channel Linking (Transients)** |                    **`100%`** *(Default)*                     | Full stereo linking on fast peaks to keep center-stage vocal imaging locked and stable.                          |
| **Channel Linking (Release)**    |                     **`75%`** *(Default)*                     | Subtle stereo unlinking on decay recovery, enhancing natural spatial width without phase drift.                  |
| **True Peak Limiting**           |                  **`ON` (`1:1 True Peak`)**                   | Clamps inter-sample analog reconstruction peaks directly at the ceiling.                                         |
| **Oversampling**                 |                           **`4x`**                            | High-resolution anti-aliasing shield; catches inter-sample peaks transparently (~3–4 ms buffer).                 |
| **Ceiling (Out Slider)**         | **`0.0 dBTP`** *(Listening)*<br>**`-1.0 dBTP`** *(Mastering)* | Unbreakable digital roof; `0.0 dBTP` maximizes volume for playback, `-1.0 dBTP` for streaming exports.           |
| **Gain Slider**                  |          **`+2 dB to +12 dB`** *(Calibrate to Gear)*          | Adjust upward to match your DAC output voltage and IEM/headphone sensitivity (stay within 1–3 dB red meter dip). |

---

#### Tier 2: Universal Static Presets (Peace, EasyEffects, Equalizer314 & Hardware DSPs)
- **Pre-Configured Files Provided:** You do **not** need to manually configure these profiles for supported software. Ready-to-load preset files are provided directly in the repository folders:
  - **Windows:** [`Equalizer APO + Peace/`](Equalizer%20APO%20%2B%20Peace/)
  - **Linux:** [`EasyEffects/`](EasyEffects/)
  - **Android:** [`Equalizer314/`](Equalizer314/)
  - **macOS:** [`SoundSource/`](SoundSource/)
- **Universal 10-Band Static Configuration Tables:** To inspect what is inside the preset files, or to manually enter them into any standalone equalizer app or hardware DSP (such as **Equalizer314**, **Qudelix-5K**, **Poweramp Equalizer**, **Wavelet**, **WiiM Home**, or **Moondrop Link**), use the reference tables below. All bands use a universally compatible **$Q = 1.00$**:

##### Tier 2A: In-Ear Monitors (IEMs Static Reference)
*Calibrated for in-ear monitors with protective cuts on lighter profiles to prevent ear-canal fatigue ($Q = 1.00$):*

| Band / Role | Frequency | Filter Shape | Q Factor | Balanced | Punchy Bass | Heavy Bass | Extreme Sub-Bass |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Preamp**<br>*(Headroom)* | — | **Digital Preamp** | — | $\mathbf{\color{#8b5cf6}-9.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-11.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-14.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-22.0\text{ dB}}$ |
| **1**<br>*(Sub-Bass)* | **32 Hz** | Low Shelf | `1.00` | $\mathbf{\color{#d97706}+2.6\text{ dB}}$ | $\mathbf{\color{#d97706}+4.3\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+15.0\text{ dB}}$ |
| **2**<br>*(Bass Core)* | **64 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+6.9\text{ dB}}$ | $\mathbf{\color{#d97706}+9.0\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+20.0\text{ dB}}$ |
| **3**<br>*(Upper Bass)* | **125 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+5.7\text{ dB}}$ | $\mathbf{\color{#d97706}+6.5\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+17.0\text{ dB}}$ |
| **4**<br>*(Low Mids)* | **250 Hz** | Peak / Bell | `1.00` | `+1.3 dB` | `+1.3 dB` | `+1.3 dB` | `+1.3 dB` |
| **5**<br>*(Mud Scoop)* | **500 Hz** | Peak / Bell | `1.00` | `-2.2 dB` | `-2.2 dB` | `-2.2 dB` | `-2.2 dB` |
| **6**<br>*(Core Mids)* | **1,000 Hz** | Peak / Bell | `1.00` | `-1.5 dB` | `-1.5 dB` | `-1.5 dB` | `-1.5 dB` |
| **7**<br>*(Upper Mids)* | **2,000 Hz** | Peak / Bell | `1.00` | `+2.3 dB` | `+2.3 dB` | `+2.3 dB` | `+2.3 dB` |
| **8**<br>*(Lower Treble)* | **4,000 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#0096c7}-2.6\text{ dB}}$ | $\mathbf{\color{#0096c7}-0.7\text{ dB}}$ | $\mathbf{\color{#0096c7}+1.3\text{ dB}}$ | $\mathbf{\color{#0096c7}+1.9\text{ dB}}$ |
| **9**<br>*(Upper Treble)* | **8,000 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#0096c7}-0.8\text{ dB}}$ | $\mathbf{\color{#0096c7}-0.5\text{ dB}}$ | $\mathbf{\color{#0096c7}+1.8\text{ dB}}$ | $\mathbf{\color{#0096c7}+3.0\text{ dB}}$ |
| **10**<br>*(Air)* | **16,000 Hz** | High Shelf | `1.00` | `+3.8 dB` | `+3.8 dB` | `+3.8 dB` | `+3.8 dB` |

##### Tier 2B: Over-Ear Headphones (Headphones Static Reference)
*Calibrated for over-ear headphones with ear-tuned presence offsets (`+0.2 dB` to `+2.7 dB`) to maintain vocal crispness ($Q = 1.00$):*

| Band / Role | Frequency | Filter Shape | Q Factor | Balanced | Punchy Bass | Heavy Bass | Extreme Sub-Bass |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Preamp**<br>*(Headroom)* | — | **Digital Preamp** | — | $\mathbf{\color{#8b5cf6}-9.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-11.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-14.0\text{ dB}}$ | $\mathbf{\color{#8b5cf6}-22.0\text{ dB}}$ |
| **1**<br>*(Sub-Bass)* | **32 Hz** | Low Shelf | `1.00` | $\mathbf{\color{#d97706}+2.6\text{ dB}}$ | $\mathbf{\color{#d97706}+4.3\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+15.0\text{ dB}}$ |
| **2**<br>*(Bass Core)* | **64 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+6.9\text{ dB}}$ | $\mathbf{\color{#d97706}+9.0\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+20.0\text{ dB}}$ |
| **3**<br>*(Upper Bass)* | **125 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+5.7\text{ dB}}$ | $\mathbf{\color{#d97706}+6.5\text{ dB}}$ | $\mathbf{\color{#d97706}+12.0\text{ dB}}$ | $\mathbf{\color{#d97706}+17.0\text{ dB}}$ |
| **4**<br>*(Low Mids)* | **250 Hz** | Peak / Bell | `1.00` | `+1.3 dB` | `+1.3 dB` | `+1.3 dB` | `+1.3 dB` |
| **5**<br>*(Mud Scoop)* | **500 Hz** | Peak / Bell | `1.00` | `-2.2 dB` | `-2.2 dB` | `-2.2 dB` | `-2.2 dB` |
| **6**<br>*(Core Mids)* | **1,000 Hz** | Peak / Bell | `1.00` | `-1.5 dB` | `-1.5 dB` | `-1.5 dB` | `-1.5 dB` |
| **7**<br>*(Upper Mids)* | **2,000 Hz** | Peak / Bell | `1.00` | `+2.3 dB` | `+2.3 dB` | `+2.3 dB` | `+2.3 dB` |
| **8**<br>*(Lower Treble)* | **4,000 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#0096c7}+0.2\text{ dB}}$ | $\mathbf{\color{#0096c7}+0.9\text{ dB}}$ | $\mathbf{\color{#0096c7}+2.7\text{ dB}}$ | $\mathbf{\color{#0096c7}+2.7\text{ dB}}$ |
| **9**<br>*(Upper Treble)* | **8,000 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#0096c7}-0.2\text{ dB}}$ | $\mathbf{\color{#0096c7}+1.0\text{ dB}}$ | $\mathbf{\color{#0096c7}+3.0\text{ dB}}$ | $\mathbf{\color{#0096c7}+3.0\text{ dB}}$ |
| **10**<br>*(Air)* | **16,000 Hz** | High Shelf | `1.00` | `+3.8 dB` | `+3.8 dB` | `+3.8 dB` | `+3.8 dB` |

##### Tier 2C: Built-in Speakers (MacBook & Mobile Speakers Reference)
*Calibrated specifically for laptop and smartphone speakers to extract maximum body, kick presence, and dialogue clarity without exceeding tiny speaker excursion limits ($Q = 1.00$):*

| Band / Role | Frequency | Filter Shape | Q Factor | Rich Clarity | Acoustic Purpose |
| :---: | :---: | :---: | :---: | :---: | :--- |
| **Preamp**<br>*(Headroom)* | — | **Digital Preamp** | — | $\mathbf{\color{#8b5cf6}0.0\text{ dB}}$ | Unified 0 dB preamp across all platforms. |
| **1**<br>*(Sub-Bass)* | **32 Hz** | Low Shelf | `1.00` | `+0.8 dB` | Subtle foundation; small laptop cones roll off naturally below 50 Hz. |
| **2**<br>*(Bass Core)* | **64 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+5.9\text{ dB}}$ | Delivers rich kick-drum body and perceived warmth through laptop chassis. |
| **3**<br>*(Upper Bass)* | **125 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+2.1\text{ dB}}$ | Tightens bass guitar and punch without boxiness. |
| **4**<br>*(Low Mids)* | **250 Hz** | Peak / Bell | `1.00` | `+0.7 dB` | Adds natural chest weight to speech and male vocals. |
| **5**<br>*(Mud Scoop)* | **500 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+3.5\text{ dB}}$ | Compensates for laptop chassis damping and lifts fundamental vocal body. |
| **6**<br>*(Core Mids)* | **1,000 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+4.6\text{ dB}}$ | Enhances speech intelligibility and telephone clarity on mobile speakers. |
| **7**<br>*(Upper Mids)* | **2,000 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#d97706}+4.8\text{ dB}}$ | Brings vocals, instruments, and media dialogue forward in the mix. |
| **8**<br>*(Lower Treble)* | **4,000 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#0096c7}+4.3\text{ dB}}$ | Crisp consonant articulation (T, K, P sounds) cutting through room noise. |
| **9**<br>*(Upper Treble)* | **8,000 Hz** | Peak / Bell | `1.00` | $\mathbf{\color{#0096c7}+2.5\text{ dB}}$ | Open cymbal shimmer and snare crack tailored for miniature speaker grills. |
| **10**<br>*(Air)* | **16,000 Hz** | High Shelf | `1.00` | `0.0 dB` | Flat/neutral top end to avoid high-frequency amplifier hiss. |

- **Color Key:**
  - **Purple (Preamp):** Digital headroom attenuation to guarantee zero digital clipping (0 dBFS distortion) on static DSPs.
  - **Amber (Bands 1–3):** The low-end bass engine (32 Hz, 64 Hz, 125 Hz) driving sub-rumble and kick punch for each profile.
  - **Cyan (Bands 8–9):** The ear-tested static treble translations (4 kHz, 8 kHz) balancing presence against ear fatigue and acoustic masking.
- **Functional Band Roles:**
  - **Band 1 (Sub-Bass - 32 Hz):** Infrasonic chest rumble and deep physical sub feel.
  - **Band 2 (Bass Core - 64 Hz):** Kick drum body and foundational 808 note energy.
  - **Band 3 (Upper Bass - 125 Hz):** Punch, transient kick snap, and bass guitar definition.
  - **Band 4 (Low Mids - 250 Hz):** Warmth and lower harmonic weight for vocals, snares, and instruments.
  - **Band 5 (Mud Scoop - 500 Hz):** Precision cut removing hollow, boxy "cardboard" resonance.
  - **Band 6 (Core Mids - 1,000 Hz):** Subtle dip controlling nasal vocal tones and horn-like hardness.
  - **Band 7 (Upper Mids - 2,000 Hz):** Gentle lift enhancing vocal presence and intimacy.
  - **Band 8 (Lower Treble - 4,000 Hz):** Vocal consonant articulation, sibilance control, and snare snap; spectrally or statically tuned to prevent fatigue.
  - **Band 9 (Upper Treble - 8,000 Hz):** Crisp cymbal shimmer, micro-detail, and high-frequency splash.
  - **Band 10 (Air - 16,000 Hz):** High-shelf sparkle, perceived openness, and extended room decay.
- **Why Treble Offsets Differ Between IEMs and Headphones:**
  - **In-Ear Monitors:** Close acoustic coupling inside the ear canal amplifies high frequencies; gentle cuts (`-2.6 dB` / `-0.8 dB`) on lighter profiles protect against fatigue.
  - **Over-Ear Headphones:** Acoustic ear-cups diffuse highs naturally; gentle boosts or neutral tuning (`+0.2 dB` / `-0.2 dB` on Balanced, `+0.9 dB` / `+1.0 dB` on Punchy Bass) preserve openness and air without harshness.
- **Preamp Warning & Headroom Calibration:** Always apply an appropriate negative digital **Preamp** value to avoid digital clipping (0 dBFS distortion) in static DSP environments:
  - **Unified Master Headroom (`-9.0 dB`, `-11.0 dB`, `-14.0 dB`, `-22.0 dB`):** All static DSP presets (Peace GUI, EasyEffects, Equalizer314) are unified to mathematical worst-case headroom attenuation matching peak filter boosts 1:1. This guarantees zero clipping on fully uncompressed 0 dBFS signals, prevents Windows' hidden limiter (`CAudioLimiter`) from causing dynamic pumping, and ensures that screen recordings (OBS, Discord, ShadowPlay) are 100% clean with zero buzz or crackle.
  - **Volume Compensation:** If additional volume is required for quiet music after applying headroom preamps, raise your Windows master volume or hardware amplifier first. On Windows, you can also add a toggleable Preamp block in Equalizer APO Configuration Editor (`+` $\rightarrow$ **Basic filters** $\rightarrow$ **Preamp**) to easily switch extra gain ON for listening and OFF before recording.

---

### Headphone vs. IEM vs. Speaker Tuning Differences
- **In-Ear Monitors (`presets/IEMS/`):** Engineered for in-ear seals with active spectral dynamics (Pro-Q) and protective static treble cuts (Static DSPs) on Bands 8 and 9 to eliminate coupler sibilance and ear fatigue.
- **Over-Ear Headphones (`presets/Headphones/`):** Engineered for physical earcup diffusion. Spectral dynamics are applied gently on everyday profiles and disabled entirely on high-excursion bass profiles, while static DSPs feature positive presence offsets (`+0.2 dB` to `+2.7 dB`) to maintain crisp vocal clarity over massive bass.
- **Built-in Speakers (`presets/Speakers/`):** Engineered for small transducer physics (MacBook and smartphone speakers). Bypasses non-reproducible sub-bass rumble (<30 Hz) while elevating kick body at 64 Hz and boosting the vocal core (500 Hz – 4 kHz) to cut through background noise with crystal-clear dialogue clarity in our **Rich Clarity** tuning.

---

## Hearing Safety & Preset Switching Best Practice

Because presets use different levels of pre-amp trimming to protect digital headroom:

> [!WARNING]  
> **Volume Jump Warning:**  
> When switching from an extreme profile (**`Extreme Sub-Bass`**) back to an everyday profile (**`Balanced`**), the vocals and midrange will sound noticeably louder because `Balanced` requires less pre-amp trimming. If you raised your amp volume on `Extreme Sub-Bass`, switching directly to `Balanced` can cause a sudden volume jump.

### How to Protect Your Ears:
1. **Always Keep Pro-L 2 in the Chain:** Set Pro-L 2's **Ceiling to `-0.1 dBTP` to `0.0 dBTP`** for listening (or **`-1.0 dBTP`** for music mastering) with **True Peak `ON`**. Even if you switch presets, Pro-L 2 acts as an instant digital airbag—it clamps peak overshoots so audio *physically cannot exceed the ceiling* or damage your hardware.
2. **Use Pro-Q's "Lock Output" Feature:** If you want to preview and switch between all presets without the volume jumping at all, right-click (or **`Control + Click`** on macOS trackpads) the **Output** knob/slider in FabFilter Pro-Q and select **"Lock Output Level"**. The EQ curves will change while your output volume stays perfectly fixed.
3. **Turn Down Volume First:** When testing presets for the first time, lower your master listening volume slightly before jumping between Tier 1 and Tier 2 profiles.



