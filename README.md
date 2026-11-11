# scoredit-sounds

Recorded instrument sounds for [scoredit](https://github.com/hikashop-nicolas/scoredit)'s
score player: the General MIDI instruments of **MuseScore_General** by S. Christian Collins
(MIT, see `LICENSE.md`), cut into small SoundFonts a player downloads only when a score needs
them.

- `gm/index.json` maps each General MIDI program (0-127, and `drums` for the kit) to its file,
  name and size in bytes.
- Instruments that share large recordings (the three pianos, for one) share a file, so each
  recording is stored once. Small shared samples are copied into each file.
- The samples keep their original compressed (Ogg Vorbis) form; nothing is re-encoded.

Built with `node scripts/make-sound-packs.mjs MuseScore_General.sf3 gm` from scoredit, from
https://ftp.osuosl.org/pub/musescore/soundfont/MuseScore_General/ (version 0.2).

Served at `https://cdn.jsdelivr.net/gh/hikashop-nicolas/scoredit-sounds@<tag>/gm/<file>`.
