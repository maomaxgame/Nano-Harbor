# Original Living Harbor audio

All 27 files below are original procedural compositions/sound designs by Nano Harbor contributors, created for this project on 2026-10-15 and 2026-10-16. No recordings, third-party samples, pretrained audio, or external compositions used. Source: [`scripts/create-audio.py`](../../scripts/create-audio.py), in this repository. Generated audio is dedicated to the public domain under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/); source code follows the repository license.

These are stylized game identities rather than authentic engine recordings. Diesel pulses, additive machinery harmonics, filtered seeded noise, brass-like horns, sea/wind/rain beds, gull-like chirps, creaks, and two original synchronized music stems were synthesized offline. Edits: peak normalization, quiet loop joins, short attack/release envelopes, MP3 encoding with ffmpeg/libmp3lame. No external assets require redistribution permission.

| Vessel | Mono engine, 8 seconds | Mono horn |
| --- | --- | --- |
| Ferry | engine-ferry.mp3 | horn-ferry.mp3 |
| Cruise | engine-cruise.mp3 | horn-cruise.mp3 |
| Oil tanker | engine-oil.mp3 | horn-oil.mp3 |
| Gas tanker | engine-gas.mp3 | horn-gas.mp3 |
| Bulk carrier | engine-grain.mp3 | horn-grain.mp3 |
| Container | engine-container.mp3 | horn-container.mp3 |
| Rescue | engine-rescue.mp3 | horn-rescue.mp3 |

Stereo ambience loops (10 seconds): ocean.mp3, shore.mp3, wind.mp3, rain.mp3, harbor.mp3. The harbor layer combines distant machinery hum, metallic clinks and rigging creaks; its restrained level rises with servicing traffic, capped at three ships.

Mono one-shots: bird-1.mp3, bird-2.mp3, bird-3.mp3, thunder-1.mp3, thunder-2.mp3, dock.mp3.

Stereo music stems (32 seconds, 60 BPM): music-calm.mp3, music-tension.mp3. Both share eight four-beat bars. Calm uses soft major pads and bells; tension adds restrained bass pulses and fifths.

Reproduce: `python3 scripts/create-audio.py` (Python standard library and ffmpeg with libmp3lame). Encoded budget 8 MiB; decoded cache limit 64 MiB enforced at runtime, including hardware resampling. Source sample rate 24 kHz. Listening review on laptop speakers/headphones remains required before release; automated signal checks cannot establish comfort or realism.
