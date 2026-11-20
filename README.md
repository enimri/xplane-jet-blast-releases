# Jet Blast for X-Plane 12

![Jet Blast: modelled blast behind a 737-800 at takeoff thrust](images/jetblast-cover.png)

Jet blast and prop wash from **online and plugin traffic**: VATSIM and IVAO (through xPilot or swift), LiveTraffic, and anything else that uses X-Plane's TCAS traffic API.

X-Plane 12 already gives this traffic a wake in the air, but nothing comes out of its engines on the ground. With Jet Blast, if you taxi or line up too close behind an aircraft that's breaking away or taking off, its exhaust pushes your aircraft sideways, rolls it and swings it around.

**[⬇ Download the latest release](https://github.com/enimri/xplane-jet-blast-releases/releases/latest)**

## Features
- Works with any traffic shown through the TCAS API. X-Plane's own AI aircraft are included too (you can turn that off).
- Thrust is estimated from each aircraft's motion: idle, breakaway, takeoff, reverse thrust after landing, and engines off when the beacon is off.
- Built-in engine data for about 100 aircraft types, from the C172 to the A380, including props and rear-engine jets.
- Blast that hugs the ground, with random gusts.
- Debug window listing every aircraft blowing on you, with its estimated thrust and the blast speed in knots.

## Install
1. Download `JetBlast-vX.Y.Z-win_x64.zip` from [Releases](https://github.com/enimri/xplane-jet-blast-releases/releases).
2. Unzip it into `X-Plane 12\Resources\plugins\`, so you get:
   ```
   plugins\JetBlast\win_x64\JetBlast.xpl
   plugins\JetBlast\jetblast.ini
   plugins\JetBlast\jetblast_types.csv
   ```
3. Start X-Plane 12. The menu is **Plugins ▸ Jet Blast**.

Requirements: X-Plane 12, Windows 64-bit. Nothing else needs installing.

## Settings
Edit `jetblast.ini`, then choose **Plugins ▸ Jet Blast ▸ Reload settings**.

| Setting | What it does |
|---|---|
| `intensity` | Strength of all forces on your aircraft (1.0 = normal) |
| `jet_constant` | How far the blast reaches (7 = default; 8–9 = further) |
| `gustiness` | How much the blast gusts (0 = steady) |
| `max_range_m` | Ignore traffic farther away than this |
| `include_xplane_ai` | Also use X-Plane's own AI traffic |
| `user_span_m`, `user_length_m` | Your aircraft size if auto-detection is wrong (0 = auto) |

Add or fix aircraft types in `jetblast_types.csv`. The format is explained inside the file.

## Known limitations
- Networks don't send engine data, so thrust is estimated from motion. A static run-up on the brakes isn't detected unless the traffic source sends throttle data.
- Blast affects your aircraft only. Other traffic isn't pushed.

## Problems or ideas?
Open an [issue](https://github.com/enimri/xplane-jet-blast-releases/issues). Include the lines starting with `JetBlast:` from `X-Plane 12\Log.txt`.

## License
Freeware: free to download and use, closed source. See [LICENSE.txt](LICENSE.txt).
