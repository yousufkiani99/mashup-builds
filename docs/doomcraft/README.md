# DoomCraft 0.1.0: community build

Unofficial build for the Mashup Library. Release tag `doomcraft-v0.1.0` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/roryekay/doomcraft/tree/594aaa6193a5cb0878ce62800dc0ab5cadfe3b68
- **Pinned commit:** `594aaa6193a5cb0878ce62800dc0ab5cadfe3b68`
- **Licence:** GPL-3.0-or-later (the patched GZDoom engine) and MIT (the Minecraft mod), roryekay. LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Unchanged:** nothing is recompiled or modified; the files are the creator's own, checked by SHA-256.
- **Workflow:** [`.github/workflows/build-doomcraft.yml`](../../.github/workflows/build-doomcraft.yml)

- **Not recompiled: the creator's own v0.1.0 files, byte for byte.** The patched `gzdoom.exe`, `doomcraft.pk3` and the
  Minecraft jar exist only inside the creator's Inno Setup installer. The workflow downloads
  `DoomCraft-Setup-0.1.0-Windows-x64.exe` from his v0.1.0 release (SHA-256 `a07094ff…e042`, pinned), unpacks it with the
  creator's documented extraction-only mode (`/VERYSILENT /SMOKETEST=1 /DIR=<temp>`: no shortcuts, no uninstaller, no
  game setup) and checks all files against his `payload-sha256.json` (SHA-256 `28cf69d8…b9aa`, pinned). Any mismatch,
  missing file or `.wad` fails the build.
- **GPL source:** `DoomCraft-Engine-Source-0.1.0.zip` is the creator's corresponding source, published here unchanged
  (SHA-256 `2d618100…0eb3`, pinned): GZDoom g4.14.2 (`ZDoom/gzdoom@99aa489`) plus DoomCraft's native code and
  `patch-engine.py`. `doomcraft-0.1.0-source.zip` is `git archive` of the pinned commit (the MIT Minecraft mod and scripts).
- **Cross-check (not shipped):** the Minecraft mod is also built from the pinned commit and compared with the creator's
  jar entry by entry (`logs/4-crosscheck.log` in the build log summary).
- **Not included:** GZDoom's stock runtime DLLs and sound font (from GZDoom's official `gzdoom-4-14-2-windows.zip`),
  Fabric, Minecraft, and any DOOM data. Players use their own `DOOM.WAD` / `DOOM2.WAD`.

## Release files

| File | What it is |
| --- | --- |
| `doomcraft-0.1.0-runtime.zip` | `runtime\gzdoom.exe` (patched), `runtime\doomcraft.pk3`, GZDoom's engine pk3s, `doomcraft.cfg`, `CONTROLS.md`, `THIRD_PARTY.md`, LICENSE/NOTICE |
| `passthrough-0.1.0-doom.jar` | The Fabric mod for Minecraft 26.3 (the creator's jar) |
| `DoomCraft-Engine-Source-0.1.0.zip` | GPL corresponding source of the engine (the creator's file, unchanged) |
| `doomcraft-0.1.0-source.zip` | The repo at the pinned commit |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Built by [run 40320527901](https://github.com/yousufkiani99/mashup-builds/actions/runs/40320527901) on 2026-10-26; draft release `doomcraft-v0.1.0`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `BUILD-LOG-SUMMARY.txt` | 15,691 | `5c61a5bcd55dfd5dfe6bb7beae6d5f618b09f4896ceb5da273860598c01a2c2c` |
| `doomcraft-0.1.0-runtime.zip` | 14,717,562 | `f08bdd72521a2a25308cbf87d6d7835e5ca93fe50403e8e7fc2bc121ed79cb42` |
| `doomcraft-0.1.0-source.zip` | 225,365 | `d6f27775c0bb4b12d8d6c9536bd08f6fe04c618466395cbc3aa18fa25d444ba3` |
| `DoomCraft-Engine-Source-0.1.0.zip` | 28,803,764 | `2d618100b2ec6e6fe5085cfb36dcc041ae866d7186d0b3b3fb07def8f10b3eb3` |
| `LICENSE.txt` | 35,821 | `0b383d5a63da644f628d99c33976ea6487ed89aaa59f0b3257992deac1171e6b` |
| `NOTICE.txt` | 18,999 | `e3e560926dec9bce2709f44f93fa4a31a506a1a402dffdf278b93a758492965c` |
| `passthrough-0.1.0-doom.jar` | 288,060 | `7cb71120ee4addfb3e987345d8fd62eaa2bd63b42d0396d40d70a4f1bceb48fc` |
| `SHA256SUMS.txt` | 535 | `18af62531f798b9c28658950f047f33b5b170df4a1ca3287ebaf7476ab660671` |
