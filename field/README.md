# CHERD for the OP-1 Field (cherd.pack)

> **Read this first**
>
> - This pack is for **OP-1 Field OS 1.7.3+0** running [open-field](https://github.com/LaP0573/open-field) for
>   OS 1.7.3 (the loader and `base.pack`). It does not run on open-field's older page for 1.7.0.
> - Installing open-field changes your unit's firmware, at your own risk. Read open-field's NOTICE first.
> - **Never install 1.7.3+1.** It locks the bootloader (1000.2.0). Only 1.7.3+0 on bootloader 1000.1.1 works.
> - A pack is a program that can read and write the files on your unit: take packs only from people you trust.

## What CHERD is

CHERD is a chord sequencer for the OP-1 Field. It is a real **eighth sequencer** in TE's sequencer menu, next to
SKETCH, and does not replace anything. It plays its chords on whatever synth the track has.

- **Right hand: roots.** Each key becomes the chord that note has in your key and scale. In C major, C gives C,
  D gives Dm, G gives G.
- **Left hand: flavors.** These keys are silent. Hold one while you strike a root: major, minor, dim, sus2, sus4,
  or extensions 7th, 9th, dom7, add9, add6. ALT (the C# key) makes an altered dominant. **Spice** (the E key) plays
  the full, rich chord for that note.
- **Flow genres:** off, color, jazz, pop, soul, gospel, bossa, ambient, blues, rock, monk and **django** (gypsy jazz).
- **Strum, comp** (stab, chrl, pump, sync and **la pompe**) and an **arpeggiator**.
- **Chord names fakebook style**, hand lettered in Petaluma Script (A-6, D7(b9), G6/9), over a keyboard of dots that
  lights up the chord tones.

The two-page [quick start](CHERD-quickstart.pdf) has everything below and more.

## Install

1. Put the unit in disk mode and copy `cherd.pack` into the `packs` folder, next to `base.pack`.
2. Restart the unit.
3. In synth mode, press Shift + Sequencer and choose **CHERD**, the last entry.

- Settings are kept in `user/pf/cherd/cherd.bin`, which shows as the `cherd` folder in disk mode.
- The pick is saved in the project as `cherd`. A unit without the pack reads that as an unknown sequencer and falls
  back to ENDLESS.

## Uninstall

Delete `cherd.pack` from the `packs` folder. If anything goes wrong, hold the help key while you switch the unit
on: it starts with no packs.

## Controls in brief

The encoders are named by position: the 1st is the leftmost, the 4th the rightmost. A click is a press on the
encoder.

| Encoder | Turn | Click |
| --- | --- | --- |
| 1st | Key, round the circle of fifths | FEEL page on / off |
| 2nd | Scale: off or one of 34 | Strum: off, up, down, alt |
| 3rd | Spread: close, open, wide, bass, lead | Comp on / off |
| 4th | Flow: the genre | Arp on / off |

- **FEEL page** (1st click): smooth, swing, human; the 4th picks the comp pattern (stab, chrl, pump, sync, pompe).
- **ARP page** (hold Shift): mode, rate (1/4 to 1/32), gate, octaves (1 to 3). Shift + 4th click keeps it open
  (again to close).
- **Lead** (3rd, the last step): single notes in the key and scale. A key in the scale plays its own note; one
  outside it moves to the nearest scale note, down on a tie (in Bb lydian, B plays Bb).
- **SEQ on** plays chords. **SEQ off** plays plain notes; CHERD's page stays up and says SEQ OFF.
- **Octave arrows** move the octave from -4 to +4 while you play. Chords sound an octave below the key you press.
- Spread, strum, comp, arp, swing and human are kept per synth slot; key, scale, flow and smooth are shared.

**First groove (Minor Swing):** Key A, Scale minor, Spread close, Flow django. Click the 1st for FEEL, turn the 4th
to pompe, click the 1st again. Click the 3rd (comp on), SEQ on, and hold A, D, E one per bar.

## This release

| | |
| --- | --- |
| File | `cherd.pack` |
| Version | 21 |
| Size | 127428 bytes |
| SHA-256 | `a0933ed8fd2d0de0be067b3a758166fbdf09abc3d1ea6dc6150ddc0b11204dbb` |

**Tested on** OS 1.7.3+0, bootloader 1000.1.1, 2026-11-19: CHERD as the eighth entry in the sequencer menu, the pick
kept across a restart, and SEQ off showing CHERD's page.

**What's new since 18:** CHERD hands its notes and the screen to engine packs (engines.pack) when they are installed,
so its chords play new synth engines; and it offers its scale and current chord to other packs (`op1f_cherd_pcs`),
which the Auto Tune pack snaps to. Both are optional links: on its own, CHERD works as before.

## Source

The source is in the open-field project (the pack's recipe under `tools/pack/cherd/`, and CHERD itself in
`tools/patch/mod_cherd.cpp`, built with `-DCHERD_PACK`).

## Credits

- **Faust (LaP0573)**, for open-field: the loader, the base and the pack tools.
- **seajay's garden.pack**, for showing how to add a sequencer.
- **Petaluma Script** by Steinberg Media Technologies, under the SIL Open Font License 1.1. Its glyphs are
  rasterized inside the pack; the licence is in [OFL-Petaluma.txt](OFL-Petaluma.txt).
- **CHERD's chord engine** comes from the OP-XY Cherd, in the Open-XY project, under the MIT License,
  "Copyright (c) 2026 Open-XY contributors".

## Licence

MIT ([LICENSE](../LICENSE)). The Petaluma Script glyphs inside the pack stay under the SIL Open Font License 1.1.
