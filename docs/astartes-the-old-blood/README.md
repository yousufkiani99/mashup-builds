# Astartes: The Old Blood 1.0.4: community build

Unofficial build for the Mashup Library. Release tag `astartes-the-old-blood-v1.0.4` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/Sebianer/astartes-old-blood/tree/ca7244a65b8e9fcac713cce822eaea5dd51c7d48
- **Pinned commit:** `ca7244a65b8e9fcac713cce822eaea5dd51c7d48`
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

Not built yet.
