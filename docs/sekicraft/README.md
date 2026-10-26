# SekiCraft 0.0.1: community build

Unofficial build for the Mashup Library. Release tag `sekicraft-v0.0.1` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/NIHKOOL/SekiCraft/tree/c671e82104b5a66493d15154b61bccbec6d4b0b6
- **Licence:** MIT (NIHKOOL) and MIT (SkyCraft, chasmlol: `LICENSE-SkyCraft.txt`). LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-sekicraft.yml`](../../.github/workflows/build-sekicraft.yml)

- **Pinned commit:** `c671e82104b5a66493d15154b61bccbec6d4b0b6`.
- **Built with the README's steps:** MSVC x64, `cmake -S sekiro -B sekiro/build -G "NMake Makefiles"
  -DCMAKE_BUILD_TYPE=Release && cmake --build sekiro/build` -> `sekicraft.dll` + `sekicraft_core.dll` (static CRT,
  MinHook vendored); `gradlew build` in `fabric/` (JDK 25).
- **No game files:** Windows SDK and MinHook only; Sekiro's addresses are found at run time.

## Release files

| File | What it is |
| --- | --- |
| `sekicraft-0.0.1-dlls.zip` | `sekicraft\sekicraft.dll` (what me3 loads), `sekicraft\sekicraft_core.dll`, licences, NOTICE |
| `sekicraft-0.0.1.jar` | The Fabric mod for Minecraft 26.3 |
| `LICENSE-SkyCraft.txt` | SkyCraft's MIT licence |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Built by [run 40325007908](https://github.com/yousufkiani99/mashup-builds/actions/runs/40325007908) on 2026-10-26; draft release `sekicraft-v0.0.1`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `BUILD-LOG-SUMMARY.txt` | 7,420 | `3b640ad435426b4a311d538cbcf8449058b027f196dd5cc7aaf6e4f364f09c21` |
| `LICENSE-SkyCraft.txt` | 1,086 | `ddd86554d7d479eccf870d1cfeecd9480cfabe8025762776b6d784d185b21dd9` |
| `LICENSE.txt` | 1,085 | `831a4d000e92484473903ea1c783414b99cacd5907ed77314ab68ba8b211c2ee` |
| `NOTICE.txt` | 5,802 | `56c08427a4d9d7bdfadba288117b16031302b10e446eeb1f2570e3109e0fbef0` |
| `sekicraft-0.0.1-dlls.zip` | 310,647 | `2c3451800de6ac649aa51d024a7a9ae9ff0567629c65d459a8cb01c0eca54574` |
| `sekicraft-0.0.1.jar` | 249,837 | `f4443cc0f6844feb94e5df31ede58e5facc96c09d6889a77b09a18e00a51b57e` |
| `SHA256SUMS.txt` | 419 | `48d518c3242b37a6801198964aa4ef330670061d17f6feb5a40962795474fd57` |
