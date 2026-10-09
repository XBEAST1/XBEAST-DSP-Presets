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
│   └── XBEAST (IEMs) - Extreme Sub-Bass.json
│
├── Equalizer APO + Peace/
│   ├── XBEAST (Headphones) - Balanced.peace
│   ├── XBEAST (Headphones) - Punchy Bass.peace
│   ├── XBEAST (Headphones) - Heavy Bass.peace
│   ├── XBEAST (Headphones) - Extreme Sub-Bass.peace
│   ├── XBEAST (IEMs) - Balanced.peace
│   ├── XBEAST (IEMs) - Punchy Bass.peace
│   ├── XBEAST (IEMs) - Heavy Bass.peace
│   └── XBEAST (IEMs) - Extreme Sub-Bass.peace
│
├── Equalizer314/
│   ├── XBEAST (Headphones) - Balanced.json
│   ├── XBEAST (Headphones) - Punchy Bass.json
│   ├── XBEAST (Headphones) - Heavy Bass.json
│   ├── XBEAST (Headphones) - Extreme Sub-Bass.json
│   ├── XBEAST (IEMs) - Balanced.json
│   ├── XBEAST (IEMs) - Punchy Bass.json
│   ├── XBEAST (IEMs) - Heavy Bass.json
│   └── XBEAST (IEMs) - Extreme Sub-Bass.json
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
    │   │   └── IEMs/
    │   │       ├── XBEAST - Balanced.ffp
    │   │       ├── XBEAST - Punchy Bass.ffp
    │   │       ├── XBEAST - Heavy Bass.ffp
    │   │       └── XBEAST - Extreme Sub-Bass.ffp
    │   ├── screenshots/
    │   └── GUIDE.md
    │
    ├── Pro-R2/
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
  - **`XBEAST (Headphones) - Balanced.peace`**, **`Punchy Bass.peace`**, **`Heavy Bass.peace`**, **`Extreme Sub-Bass.peace`**: Calibrated with ear-tuned presence offsets (`+0.2 dB` to `+2.7 dB`) and adjusted listening preamps (`-2 dB` to `-10 dB`) to deliver punchy, distortion-free output volume on over-ear cans.
- **In-Ear Monitor (IEM) Profiles (`.peace`):**
  - **`XBEAST (IEMs) - Balanced.peace`**, **`Punchy Bass.peace`**, **`Heavy Bass.peace`**, **`Extreme Sub-Bass.peace`**: 10-band static profiles matching the Tier 2A master specification with ear-safe preamps (`-2 dB` to `-10 dB`).
- **How to Install into Peace GUI:**
  - Copy the `.peace` files into your Equalizer APO configuration directory:
    ```
    C:\Program Files\EqualizerAPO\config
    ```
  - Open **Peace GUI**, and your profiles will be automatically available in the preset list.
- **Windows Audio Architecture & The "Hidden Limiter":** Windows 10 and 11 feature an integrated, low-overhead system limiter (`CAudioLimiter` inside the WASAPI shared audio engine). When audio peaks approach `0 dBFS`, Windows applies dynamic peak control rather than harsh digital clipping (square-wave flat tops). This architectural safeguard—combined with the fact that commercial music rarely peaks at full scale across pure sub-bass—allows our Peace presets to utilize practical listening preamps (`-2 dB` to `-10 dB`) to deliver loud, punchy volume through USB DAC dongles and high-impedance headphones without audible crackle.

### 3. Equalizer314 (Android)
System-wide parametric equalization profiles for **Equalizer314** (open-source Android equalizer powered by Android's native `DynamicsProcessing` architecture):
- **Over-Ear Headphones Profiles (`.json`):**
  - **`XBEAST (Headphones) - Balanced.json`**, **`Punchy Bass.json`**, **`Heavy Bass.json`**, **`Extreme Sub-Bass.json`**: Tuned with ear-cup presence offsets (`+0.2 dB` to `+2.7 dB`) to maintain crisp vocal articulation over powerful low-end excursions.
- **In-Ear Monitor (IEM) Profiles (`.json`):**
  - **`XBEAST (IEMs) - Balanced.json`**, **`Punchy Bass.json`**, **`Heavy Bass.json`**, **`Extreme Sub-Bass.json`**: Calibrated for direct ear-canal insertion with protective treble tuning matching the Tier 2A master specification.
- **Technical Specifications:**
  - **Filter Topology:** 10 parametric bands ($Q = 1.00$). Band 1 is `LOW_SHELF`, Bands 2–9 are `BELL`, and Band 10 is `HIGH_SHELF`.
  - **Headroom Protection:** Integrated digital preamp attenuation (`-9 dB` on Balanced, `-11 dB` on Punchy Bass, `-14 dB` on Heavy Bass, and `-20 dB` on Extreme Sub-Bass) matching peak filter boosts to guarantee zero `0 dBFS` clipping across Android's audio pipeline.
- **How to Import into Equalizer314:**
  1. Download or copy the desired `.json` files to your Android device (e.g., your device's `Download/` folder).
  2. Launch **Equalizer314** and open the **Presets** menu (or tap the preset icon on the main interface).
  3. Select **Import**, choose the `.json` profile corresponding to your listening gear (Headphones or IEMs), and apply.

### 4. SoundSource (macOS)
System-wide audio control on macOS via Rogue Amoeba's **SoundSource**:
- **`Presets.plist`**: Custom EQ presets file containing 6 universal 10-Band EQ profiles aligned with Tier 2 static specifications:
  - **Over-Ear Headphones:** `XBEAST (Headphones) - Balanced`, `Punchy Bass`, and `Heavy Bass`.
  - **In-Ear Monitors (IEMs):** `XBEAST (IEMs) - Balanced`, `Punchy Bass`, and `Heavy Bass`.
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
- **[Pro-Q](FabFilter/Pro-Q/GUIDE.md)**: Beginner's guide to massive bass, dynamic precision, and clean sound. Covers the "Water Glass" headroom principle, 32-bit float vs DAC fixed-point limits, why 8–10 bands is optimal for IEMs (avoiding 16–32 band phase smearing & pre-ringing), Dynamic EQ mechanics (taming sibilance, harsh plate reverbs, and boomy drops), and real-time live DSP routing chains for SoundSource (macOS) and Equalizer APO (Windows).
- **[Pro-L 2](FabFilter/Pro-L/GUIDE.md)**: Beginner's guide to loud, punchy, and distortion-free sound. Explains what a limiter does, how **Attack** (drum punch vs. flatness) and **Release** (waveform buzz vs. volume pumping) work when turning them up or down, the 3 essential settings (Ceiling, Gain sweet spot, Modern style), and a 5-scenario problem solver.
- **[Pro-R 2](FabFilter/Pro-R2/GUIDE.md)**: Plain-English guide to professional reverb space. Breaks down the Blue vs. Yellow curve ("The Stopwatch vs. The Volume Slider"), all 10 core dials with physical analogies, a massive IF/THEN decision engine for fixing muddy bass, harsh sibilance, and boxy vocals, 5 scenario presets, and the 10-second solo ear test.
- **Pro-C**: Compressor guide and presets (coming soon).

---

## Tested Hardware & Audiophile Chain

These profiles and FabFilter presets have been tested and calibrated on the following reference hardware:

| Component | Hardware | Architecture & Sonic Characteristics |
| :--- | :--- | :--- |
| **DAC / Amp** | **JCALLY JM98MAX** | Cirrus Logic **CS43198** 32-bit DAC paired with an **SGM8262** dual operational amplifier. Delivers ~195 mW @ 32Ω with ~0.65Ω output impedance, 125 dB SNR, and 0.0003% THD+N. Supports PCM decoding up to 32-bit/384 kHz and native DSD256. |
| **In-Ear Monitors (IEMs)** | **KZ Castor Improved Bass Edition** | Stacked dual dynamic driver configuration with a 10mm dual-magnetic composite driver dedicated to 20–200 Hz low frequencies alongside an 8mm driver handling midrange and treble. Built with an integrated 2-way electronic crossover, independent acoustic chambers, and 4-stage hardware tuning dip switches. |
| **Over-Ear Headphones** | **HyperX Cloud III** | Closed-back circumaural headphones utilizing angled 53mm dynamic drivers with neodymium magnets. Features a 64Ω nominal impedance and a 10 Hz – 21 kHz frequency response within sealed acoustic ear-cup enclosures. |

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
2. **Check Pro-L 2 Basics:** Ensure **Ceiling** is at **`-1.0 dBTP`**, **Style** is set to **`Modern`**, and **`1:1 True Peak`** is **ON**.
3. **Adjust the Gain Slider:** Slowly push the Pro-L 2 **Gain slider** upward until the music reaches your ideal loudness.
4. **Watch the Top Red Meter:** On the loudest bass hits and drops, the red gain reduction meter at the top of Pro-L 2 should dip by **`1 dB to 3 dB`** (the sweet spot). If it is constantly dipping by `6 dB+`, pull the Gain slider back down slightly to keep your transients dynamic and punchy.

---

## Preset Architecture & Listening Tiers

The presets in this repository are structured across two dimensions: **Sound Signature Curves** (bass level) and **DSP Platform Tiers** (dynamic vs. static).

### 1. Sound Signature Curves

| Category | Presets | Sonic Character & Target |
| :--- | :--- | :--- |
| **Everyday & Audiophile** | **`Balanced`**, **`Punchy Bass`** | Controlled sub-bass and dynamic kick-drum punch. Vocal-forward and clean across all genres. |
| **High-Excursion Bass** | **`Heavy Bass`**, **`Extreme Sub-Bass`** | Deep sub-bass wall and infrasonic car-subwoofer rumble (+12 dB to +20 dB boost). |

---

### 2. DSP Platform Tiers: Active Dynamic vs. Universal Static

To ensure the best possible sound across all platforms from desktop VST hosts to mobile equalizers and dedicated hardware DACs:

#### Tier 1: FabFilter Suite (Master Gold Standard)
- **The Ultimate Experience:** Hosted via **SoundSource** (macOS) or **Equalizer APO VST** (Windows).
- **Active Real-Time Dynamic EQ:** Features intelligent dynamic range ducking on **Band 8 (4 kHz)** and **Band 9 (8 kHz)**. Treble remains crisp, airy, and uncompressed during quiet moments, but automatically ducks by the specified dynamic range the instant a harsh vocal "S", piercing cymbal, or loud snare spike hits.
- **Paired with Pro-L 2:** True Peak limiter restores full commercial loudness safely with zero low-end buzz or distortion.
- **Preset Locations:** Ready-to-load `.ffp` files are provided in [`presets/IEMs/`](FabFilter/Pro-Q/presets/IEMs/) and [`presets/Headphones/`](FabFilter/Pro-Q/presets/Headphones/).

##### Tier 1A: In-Ear Monitors (IEMs Pro-Q Reference)
*Engineered for in-ear monitors to tame close-proximity ear-canal resonances with active dynamic collars across all four profiles ($Q = 1.00$):*

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
| **8**<br>*(Lower Treble)* | **4,000 Hz** | Peak / Bell | `1.00` | `+2.7 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-10.0\text{ dB}}$)* | `+2.7 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-8.0\text{ dB}}$)* | `+2.7 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-4.0\text{ dB}}$)* | `+2.7 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-2.0\text{ dB}}$)* |
| **9**<br>*(Upper Treble)* | **8,000 Hz** | Peak / Bell | `1.00` | `+3.0 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-4.5\text{ dB}}$)* | `+3.0 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-3.0\text{ dB}}$)* | `+3.0 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-1.0\text{ dB}}$)* | `+3.0 dB` |
| **10**<br>*(Air)* | **16,000 Hz** | High Shelf | `1.00` | `+3.8 dB` | `+3.8 dB` | `+3.8 dB` | `+3.8 dB` |

##### Tier 1B: Over-Ear Headphones (Headphones Pro-Q Reference)
*Engineered for over-ear headphones where earcups naturally diffuse treble. Features gentle dynamic ducking on Balanced and Punchy Bass, and pure static treble on Heavy and Extreme Sub-Bass ($Q = 1.00$):*

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
| **8**<br>*(Lower Treble)*  | **4,000 Hz**  |   Peak / Bell   |  `1.00`  | `+2.7 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-7.0\text{ dB}}$)* | `+2.7 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-5.0\text{ dB}}$)* |                 `+2.7 dB`                 |                 `+2.7 dB`                 |
| **9**<br>*(Upper Treble)*  | **8,000 Hz**  |   Peak / Bell   |  `1.00`  | `+3.0 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-3.0\text{ dB}}$)* | `+3.0 dB`<br>*(Dyn: $\mathbf{\color{#0096c7}-3.0\text{ dB}}$)* |                 `+3.0 dB`                 |                 `+3.0 dB`                 |
|     **10**<br>*(Air)*      | **16,000 Hz** |   High Shelf    |  `1.00`  |                           `+3.8 dB`                            |                           `+3.8 dB`                            |                 `+3.8 dB`                 |                 `+3.8 dB`                 |

- **Dynamic Range Mechanics (Bands 8 & 9):**
  - **In-Ear Monitors:** Static baselines remain constant at `+2.7 dB` and `+3.0 dB` while dynamic range collars scale from `-10.0 dB` on *Balanced* down to `-2.0 dB` on *Extreme Sub-Bass*.
  - **Over-Ear Headphones:** Static baselines remain at `+2.7 dB` and `+3.0 dB`. Dynamic ducking is tuned gentler on *Balanced* (`-7.0 dB` / `-3.0 dB`) and *Punchy Bass* (`-5.0 dB` / `-3.0 dB`), while *Heavy Bass* and *Extreme Sub-Bass* run fully static to prevent low-end acoustic masking from swallowing vocal presence.

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
  - **Band 8 (Lower Treble - 4,000 Hz):** Vocal consonant articulation, sibilance control, and snare snap; dynamically or statically tuned to prevent fatigue.
  - **Band 9 (Upper Treble - 8,000 Hz):** Crisp cymbal shimmer, micro-detail, and high-frequency splash.
  - **Band 10 (Air - 16,000 Hz):** High-shelf sparkle, perceived openness, and extended room decay.
- **Why Treble Offsets Differ Between IEMs and Headphones:**
  - **In-Ear Monitors:** Close acoustic coupling inside the ear canal amplifies high frequencies; gentle cuts (`-2.6 dB` / `-0.8 dB`) on lighter profiles protect against fatigue.
  - **Over-Ear Headphones:** Acoustic ear-cups diffuse highs naturally; gentle boosts or neutral tuning (`+0.2 dB` / `-0.2 dB` on Balanced, `+0.9 dB` / `+1.0 dB` on Punchy Bass) preserve openness and air without harshness.
- **Preamp Warning & Headroom Calibration:** Always apply an appropriate negative digital **Preamp** value to avoid digital clipping (0 dBFS distortion) in static DSP environments:
  - **Peace GUI Presets (Listening Calibrated via Windows Audio Engine):** Configured with listening preamps (`-2.0 dB` on Balanced, `-3.5 dB` on Punchy Bass, `-6.0 dB` on Heavy Bass, and `-10.0 dB` on Extreme Sub-Bass). Because Windows 10 and 11 feature an internal system limiter (`CAudioLimiter` in WASAPI shared mode) and commercial tracks rarely push 0 dBFS across sustained sub-bass, these preamps deliver maximum punch and volume on headphones without harsh digital distortion or volume pumping.
  - **EasyEffects & Equalizer314 Presets & Reference Tables (Mathematical Headroom):** EasyEffects and Equalizer314 integrate mathematical worst-case headroom attenuation (`-9.0 dB`, `-11.0 dB`, `-14.0 dB`, and `-22.0 dB` matching peak filter boosts 1:1) paired with brickwall limiter protection to guarantee zero clipping even on fully uncompressed 0 dBFS test tones.

---

### Headphone vs. IEM Tuning Differences
- **In-Ear Monitors (`presets/IEMs/`):** Engineered for in-ear seals with active dynamic ducking (Pro-Q) and protective static treble cuts (Static DSPs) on Bands 8 and 9 to eliminate coupler sibilance and ear fatigue.
- **Over-Ear Headphones (`presets/Headphones/`):** Engineered for physical earcup diffusion. Dynamic EQ is applied gently on everyday profiles and disabled entirely on high-excursion bass profiles, while static DSPs feature positive presence offsets (`+0.2 dB` to `+2.7 dB`) to maintain crisp vocal clarity over massive bass.

---

## Hearing Safety & Preset Switching Best Practice

Because presets use different levels of pre-amp trimming to protect digital headroom:

> [!WARNING]  
> **Volume Jump Warning:**  
> When switching from an extreme profile (**`Extreme Sub-Bass`**) back to an everyday profile (**`Balanced`**), the vocals and midrange will sound noticeably louder because `Balanced` requires less pre-amp trimming. If you raised your amp volume on `Extreme Sub-Bass`, switching directly to `Balanced` can cause a sudden volume jump.

### How to Protect Your Ears:
1. **Always Keep Pro-L 2 in the Chain:** Set Pro-L 2's **Ceiling to `-1.0 dBTP`** with **True Peak `ON`**. Even if you switch presets, Pro-L 2 acts as an instant digital airbag it clamps peak overshoots so audio *physically cannot exceed -1.0 dBTP* or damage your hardware.
2. **Use Pro-Q's "Lock Output" Feature:** If you want to preview and switch between all presets without the volume jumping at all, right-click the **Output** slider in FabFilter Pro-Q and select **"Lock Output Level"**. The EQ curves will change while your output volume stays perfectly fixed.
3. **Turn Down Volume First:** When testing presets for the first time, lower your master listening volume slightly before jumping between Tier 1 and Tier 2 profiles.



