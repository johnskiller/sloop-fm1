<p align="center"><img src="assets/logo/bubba-logo.png" alt="Bubba" width="420"></p>

<p align="center"><b>A live groovebox firmware for the M-VAVE FM-1.</b><br>
Free and open source (GPL-3.0), made from <a href="https://github.com/isod89/sloop-fm1">SLOOP</a> by isod89 and
<a href="https://github.com/hugelton/Felucca">Felucca</a> by Leo Kuroshita / Hügelton Instruments.</p>

<p align="center">
<a href="MANUAL_BUBBA.md">Manual (español)</a> ·
<a href="SLOOP.md">SLOOP's manual (the controls Bubba keeps)</a> ·
<a href="web/editor.html">Web editor</a>
</p>

---

Bubba turns the FM-1 into an eight-track groovebox you play live: **seven synths and a drum machine**, 11 engines, 82 sounds, 38 drum kits plus three of your own, a **SAMPLER** (load a recording from the editor, cut it into
chops on the device, play them on 16 pads, sequence them like the drums) and a **looper on every track**. No factory patterns, nothing to load: everything you hear, you play.

> **Status:** 2.0. Install at your own risk. **2.0 is a clean break: its first boot erases everything stored on the
> FM-1** (projects, samples, presets, settings, the knob calibration) and reads nothing older. From 2.0 on, updates
> keep your data.

## What Bubba adds

| | |
| --- | --- |
| **Screens (2.0)** | Every screen is made the same way: a header (transport, BPM, beats, where you are, the track), one module (steps, lanes, wave, pads, tracks, lists, curves), a strip that shows the screen's own keys, and the four knobs at the bottom, each always in its colour. The keys' jobs and their hints come from one table (`ui_keys.def`) |
| **8 tracks** | 7 synths + drums; 8 voices shared, up to 4 a track; ANALOG's UNISON on one voice |
| **SAMPLER** | A SLICE track's own screen (EDIT): CHOP (the waveform, start / end, cuts tapped on the device, ZOOM, AUTO, FIT to 1–8 bars), PADS (16 pads, each with its tune, level, play mode, direction; recorded with REC), STEP (a pad's steps, as the drum grid). The audio comes whole from the web editor (3 slots × 92 KB, 11.7 s at 16 kHz) |
| **Looper** | On every synth track, RC style: REC → PLAY → DUB → PLAY, start on the bar or the beat, stop / start on the bar (OCT−), hold REC to clear (undo brings it back), SMPL: a SLICE loop fitted to the bars |
| **Drums** | On the drum screen: black 11 tapped mutes the picked sound, held shows the 16 sounds to mute with the white keys; KNOB 2 sets each sound's volume; a step held + KNOB 2 its level (ghost, soft, norm, acc). Off the drum screen the keys are live pads; REC records each pad on its own line. Felucca's five analog kits (F.80 F.10 F.66 F.55 F.77, its `drum_voice.c`) next to ACOUSTIC and the 32 synthesised kits; USR1–USR3: a slot as your kit |
| **FM6** | SLOOP 2.4's six-operator FM (msfa, Apache-2.0): 32 algorithms, 9 factory patches (FM VIBES in VIBES' place), a bank of 27, DX7 SysEx import / export in the web editor; on two tracks at a time |
| **Chords (2.0)** | The chord you hold is shown (its name, the CHORD+ modifiers, its notes on a keyboard); a step's chord is edited whole: MOVE by scale degrees, TYPE (triad, 7th, 9th, sus4, power), INV |
| **Small controls** | A synth step's chance (SEQ + a step held + PRESETS), SEQ TOOLS on SEQ + black 5–9 (SHIFT, REVERSE, RANDOM, COOK), MIDI controllers (GLIDE, LEVEL, PAN, ENV, FILTER, sends), pitch bend, sustain |
| **Sounds** | Felucca's tenor SAX built in (TENOR SAX, SAX BREATH); a pack builder for the slots (`tools/make_pack.py`: the whole SAX, the scratches) |
| **From SLOOP 2.4 / Felucca 1.1.5** | A filter per track (FILT), CHORD+ (black keys: minor, 7, sus4, 9, inversion; STRUM; voice leading), NUDGE per step, fills, quick chain of sections, steps of 1/2, 1 and 2 bars, dotted delays, MIDI IN = CLOCK only, MIDI OUT = SEQ, the USB console off by default, an installer that checks the whole package before it erases anything, and their fixes |
| **Format** | Bubba 2.0's own, every object versioned (an update migrates it): 4 projects A–D with the 8 tracks, the autosave, 32 user presets, the sample edits, the FM6 bank |

Everything is in the [manual](MANUAL_BUBBA.md) (Spanish).

## Build and test

| | |
| --- | --- |
| `py -3 tools/docker_build.py fw` | The firmware: `build/felucca.fwsc` (JieLi toolchain in Docker) |
| `py -3 tools/docker_build.py test` | Every host test (`tests/run_tests.sh`), including `slice_test` and `looper_test` |
| `py -3 tools/emulator/build_emu.py` | The Windows emulator (MSVC): the real firmware over an emulated HAL (`LAUNCH-EMULATOR.bat`) |
| `py -3 web/make_site.py build/felucca.fwsc 2.0 OUT` | The installer site (Web MIDI, Chrome / Edge) |
| `py -3 tools/fw_sizes.py` | Flash per function and source file (from `build/felucca.dis`; `--diff` between builds) |
| `py -3 tools/ppm_diff.py A B` · `tools/ppm_sheet.py` | Compare the screens the UI tests capture; a contact sheet of them |
| `py -3 tools/fm1_cpu.py 90` | CPU on the FM-1 for 90 s (menu → USB SERIAL on, replug) |

Memory: flash 564,436 of 581,564 B; RAM 93,472 of 98,304 B (the user presets are read from flash).

## Credits

- **SLOOP** — isod89, [github.com/isod89/sloop-fm1](https://github.com/isod89/sloop-fm1) (GPL-3.0).
- **Felucca** — Leo Kuroshita (@kurogedelic), [Hügelton Instruments](https://hugelton.com),
  [github.com/hugelton/Felucca](https://github.com/hugelton/Felucca) (GPL-3.0): the firmware Bubba stands on, the
  analog kits, the SAX, the FM6 port.
- **FM6** — msfa (Google, Pascal Gauthier / Dexed), Apache-2.0: `LICENSES/Apache-2.0-msfa.txt`.
- **Samples** — Versilian Studios VSCO-2 CE and VCSL (CC0); the scratch pack: the Sonic Pi sample set (CC0).
  See `assets/samples-cc0/CREDITS.txt`.
- **Font** — Terminus (SIL OFL 1.1). **PHASE** — CrispyZebra (GPL). **VOICE** — after klattsch (MIT).
- **Bubba** — Erick Buendía Barrientos.

M-VAVE and FM-1 are trademarks of their respective owners; Bubba is not affiliated with them.

## Licence

GPL-3.0-only, no warranty. See [LICENSE](LICENSE).
