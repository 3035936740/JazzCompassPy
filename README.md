# JazzCompass

**The Digital Grimoire for Jazz Theory and Improvisation.**

`jazz_compass.py` is a comprehensive Python-based harmonic engine designed for jazz musicians, composers, and software developers. It bridges the gap between traditional music theory and algorithmic analysis, providing tools for **Chord-Scale Theory (CST)**, **Lydian Chromatic Concept (LCC)**, **Blues Toolkit**, **Negative Harmony**, and **Functional Progression Analysis**.

---

## Key Features

### 1. Advanced Chord Parsing (`ChordConverter`)

* **Extensive Library**: Supports over 60 chord types including extensions (`7#5b9`, `maj13`, `m-maj7`).
* **Slash Chord Support**: Accurately handles inversions and upper structures (e.g., `D/C`, `F/G`).
* **Enharmonic Intelligence**: Automatically standardizes sharps and flats for consistent internal logic.

### 2. Chord-Scale Theory (`CSTAnalyzer`)

* **Mode Matching**: Instantly find matching scales (Ionian, Lydian, Dorian, Altered, etc.) for any given chord.
* **Tension Analysis**: Automatically categorizes scale notes into **Available Tensions** or **Avoid Notes** (minor 9th dissonance detection).
* **Brightness Scoring**: Ranks scales based on their displacement on the Circle of Fifths.

### 3. Lydian Chromatic Concept (`LCCAnalyzer`)

* **Gravitational Logic**: Implements George Russell's LCC to find "Parent Lydian" scales.
* **Ingoing vs. Outgoing**: Ranks improvisation options by their "tonal gravity," allowing for both consonant and "outside" modern sounds.

### 4. Blues Toolkit (`BluesToolkit`)

* **Core Features**: Intelligent Scale Recommendation: Recommends parallel or relative scales based on a chord's characteristic notes (such as major third, minor seventh, #11, etc.). Supports various jazz-blues colors including Lydian Dominant, Mixolydian Blues, and Minor Blues.
* **Specific Note Generation**: Automatically translates scale theory into concrete lists of notes, making it easy for musicians to locate the notes directly on their fretboard or keyboard.
* **Tonal Color Analysis (analyze_improv_feel)**: Automatically calculates a "spiciness level" (from safe to experimental) by comparing the scale notes with the chord notes, and highlights the "tension notes" that create friction.

### 5. Geometric Harmony & Linkage Engine (`NeoRiemannianToolkit`)

This module moves beyond traditional functional harmony (like $ii-V-I$) to explore **Voice Leading** and **Tonnetz** geometry. It is designed to find "cinematic" and "smooth" transitions that are mathematically related but tonally distant.

* **Core Transformations (P, L, R)**:
* **P (Parallel)**: Connects major and minor chords with the same root (e.g., $C \leftrightarrow Cm$).
* **L (Leading-tone exchange)**: Connects chords sharing a major third (e.g., $C \leftrightarrow Em$).
* **R (Relative)**: Connects relative major/minor pairs (e.g., $C \leftrightarrow Am$).


* **Advanced Geometric Mapping**:
* **Tonnetz Navigation**: Includes **S (Slide)** transformations (e.g., $C \leftrightarrow C\#m$) and **N (Near)** relations for sophisticated modulations.
* **Symmetrical Hubs**: Utilizes **Augmented** and **Diminished** pivots to transition between distant keys instantaneously.


* **Octatonic Tower**:
* A specialized logic for 4-note chords (e.g., $m7b5$, $dim7$). It leverages the symmetry of the **Octatonic Scale** to find "geometric neighbors" that maintain a consistent tension profile.

---

## Quick Start

### Installation

No external dependencies required. Simply import the module into your Python environment.

```python
from jazz_compass import JazzBrain

# Initialize the engine
jazz = JazzBrain()

# 1. Generate a full harmonic report for a complex chord
jazz.get_full_report("F#m7b5")

# 2. Analyze a professional chord progression
progression = ["Cmaj7", "Ebdim7", "Dm7", "G7"]
key = jazz.find_key_center_pro(progression)
print(f"Analysis: {key}") 
# Output: Recommended Key: C Major (Ionian)

# 3. Transform a chord via Negative Harmony
neg_chord = jazz.to_negative("G7", axis="C")
print(f"Negative G7: {neg_chord}")

```

---

## Visualizer

The built-in terminal visualizer allows you to see the chord geometry immediately:

```text
=== Abmaj7 Jazz Report ===
Piano Visualization:
C   C#  D   D#  E   F   F#  G   G#  A   A#  B 
● | - | - | ● | - | - | - | ● | ● | - | - | - 

```

---

## Project Structure

| Class | Responsibility |
| --- | --- |
| `ChordConverter` | String regex parsing & interval calculation. |
| `CSTAnalyzer` | Scale definitions, brightness, and avoid-note logic. |
| `LCCAnalyzer` | Tonal gravity and Parent Lydian organization. |
| `BluesToolkit` | Improvisation guide: Blues/Pentatonic suggestions & Tension (Spiciness) analysis. |
| `JazzBrain` | The "API Layer" combining all modules for end-user reports. |

---

## License

Distributed under the **MIT License**. Feel free to use this in your DAWs, educational apps, or personal practice tools.