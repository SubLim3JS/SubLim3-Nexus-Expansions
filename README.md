# SubLim3 Nexus Expansions

Optional game systems and audio packs for the SubLim3 Nexus platform live here,
outside the core application repo.

The core Nexus repo should stay lightweight: app engine, hardware support,
installer/updater, Custom RPG, and tiny built-in system sounds. This repo is for
downloadable content.

## Repository layout

```text
catalog.json

packs/
  dnd5e/
    manifest.json
    system.json
    audio/
      Battle Mode/
      Tavern/
      Dungeon/
      SFX/

audio-packs/
  fantasy-core/
    manifest.json
    files/
      Battle Mode/
      Boss Fight/
      Dungeon/
      Tavern/
      Travel/
      SFX/
```

## Where to put game-system audio

Put audio that belongs to a specific game system inside that pack:

```text
packs/<pack_id>/audio/<scene-folder>/<audio-file>
```

Examples:

```text
packs/dnd5e/audio/Battle Mode/initiative-rise.mp3
packs/dnd5e/audio/Tavern/busy-inn.ogg
packs/dnd5e/audio/SFX/critical-hit.wav
```

## Where to put shared audio packs

Put audio that can be used by multiple systems in `audio-packs`:

```text
audio-packs/<audio_pack_id>/files/<scene-folder>/<audio-file>
```

Examples:

```text
audio-packs/fantasy-core/files/Battle Mode/battle-drums.ogg
audio-packs/fantasy-core/files/Dungeon/deep-cavern.flac
audio-packs/fantasy-core/files/SFX/door-open.wav
```

## Folder names become GM queues

Nexus preserves folder names when importing audio. In the Media player, the GM
can select a folder such as:

```text
Expansion Audio/Dnd5e/Battle Mode
```

That folder becomes the active scene queue.

Recommended folder names:

- `Battle Mode`
- `Boss Fight`
- `Tavern`
- `Dungeon`
- `Travel`
- `Town`
- `Tension`
- `Chase`
- `SFX`

Files inside folders named `SFX`, `FX`, `Effect`, or `Effects` are imported as
one-shot effects. Other audio files are imported as looping ambience.

## Supported audio formats

- `.mp3`
- `.wav`
- `.ogg`
- `.oga`
- `.opus`
- `.m4a`
- `.aac`
- `.flac`
- `.webm`

## Importing into Nexus

From the core `SubLim3-Nexus` repo:

```bash
npm run audio:expansions:import
```

To remove imported expansion audio:

```bash
npm run audio:expansions:remove
```
