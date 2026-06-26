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
  fantasy-battle-mode/
    manifest.json
    files/
      Battle Mode/
  fantasy-tavern/
    manifest.json
    files/
      Tavern/
  fantasy-town/
    manifest.json
    files/
      Town/
  fantasy-travel/
    manifest.json
    files/
      Travel/
  horror-chase/
    manifest.json
    files/
      Chase/
  horror-tension/
    manifest.json
    files/
      Tension/
```

## Where to put game-system audio

Put audio that belongs to a specific game system inside that pack:

```text
packs/<pack_id>/audio/<scene-folder>/<audio-file>
```

Examples:

```text
packs/dnd5e/audio/Battle Mode/initiative-rise.mp3
packs/dnd5e/audio/Battle Mode/cover.jpg
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
audio-packs/fantasy-battle-mode/files/Battle Mode/battle-drums.ogg
audio-packs/fantasy-battle-mode/files/Battle Mode/cover.jpg
audio-packs/fantasy-tavern/files/Tavern/busy-inn.mp3
audio-packs/horror-chase/files/Chase/pursuit.wav
```

Add `cover.jpg`, `cover.jpeg`, `cover.png`, or `cover.webp` to any audio
folder to use it as the Media player album art for tracks imported from that
folder. Child folders inherit the nearest parent cover.

## Folder names become GM queues

Nexus preserves folder names when importing audio. In the Media player, the GM
can select a folder such as:

```text
Expansion Audio/Fantasy/Battle Mode
Expansion Audio/Horror/Chase
```

That folder becomes the active scene queue.

Each scene is its own installable audio pack. Use the manifest field
`library_folder` to group related packs together in the Media Library. For
example, `fantasy-battle-mode`, `fantasy-tavern`, `fantasy-town`, and
`fantasy-travel` all set `"library_folder": "Fantasy"`, so they install beneath
`Expansion Audio/Fantasy/...` while remaining individually installable.

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
