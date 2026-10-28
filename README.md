# rp_arquitens_town

![rp_arquitens_town](images/preview.jpg)

A Garry's Mod Star Wars RP map: an edit of Bananakin's open-source
[Arquitens Class Cruiser](https://steamcommunity.com/sharedfiles/filedetails/?id=3622448623).
The ship is unchanged. The planet below has grown into a full town, with a hidden criminal base and a Jedi temple.

**Created by JavenLander**

This repository holds the map's source (`rp_arquitens_town.vmf`), as the original map's license requires edits to stay open source.

## What's in the map

- **Town:** the original village grows into one town. 14 new buildings and a second round landing bay sit along narrow, paved alleys with street lamps and yard props. Rocky cliffs ring the town, and the village wall closes the passes between them. The ground under the houses is bare earth and the town floor is level, so props don't float or sink. Each new house is its own Hammer group, so it moves as one piece.
- **Criminal hideout:** a secret underground base below the village, with a casino and bar, two barracks rooms, a boss office, a vault and a hidden escape route that comes out at a sewer grate.
- **Jedi Temple:** reached from a crystal cave in the hillside near the Jedi monument. It's based on Jedi Temple Redux, with sharpened textures, normal maps and soft reflections. The old tan walls are now blue-grey stone.
- **Ambience:** the town, the hideout, the staff room and each part of the temple have their own background sound.
- **Staff room:** a sealed room below the map, used by the Lander Naval Command addon's staff buttons (fix reactor, shields, life support and so on).
- **Shuttle landing points:** named `info_teleport_destination`s for the Lander Naval Command addon's shuttle stops. These are `land_ship` (the hangar), `land_town` (the village pad), `land_temple` (the ruins pad) and `land_sfbase` (the Republic outpost pad).

## Repository layout

```
rp_arquitens_town.vmf        the map source (Hammer++)
images/                      Workshop cover and a town screenshot
tools/content_extractor/     copies the Arquitens content the map uses out of the original addon
```

## Opening and compiling

1. **Get the content.** The map uses models, materials and sounds from the original Arquitens addon and from
   [Jedi Temple Redux [FTP]](https://steamcommunity.com/sharedfiles/filedetails/?id=2711897704).
   Subscribe to both on the Workshop, or install the published rp_arquitens_town addon, which includes everything the map uses.
   Hammer needs the files loose (or mounted), so extract them into `garrysmod/` if your setup needs that.
2. **Open** `rp_arquitens_town.vmf` in **Hammer++** for Garry's Mod.
3. **Compile** with VBSP, VVIS and VRAD (normal settings), then build cubemaps in game (`buildcubemaps`).
4. **Watch the brush limit.** The map is at about 8,140 of Source's 8,192 brushes. New detail should be props or `func_detail` wherever possible, and areas you replace should be removed first.

### Things to know when editing

- The terrain is power-4 displacements on a 128-unit grid, with the town floor at z = -12756.
- The hideout (z around -16200), the Jedi temple (z around -14000) and the staff room (z around -15000) are sealed boxes below the planet. Their entrances are teleports: `crim_lift_down` / `crim_lift_up`, `crim_escape`, `jt_enter` / `jt_exit`, and `admin_room_exit`.
- The hideout's secret entrance and exit are `func_button`s (`crim_bottle_button`, `crim_escape_button`). Each one enables its teleport for a few seconds.
- The soundscape triggers use the original map's soundscapes. The map's soundscape file has to be named `scripts/soundscapes_rp_arquitens_town.txt`; the content extractor makes it.

## Publishing without the original addon as a requirement

`tools/content_extractor` copies only the Arquitens files this map uses out of the original addon's `.gma`. It doesn't copy the whole 1.7 GB pack. It also creates the soundscape and particle files under this map's name.

1. Run `RUN_ME.bat`. It looks for the Arquitens `.gma` in the usual Steam Workshop folders, or you can pass `-Gma "<path>"`.
2. Merge `rp_arquitens_town_content/` into the addon folder next to `maps/rp_arquitens_town.bsp`.
3. Check `content_report.txt`. Anything listed there should be base Garry's Mod or Half-Life 2 content.

## Credits

**Original map: [Arquitens Class Cruiser](https://steamcommunity.com/sharedfiles/filedetails/?id=3622448623)** (open source)
- Bananakin: Map
- Goldie: Textures, Sounds, Support
- Deadshotlp: Support
- 122jimbo: Textures
- ColdSaturNight: Textures
- Halves: Models
- Graves: Models, Particles, NPC Scripts
- FallenLogic: NPC Models + Animations

The Arquitens hyperspace system and NPC scripts are not open source and are not part of this edit.

**Jedi Temple: [Jedi Temple Redux [FTP]](https://steamcommunity.com/sharedfiles/filedetails/?id=2711897704) by MacDuffin**
- King Pommes: Inspiration
- Aurora Mapping Studio: Original conversion of the SWBF2 map to Source
- pichotm: Released the SWBF2 Jedi Temple map
- SpyShadow: Textures
- BigMac: Holocron Room
- Stiffy360: Dojo assets
- Ricky: Knowledge and support
- Asus: Custom textures
- Jedi Knight Academy Mods: Sounds and textures

**This edit:** town expansion, criminal hideout, cave and temple integration, by **JavenLander**.

## License

This edit follows the original Arquitens map's terms: it's a public map addon, kept open source, and it credits the original authors above. Third-party assets belong to their creators. They are not in this repository. Get them from the Workshop items linked above.
