# Mojave in Skyrim 0.2.0: community build

Unofficial build for the Mashup Library. Release tag `mojave-in-skyrim-v0.2.0` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/Pitorad/mojave-in-skyrim/tree/58520efa9e7905421065ba866a7df4968dc36e43
- **Licence:** GPL-3.0-or-later (Pitorad); CommonLibSSE-NG MIT, miniaudio public domain / MIT-0. LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-mojave-in-skyrim.yml`](../../.github/workflows/build-mojave-in-skyrim.yml)

- **Pins:** `58520efa9e7905421065ba866a7df4968dc36e43` (0.2.0); submodules CommonLibSSE-NG
  `94faaed0c60eddd8347767f2d4d29a97c93bde8c`, miniaudio `9634bedb5b5a2ca38c1ee7108a9358a4e233f14d`; vcpkg at the
  manifest's `builtin-baseline` `ee12231b20c95013c6638d845d04c91559a1d1ff`.
- **Built with the repo's CMake presets:** `cmake --preset default` and `cmake --build --preset release` (Ninja
  Multi-Config, MSVC x64 from Visual Studio 2022 as in the creator's MODLOG, `windows-2022` image; vcpkg at
  `../.tools/vcpkg`) -> `build/RelWithDebInfo/MojaveInSkyrim.asi`.
- `src/generated/Sheets.h` and `package/MojaveInSkyrim.ini` are committed outputs of `tools/sheets.py gen`, whose
  preflight needs Skyrim SE and Fallout: New Vegas installed. After `cmake --preset default`, that one command in the
  generated `build/**/*.ninja` files is replaced with a no-op, so the committed files are used; the build fails if either
  changes. The creator's code is not changed and no game file is read.
- Packaged like the creator's `tools/package.py` minus the Address Library files (meh321's; not ours to ship).
- **GPL source:** `mojave-in-skyrim-0.2.0-source.zip` = the repo and both submodules at the pinned commits, plus the
  source archives vcpkg downloaded for the statically linked libraries, with BUILD.txt. Eight macOS framework symlinks
  in CommonLibSSE-NG's openvr submodule are stored as text files holding their target, as git does without symlinks.

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

Built by [run 40333402498](https://github.com/yousufkiani99/mashup-builds/actions/runs/40333402498) on 2026-10-26; draft release `mojave-in-skyrim-v0.2.0`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `BUILD-LOG-SUMMARY.txt` | 26,327 | `d339eb63e4478df35454fef2483873bc918e3764f1163935aaa1b1662ed91f4b` |
| `LICENSE.txt` | 35,823 | `230184f60bae2feaf244f10a8bac053c8ff33a183bcc365b4d8b876d2b7f4809` |
| `mojave-in-skyrim-0.2.0-source.zip` | 164,818,197 | `4596163d2c0cece201157f7b102acc29743d5e2337b4d6db84b3b73f536df4c0` |
| `mojave-in-skyrim-0.2.0.zip` | 996,526 | `9146df8b98dd12c275dd0732c585a3dd04103ae0af7406077fda7f68ab4b10ac` |
| `NOTICE.txt` | 2,964 | `c62961be0ef12bb0b725bc0f972450c05c3f2c087aab75bec3b85ff454aa7866` |
| `SHA256SUMS.txt` | 348 | `fbd2da97b567ad7c8823992e52845a4b6ce0b38a6456d93b90e6b503086348e0` |
