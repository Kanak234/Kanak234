# VAJRA

A third-person tactical stealth shooter, made in **Godot 4.7** (GDScript) by **Kanak Prabhakar**.
Stage 1: a one-mission vertical slice.

You are Captain Agnivesh, callsign VAJRA. The Vritra Combine, a flagless arms syndicate, has seized a forward base in the Karanth hills. Your handler, Tara, sends you in alone at dusk. Infiltrate the base, disable the comms tower, recover the intel and reach the helipad, quietly or loudly.
All people, places and groups are fictional.

![Main menu](docs/screenshots/phase_7/p05_main_menu.png)
![Mission 1](docs/screenshots/phase_7/linux_build_mission1.png)

## Features
- Third-person controller: walk, run, sprint, crouch, jump, with blended animation and IK weapon holding.
- Guard AI that **sees** (cone, distance, light level, stance, movement) and **hears** (footsteps, shots). States: patrol, suspicious, alert, combat, search. Guards take cover, flank and reload.
- Alarm system: a guard runs to the alarm panel, then siren, beacons and reinforcement waves follow. You can disable the panel.
- Knife, silenced pistol, assault rifle, sniper rifle; silent takedowns; binoculars with marking; satellite map; compass.
- Ordered and optional objectives, checkpoints, results screen with a rating, rolling credits.
- Settings: graphics presets, resolution, V-Sync, FPS cap, FOV, key rebinding, mouse and volume.

## Play
**itch.io:** https://kanak234.itch.io/vajra

Download the Windows or Linux zip, unzip it, and run `Vajra.exe` / `Vajra.x86_64`. Nothing else to install (a Vulkan-capable GPU is needed).
The same zips and the trailer are also attached to this repository's **v0.1.0 release**.

## Build from source
1. Install **Godot 4.7.2** (standard build) and its export templates.
2. Open `project.godot`, or run the game from a terminal:
   ```bash
   godot --path .
   ```
3. Export both builds (they go to `builds/`, which git ignores):
   ```bash
   godot --headless --export-release "Linux" builds/linux/Vajra.x86_64 && godot --headless --export-release "Windows Desktop" builds/windows/Vajra.exe
   ```

## Tests
Every phase has an automated test, e.g.:
```bash
godot --headless --path . tests/test_phase7_release.tscn
```
Long stability run inside an exported build: `./builds/linux/Vajra.x86_64 --headless -- --soak=30`.

## Project layout
```
scenes/   scripts/   (player, ai, systems, ui, levels)
assets/original/     made for this game (characters, weapons, level, animations)
assets/third_party/  CC0 packs (see ASSET_LICENSES.md)
tools/               content build scripts (Blender, Godot) and release packaging
tests/               automated tests
docs/                design, architecture, phase write-ups, acceptance, screenshots
```

## Documentation
- [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md): how the systems fit together
- [docs/PHASE_0_EXPLAINED.md](docs/PHASE_0_EXPLAINED.md) … [docs/PHASE_7_EXPLAINED.md](docs/PHASE_7_EXPLAINED.md): what each phase built
- [docs/ACCEPTANCE.md](docs/ACCEPTANCE.md): Stage 1 acceptance results
- [docs/VIVA_GUIDE.md](docs/VIVA_GUIDE.md): the four core systems explained

## Credits and licenses
- Characters: MakeHuman Community assets (CC0).
- Animations: Quaternius Universal Animation Library (CC0).
- Textures, HDRI and props: Poly Haven (CC0).
- Engine: Godot (MIT).

Full list: [ASSET_LICENSES.md](ASSET_LICENSES.md). No content from any other game is used.

© Kanak Prabhakar. All rights reserved for the original code and content, except the third-party assets listed above, which keep their own licenses.
