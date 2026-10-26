# SekiCraft 0.0.1: community build

Unofficial build for the Mashup Library. Release tag `sekicraft-v0.0.1` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/NIHKOOL/SekiCraft/tree/c671e82104b5a66493d15154b61bccbec6d4b0b6
- **Pinned commit:** `c671e82104b5a66493d15154b61bccbec6d4b0b6`
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

Not built yet.
