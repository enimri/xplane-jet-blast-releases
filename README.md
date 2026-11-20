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
- Settings window inside X-Plane, a one-click bug report, and an update check.

## Install
1. Download `JetBlast-vX.Y.Z.zip` from [Releases](https://github.com/enimri/xplane-jet-blast-releases/releases).
2. Unzip it into `X-Plane 12/Resources/plugins/`, so you get:
   ```
   plugins/JetBlast/win_x64/JetBlast.xpl   (Windows)
   plugins/JetBlast/mac_x64/JetBlast.xpl   (macOS, Intel and Apple Silicon)
   plugins/JetBlast/lin_x64/JetBlast.xpl   (Linux)
   plugins/JetBlast/jetblast.ini
   plugins/JetBlast/jetblast_types.csv
   ```
   X-Plane picks the right one for your system automatically.
3. Start X-Plane 12. The menu is **Plugins ▸ Jet Blast**.

Requirements: X-Plane 12 on Windows 64-bit, macOS 11 or newer, or 64-bit Linux. Nothing else needs installing.

**macOS:** the plugin isn't signed with a paid Apple certificate, so macOS may block it the first time. If X-Plane says the plugin couldn't load, open Terminal and run this once (adjust the path to your X-Plane folder):
```
xattr -dr com.apple.quarantine "/Applications/X-Plane 12/Resources/plugins/JetBlast"
```

## Settings
Open **Plugins ▸ Jet Blast ▸ Settings...** in X-Plane. Click **−** / **+** or **ON/OFF** to change a setting; it takes effect immediately. Click **Save** to keep it for next time.

You can also edit `jetblast.ini` directly, then choose **Plugins ▸ Jet Blast ▸ Reload settings**.

| Setting | What it does |
|---|---|
| `intensity` | Strength of all forces on your aircraft (1.0 = normal) |
| `jet_constant` | How far the blast reaches (7 = default; 8–9 = further) |
| `gustiness` | How much the blast gusts (0 = steady) |
| `max_range_m` | Ignore traffic farther away than this |
| `include_xplane_ai` | Also use X-Plane's own AI traffic |
| `user_span_m`, `user_length_m` | Your aircraft size if auto-detection is wrong (0 = auto, ini file only) |
| `check_updates` | Check for a newer Jet Blast version when X-Plane starts |

## Updates
When X-Plane starts, Jet Blast asks GitHub once whether a newer version exists. If there is one, the menu changes to **Jet Blast (update available)** and the Settings window shows where to download it. Nothing is installed automatically. The check sends no personal data; turn it off in Settings or with `check_updates = 0`.

Add or fix aircraft types in `jetblast_types.csv`. The format is explained inside the file.

## Known limitations
- Networks don't send engine data, so thrust is estimated from motion. A static run-up on the brakes isn't detected unless the traffic source sends throttle data.
- Blast affects your aircraft only. Other traffic isn't pushed.
- The macOS and Linux versions are new and have only been build-tested so far. Reports from Mac and Linux users are especially welcome.

## Problems or ideas?
Choose **Plugins ▸ Jet Blast ▸ Copy bug report** right after the problem happens. Then paste the report into an [issue](https://github.com/enimri/xplane-jet-blast-releases/issues) or a reply in the forum thread. It contains your Jet Blast version and settings, your aircraft type, the traffic around you and recent Jet Blast log lines. It never includes your name, account, location or files. The same report is also saved as `jetblast_bugreport.txt` in the plugin folder.

## License
Freeware: free to download and use, closed source. See [LICENSE.txt](LICENSE.txt).
