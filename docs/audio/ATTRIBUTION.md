# Original Living Harbor audio

All 27 files below are original procedural compositions/sound designs by Nano Harbor contributors, created for this project on 2026-10-15 and 2026-10-16. No recordings, third-party samples, pretrained audio, or external compositions used. Source: [`scripts/create-audio.py`](../../scripts/create-audio.py), in this repository. Generated audio is dedicated to the public domain under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/); source code follows the repository license.

These are stylized game identities rather than authentic engine recordings. Diesel pulses, additive machinery harmonics, filtered seeded noise, brass-like horns, sea/wind/rain beds, gull-like chirps, creaks, and two original synchronized music stems were synthesized offline. Edits: peak normalization, quiet loop joins, short attack/release envelopes, MP3 encoding with ffmpeg/libmp3lame. The sea, weather and music layers were revised on 2026-10-18 for longer, softer background playback. No external assets require redistribution permission.

| Vessel | Mono engine, 8 seconds | Mono horn |
| --- | --- | --- |
| Ferry | engine-ferry.mp3 | horn-ferry.mp3 |
| Cruise | engine-cruise.mp3 | horn-cruise.mp3 |
| Oil tanker | engine-oil.mp3 | horn-oil.mp3 |
| Gas tanker | engine-gas.mp3 | horn-gas.mp3 |
| Bulk carrier | engine-grain.mp3 | horn-grain.mp3 |
| Container | engine-container.mp3 | horn-container.mp3 |
| Rescue | engine-rescue.mp3 | horn-rescue.mp3 |

Mono ambience loops (24 seconds): ocean.mp3, shore.mp3, wind.mp3, rain.mp3, harbor.mp3. Layered low-pass noise gives the sea and surf uneven swells, the wind soft broadband gusts without a pitched whistle, and the rain a rounded patter without harsh white-noise hiss. The harbor layer adds distant machinery and muffled fender contacts; its restrained level rises with servicing traffic, capped at three ships. Overlapping 0.8-second ends keep the beds continuous without a silent loop join. Peaks are limited to 0.36, or 0.32 for rain, before the quiet runtime mix.

Mono one-shots: bird-1.mp3, bird-2.mp3, bird-3.mp3, thunder-1.mp3, thunder-2.mp3, dock.mp3. The two thunder variants are soft seven-second rolls of filtered noise with a gradual arrival and natural decay; they contain no sharp crack or tonal sweep.

Mono music stems (60 seconds): music-calm.mp3, music-tension.mp3. Both share four slowly overlapping suspended chords with a common clock and two-second loop crossfades. Calm uses warm, gently breathing pads; tension adds a subdued low register. There are no bells, lead melody or insistent beat. Both peaks are limited to 0.24 before runtime volume controls.

Reproduce: `python3 scripts/create-audio.py` (Python standard library and ffmpeg with libmp3lame). Encoded budget 8 MiB; decoded cache limit 64 MiB enforced at runtime. Source sample rate 24 kHz; the browser audio context requests 48 kHz. Mono background assets leave room for operations sounds and bundled speech; the renderer reserves 3.6 MiB at that rate for those layers. Listening review on laptop speakers/headphones remains required before release; automated signal checks cannot establish comfort or realism.

## Coast Guard operations room

Eight additional original procedural sounds, created for Nano Harbor on 2026-10-18, are dedicated to [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/):

- `collision-room.mp3`: centered mono warning horn, 2.1 seconds; two alternating high/low pairs made from additive harmonics. One shared loop plays during collision risk or danger-zone exposure with grace remaining.
- `collision-impact.mp3`: prominent one-time hull crash, 2.8 seconds; heavy impact, sustained midrange metal tearing and water release.
- `boat-sinking.mp3`: prominent one-time sinking cue, 3.6 seconds; descending distress tones, hull groan and sustained rushing/bubbling water.
- `radio-squelch.mp3`: generic building channel-opening call, 0.8 seconds; "CG" (`-.-. --.`) at a steady 760 Hz with a restrained second harmonic. Boat selections instead key a deterministic identifier motif locally, at 760 Hz for merchant boats and 920 Hz for repair boats, lasting at most 0.84 seconds. Crisp dots and dashes use short attack/release ramps and silent gaps, with no receiver hiss or pitch sweep. All generated tones are original and dedicated to CC0.
- `radio-acknowledge.mp3`: rising two-note merchant acknowledgement, 0.35 seconds.
- `radio-reject.mp3`: falling two-note merchant rejection, 0.35 seconds.
- `radio-repair.mp3`: crisp naval repair-unit call with a double chirp and rising finish, 0.55 seconds.
- `radio-repair-reject.mp3`: related repair-unit call with a descending finish, 0.55 seconds.

The response calls combine a small amount of seeded receiver static with sine tones and a restrained second harmonic. These eight effects contain no recordings, third-party samples, pretrained audio or external compositions. Reproduce them with `python3 scripts/create-operations-audio.py`, which reuses the renderer from `create-audio.py`. Edits are peak normalization, short attack/release envelopes, and MP3 encoding with ffmpeg/libmp3lame.

## Bundled spoken radio

Five clips were generated offline on 2026-10-18 with Piper 1.8.0 and Bryce Beattie's public-domain Norman male English voice. Model revision, hashes, primary sources and build-time engine licensing are recorded in [RADIO_VOICES_LICENSE.txt](RADIO_VOICES_LICENSE.txt). The user auditioned and approved this voice. No engine or voice model is included in the frontend.

| File | Spoken line | Duration |
| --- | --- | --- |
| radio-voice-contact.mp3 | On channel. | 0.640 s |
| radio-voice-acknowledge.mp3 | Copy that! | 1.430 s |
| radio-voice-acknowledge-alt.mp3 | Roger that! | 0.890 s |
| radio-voice-reject.mp3 | Cannot reach that point, officer. | 2.110 s |
| radio-voice-repair.mp3 | Aye aye, officer. | 1.950 s |

Reproduce with the temporary Piper environment and pinned local model described in `scripts/create-radio-voices.py`; generation itself needs no network. Processing uses a 180–3600 Hz radio band, gentle compression, edge-silence/breath trimming with consonant padding, and normalization before mono 24 kHz MP3 encoding. Speaking rate and pitch are unchanged; no hiss is added. The generator validates its eight-second / 80 KB budget before replacing files.

Only the finished clips ship with the game. Runtime uses local Web Audio buffers, with no browser speech service, external TTS API or voice model download. Captions retain vessel IDs and full order details. The five clips total 7.020 seconds, 59,745 compressed bytes and approximately 1.285 MiB decoded at 48 kHz. One-minute music stems offset their size; all 40 assets total approximately 62.607 MiB decoded, below the existing 64 MiB cache limit.
