# Minecraft in Monster Hunter World (Windows port) 0.1.0: community build

Unofficial build for the Mashup Library. Release tag `minecraft-in-monster-hunter-world-windows-port-v0.1.0` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/Alvariill0/minecraft-crossover-bridge-windows/tree/6e1a4f15d77cd827f89abe2b7e3f3a274270f34c
- **Licence:** MIT (justbustin; Windows port by Alvariill0). LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-minecraft-in-monster-hunter-world-windows-port.yml`](../../.github/workflows/build-minecraft-in-monster-hunter-world-windows-port.yml)

- **Pinned commit:** `6e1a4f15d77cd827f89abe2b7e3f3a274270f34c`.
- **Built with the creator's own steps:** `make -C monster-hunter-world/mhw-bridge` under MSYS2 MINGW64
  (`mingw-w64-x86_64-gcc`, `make`) -> `dinput8.dll` + `mhwbridge_core.dll` (MinHook vendored); `gradlew build` in
  `monster-hunter-world/mc-bridge` (Gradle on JDK 25, Minecraft compiled on the JDK 21 toolchain).
- **No game files:** signatures and offsets are found at run time; MinGW headers and MinHook only.
- Solo only: never join online sessions or answer SOS flares with it.

## Release files

| File | What it is |
| --- | --- |
| `minecraft-in-monster-hunter-world-windows-port-0.1.0-game-files.zip` | `dinput8.dll` (next to MonsterHunterWorld.exe), `mhwbridge\mhwbridge_core.dll`, notices |
| `mhw-bridge-0.1.0.jar` | The Fabric mod for Minecraft 1.21.1 |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Built by [run 40324544768](https://github.com/yousufkiani99/mashup-builds/actions/runs/40324544768) on 2026-10-26; draft release `minecraft-in-monster-hunter-world-windows-port-v0.1.0`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `BUILD-LOG-SUMMARY.txt` | 8,726 | `2885b61e69ea32caac0baf8f1515e3cd0f846454ec123d9826cb13310eb6d473` |
| `LICENSE.txt` | 1,088 | `c4b95543e6a1f61cfa616da930cc3d80ec332d11283452b25b2e5750ac291aa7` |
| `mhw-bridge-0.1.0.jar` | 108,395 | `da78664b1886c01179d448e7ea890166cc7d770fc70574e91b2b399c8996d958` |
| `minecraft-in-monster-hunter-world-windows-port-0.1.0-game-files.zip` | 203,087 | `0bdda4db9de769ec0b15d08234d55e89f107563a646e40c8c3d312c009ceb1be` |
| `NOTICE.txt` | 5,973 | `8544a728693e4fc650e42ea29258e5168e833dc1b9e597ad4310391188904b26` |
| `SHA256SUMS.txt` | 376 | `07549914bc2eec71cba1d3054ce87ce2276ba04072219b3bb9dae6ba5b507496` |
