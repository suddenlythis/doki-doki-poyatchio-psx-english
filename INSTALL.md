# Installing the Doki Doki Poyatchio!! English translation (v1.0)

The download contains only the changes to the game's data track, not the game. You need your
own disc image of Doki Doki Poyatchio!! (Japan), the Redump version.

## What you need

- The Redump version of **Doki Doki Poyatchio!! (Japan)** (product code SLPS-01573): one `.cue`
  and one `.bin`, as Redump catalogues it. The disc has a single track.
- The file that gets patched must be exactly:

  | File | Size | SHA-1 |
  |---|---|---|
  | `Doki Doki Poyatchio!! (Japan).bin` | 711,908,064 bytes | `be62448e2f80879ceea35c00e68d0cc1d9c40695` |

  With any other file the patch refuses to apply.
- xdelta3, or a front end for it such as Delta Patcher or xdelta UI. Rom Patcher JS in a web
  browser also applies `.xdelta` files.
- A PlayStation emulator. Tested in DuckStation.

## What is in the zip

| File | What it is |
|---|---|
| `DokiDokiPoyatchio-EN-v1.0.xdelta` | The patch for the data track |
| `Doki Doki Poyatchio!! (English).cue` | Optional cue sheet, only for the side-by-side alternative below. Most people do not need it |
| `README.txt` | The release notes |

## How to apply

Patch the `.bin` with the `.xdelta`. Keep the file name, and open your usual `.cue`. That is all.

### With Delta Patcher

1. Original file = your `Doki Doki Poyatchio!! (Japan).bin`
2. XDelta patch = `DokiDokiPoyatchio-EN-v1.0.xdelta`
3. Tick Backup original file in the settings, then Apply patch.

### With the command line

xdelta3 writes a new file, so rename the original first:

```
ren "Doki Doki Poyatchio!! (Japan).bin" "original.bin"
xdelta3 -d -s "original.bin" DokiDokiPoyatchio-EN-v1.0.xdelta "Doki Doki Poyatchio!! (Japan).bin"
```

### Check the result

The patched file is 711,908,064 bytes with this SHA-1 checksum:

| File | SHA-1 after patching |
|---|---|
| `.bin` | `8e3d3e6269fee067772ba17d7ddeee6e2526650e` |

## Alternative: keep the Japanese and English discs side by side

Leave your files alone, save the patched file as `Doki Doki Poyatchio!! (English).bin`
in the same folder, and open `Doki Doki Poyatchio!! (English).cue` from the zip.

## After patching

Start a new game. Saves made with the Japanese game store the hero's name in kana, which the
English font shows as symbols. A save state made on the Japanese game keeps the old program
and text in memory, so load the game normally instead. In-game saves are offered when the hero
goes to bed at night.

Controls: Circle confirms and talks, Cross cancels, Triangle opens the pocket and keyword menu,
Square shouts a greeting ("Hiya!"), Start pauses. If the game does not react to the pad, set the
controller type to Digital Controller.

## Tested on

DuckStation. Not tested on other emulators or on real hardware.
