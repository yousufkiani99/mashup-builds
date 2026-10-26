# Mojave in Skyrim 0.2.0: community build

Unofficial build for the Mashup Library. Release tag `mojave-in-skyrim-v0.2.0` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/Pitorad/mojave-in-skyrim/tree/58520efa9e7905421065ba866a7df4968dc36e43
- **Pinned commit:** `58520efa9e7905421065ba866a7df4968dc36e43`
- **Licence:** GPL-3.0-or-later (Pitorad); CommonLibSSE-NG MIT, miniaudio public domain / MIT-0. LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-mojave-in-skyrim.yml`](../../.github/workflows/build-mojave-in-skyrim.yml)

- **Pins:** `58520efa9e7905421065ba866a7df4968dc36e43` (0.2.0); submodules CommonLibSSE-NG
  `94faaed0c60eddd8347767f2d4d29a97c93bde8c`, miniaudio `9634bedb5b5a2ca38c1ee7108a9358a4e233f14d`; vcpkg at the
  manifest's `builtin-baseline` `ee12231b20c95013c6638d845d04c91559a1d1ff`.
- **Built with the repo's CMake presets:** `cmake --preset default` and `cmake --build --preset release` (Ninja
  Multi-Config, MSVC x64, vcpkg at `../.tools/vcpkg`) -> `build/RelWithDebInfo/MojaveInSkyrim.asi`.
- `src/generated/Sheets.h` and `package/MojaveInSkyrim.ini` are committed outputs of `tools/sheets.py gen`, which reads
  game files. The workflow touches both so CMake never runs it, and fails if either changes. No game file is read.
- Packaged like the creator's `tools/package.py` minus the Address Library files (meh321's; not ours to ship).
- **GPL source:** `mojave-in-skyrim-0.2.0-source.zip` = the repo and both submodules at the pinned commits, plus the
  source archives vcpkg downloaded for the statically linked libraries, with BUILD.txt.

## Release files

| File | What it is |
| --- | --- |
| `mojave-in-skyrim-0.2.0.zip` | Into the Skyrim SE folder: `MojaveInSkyrim.asi`, `MojaveInSkyrim.ini`, `Data\SKSE\Plugins\MojaveInSkyrim\` (README, licences, NOTICE) |
| `mojave-in-skyrim-0.2.0-source.zip` | Complete source as built (GPL-3) |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Not built yet.
