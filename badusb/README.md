# Flipper Zero — ready to copy

Copy this entire `badusb` folder onto your Flipper’s microSD card so it lands at:

```text
SD Card/badusb/
```

After copy you should have paths like:

```text
SD Card/badusb/Prank/High_Contrast/High-Contrast.txt
SD Card/badusb/Prank/Mouse_Zap/MouseZap.txt
...
```

## Install (pick one)

### Option A — qFlipper (easiest)

1. Install [qFlipper](https://flipperzero.one/update) and connect your Flipper over USB.
2. Open **File manager** → `SD Card` → `badusb`.
3. Drag the contents of this repo’s `badusb/Prank` folder into `SD Card/badusb/` (create `Prank` if needed), or upload the whole `badusb` tree so folders match the layout above.
4. Disconnect qFlipper before running payloads.

### Option B — Flipper mobile app

1. Connect Flipper over Bluetooth.
2. **Options → File Manager → ext → badusb**.
3. Upload the `.txt` scripts (keep the `Prank/...` subfolders).

### Option C — SD card directly

1. Power off Flipper, remove the microSD card, mount it on a computer.
2. Copy this repo’s `badusb` folder onto the card root (merge with any existing `badusb` folder).
3. Eject safely, reinsert, power on.

## Run a payload

1. On Flipper: **Main Menu → Bad USB**.
2. Open `Prank` → pick a script.
3. Confirm **USB** mode (not Bluetooth) unless you intentionally want BLE BadUSB.
4. Optional: press **Layout** and set the keyboard layout to match the target PC (default is US English).
5. Plug Flipper into the PC with a data USB cable.
6. Press **OK / Run**.

## Included payloads

| Folder | Scripts | What it does |
| --- | --- | --- |
| `Prank/High_Contrast` | `High-Contrast.txt`, `High-Contrast-Lock.txt` | Toggles Windows high contrast |
| `Prank/Mouse_Zap` | `MouseZap.txt` | Swaps primary mouse button + slows cursor |
| `Prank/Nope_Pad` | `Nope-Pad*.txt` | Disables / restores laptop touchpad |
| `Prank/Telnet_Star_Wars` | `TelnetStarWars.txt` | Enables Telnet client and plays ASCII Star Wars |
| `Prank/Win_Zoom` | `Win-Zoom.txt` | Zooms the Windows display |

## Compatibility fixes in this package

- Folder names use underscores (no spaces) for reliable browsing on Flipper.
- `MouseZap` arrow keys use Flipper-supported `RIGHTARROW` / `LEFTARROW` names.
- Scripts stay plain `.txt` DuckyScript — no compile step.

## Important

- Use only on machines and accounts you own or have explicit permission to test.
- Close qFlipper before running Bad USB over USB.
- `TelnetStarWars` needs admin approval (UAC) and network access; `ALT y` assumes an English UAC dialog.
- Large PIN-bruteforce text dumps from the old `Pin Bruteforce/` folder are **not** included here — they are impractical on Flipper (multi‑MB / millions of lines) and are for attacking authentication, which this package does not support.
