# XBEAST DSP Presets

Curated audio DSP presets, tuning profiles, and engineering guides for cross-platform sound optimization and mastering.

---

## Repository Structure

```
XBEAST-DSP-Presets/
├── README.md
│
├── EasyEffects/
│   ├── Reverb.json
│   ├── Tight Bass.json
│   ├── Tight Bass 2.json
│   └── Tight Bass 3.json
│
├── Equalizer APO + Peace/
│   ├── Presets/
│   │   ├── Bass Boosted.peace
│   │   ├── config.txt
│   │   ├── Gaming Bass.peace
│   │   └── Gaming.peace
│   ├── Presets Directory.txt
│   └── Tested On.txt
│
├── JamesDSP Rootless/
│   ├── XBEAST V1.tar
│   ├── XBEAST V1 BASS.tar
│   ├── XBEAST V2.tar
│   └── XBEAST V2 BASS.tar
│
├── Mac OS/
│   ├── Directory.txt
│   └── Sound Source/
│       └── Presets.plist
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
    ├── Pro-C/
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
Presets designed for **EasyEffects** (PipeWire audio processing):
- **`Reverb.json`**: General room ambiance and spatial enhancement.
- **`Tight Bass.json`**, **`Tight Bass 2.json`**, **`Tight Bass 3.json`**: Precision low-end tightening profiles delivering punchy transient impact without boominess or masking.

### 2. Equalizer APO + Peace (Windows)
System-wide parametric equalization curves for Windows:
- **`Bass Boosted.peace`**: Enhanced low-end curve for bass-heavy listening.
- **`Gaming.peace`**: Competitive sound profile tuned for footprint clarity, transient spatial localization, and reduced ear fatigue.
- **`Gaming Bass.peace`**: Hybrid profile offering competitive spatial imaging alongside satisfying cinematic low-end punch.
- **`config.txt`**, **`Presets Directory.txt`**, **`Tested On.txt`**: Installation paths, device notes, and hardware validation details.

### 3. JamesDSP Rootless (Android)
Audio profiles packaged for rootless **JamesDSP** on Android:
- **`XBEAST V1.tar`**, **`XBEAST V1 BASS.tar`**
- **`XBEAST V2.tar`**, **`XBEAST V2 BASS.tar`**
- Optimized for headphone listening, dynamic range management, and sub-bass clarity on mobile devices.

### 4. Mac OS (SoundSource)
System-wide audio control on macOS via Rogue Amoeba's **SoundSource**:
- **`Presets.plist`**: Custom EQ presets file.
- **`Directory.txt`**: Installation instructions pointing to `~/Library/Application Support/SoundSource/Presets/`.

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
| **DAC / Amp** | **JCALLY JM98MAX** | High-performance USB-C DAC/Amp dongle powered by dual Cirrus Logic CS43198 DAC chips with independent dual-channel amplification. Delivers clean power, high signal-to-noise ratio, and near-zero output impedance (<0.5 Ω) for strict damping factor control over low-frequency excursions. |
| **In-Ear Monitors (IEMs)** | **KZ Castor Pro (Bass Edition)** | Dual dynamic driver configuration featuring an independent 10mm composite magnetic driver dedicated to sub-bass, alongside an 8mm driver for mids and highs. The airtight ear-canal seal and dedicated sub-woofer driver allow presets like **`XBEAST - Heavy Bass`** and **`XBEAST - Extreme Sub-Bass`** to deliver massive, physical sub-bass pressure without causing intermodulation distortion or vocal muddiness. |
| **Over-Ear Headphones** | **HyperX Cloud III** | Closed-back over-ear headphone with angled 53mm dynamic drivers. Provides a balanced, clear soundstage with controlled low-end. Pairs exceptionally well with **`XBEAST - Balanced`** and **`XBEAST - Punchy Bass`** for punchy transient attack and long listening comfort without driver strain. |

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

The `XBEAST` Pro-Q presets are organized into two distinct listening tiers:

| Tier                              | Presets                                  | Sonic Character & Target                                                                    |
| :-------------------------------- | :--------------------------------------- | :------------------------------------------------------------------------------------------ |
| **Tier 1: Everyday & Audiophile** | **`Balanced`**, **`Punchy Bass`**        | Controlled sub-bass and dynamic kick-drum punch. Vocal-forward and clean across all genres. |
| **Tier 2: High-Excursion Bass**   | **`Heavy Bass`**, **`Extreme Sub-Bass`** | Deep sub-bass wall and infrasonic car-subwoofer rumble (+12 dB to +20 dB boost).            |

### Headphone vs. IEM Tuning Differences
- **In-Ear Monitors (`presets/IEMs/`):** Feature negative Dynamic EQ on **Band 8 (4 kHz)** and **Band 9 (8 kHz)**. Because IEMs sit directly inside the sealed ear canal, loud treble can quickly cause ear fatigue; the dynamic bands automatically tame sharp sibilance and piercing snare claps while keeping quiet passages airy and detailed.
- **Over-Ear Headphones (`presets/Headphones/`):** Feature uncompressed static treble. Over-ear headphone pads and acoustic ear-cups naturally diffuse high frequencies, so static highs are maintained to overcome acoustic masking from heavy bass and preserve energy and presence.

---

## Hearing Safety & Preset Switching Best Practice

Because presets use different levels of pre-amp trimming to protect digital headroom:

> [!WARNING]  
> **Volume Jump Warning:**  
> When switching from an extreme profile (**`Extreme Sub-Bass`**) back to an everyday profile (**`Balanced`**), the vocals and midrange will sound noticeably louder because `Balanced` requires less pre-amp trimming. If you raised your amp volume on `Extreme Sub-Bass`, switching directly to `Balanced` can cause a sudden volume jump.

### How to Protect Your Ears:
1. **Always Keep Pro-L 2 in the Chain:** Set Pro-L 2's **Ceiling to `-1.0 dBTP`** with **True Peak `ON`**. Even if you switch presets, Pro-L 2 acts as an instant digital airbag—it clamps peak overshoots so audio *physically cannot exceed -1.0 dBTP* or damage your hardware.
2. **Use Pro-Q's "Lock Output" Feature:** If you want to preview and switch between all presets without the volume jumping at all, right-click the **Output** slider in FabFilter Pro-Q and select **"Lock Output Level"**. The EQ curves will change while your output volume stays perfectly fixed.
3. **Turn Down Volume First:** When testing presets for the first time, lower your master listening volume slightly before jumping between Tier 1 and Tier 2 profiles.



