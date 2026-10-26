# Astartes: The Old Blood 1.0.4: community build

Unofficial build for the Mashup Library. Release tag `astartes-the-old-blood-v1.0.4` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/Sebianer/astartes-old-blood/tree/ca7244a65b8e9fcac713cce822eaea5dd51c7d48
- **Licence:** GPL-3.0 (Sebianer); MinHook BSD-2-Clause. LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-astartes-the-old-blood.yml`](../../.github/workflows/build-astartes-the-old-blood.yml)

- **Pinned commit:** `ca7244a65b8e9fcac713cce822eaea5dd51c7d48` (1.0.4).
- **Built with the creator's `tools/package.sh` steps:** `python -I tools/gen.py` without a Space Marine 2 folder (it
  reuses the committed `sheets/sfx_resolved.json`; the build fails if the generated files change); `sh hook/build.sh`
  (MSVC `cl` x64 + MinHook -> `dinput8.dll`); .NET Framework 4 `csc` -> `AstartesLauncher.exe`. `tools/msvc.bat` calls
  VS 2019 Build Tools' `vcvars64.bat` by a fixed path the runner doesn't have; the same MSVC x64 environment comes from
  `ilammy/msvc-dev-cmd`, so the creator's exact `cl` command line runs.
- **No game files.** vgmstream is not included (it comes from its own official release).
- **GPL source:** `astartes-the-old-blood-1.0.4-source.zip` (`git archive` of the pinned commit, MinHook included).

## Release files

| File | What it is |
| --- | --- |
| `astartes-the-old-blood-1.0.4.zip` | Into the Old Blood folder: `dinput8.dll`; `AstartesOldBlood\` (AstartesLauncher.exe, README.txt, licences, NOTICE) |
| `astartes-the-old-blood-1.0.4-source.zip` | Source at the pinned commit (GPL-3) |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Built by [run 40335892087](https://github.com/yousufkiani99/mashup-builds/actions/runs/40335892087) on 2026-10-26; draft release `astartes-the-old-blood-v1.0.4`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `astartes-the-old-blood-1.0.4-source.zip` | 121,043 | `5080d48c41a21307b493f4392801a0d4dad4b24d7dfc0de1deba7ea102e80bdb` |
| `astartes-the-old-blood-1.0.4.zip` | 181,247 | `ba828d7af87e3b1b9faa1099bb1abbc35e54dc506fe4a0d5d1e13d7b5f065f24` |
| `BUILD-LOG-SUMMARY.txt` | 2,412 | `00b7d0aa83cd2033be99ee49556a50e62a703fcfe14cfb911c584909fd4717f7` |
| `LICENSE.txt` | 35,823 | `230184f60bae2feaf244f10a8bac053c8ff33a183bcc365b4d8b876d2b7f4809` |
| `NOTICE.txt` | 1,448 | `c39133a488062e18e24a3e5555f9652093b9ed07f4f141191cc07289fe3266cb` |
| `SHA256SUMS.txt` | 360 | `1d53e2bb43c05a1a10645c85b0d44d3668b52ab4a19d9c11a08e1a0432b130f5` |
