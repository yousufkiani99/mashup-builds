# Portal Gun in Outer Wilds 0.1.0: community build

Unofficial build for the Mashup Library. Release tag `portal-gun-in-outer-wilds-v0.1.0` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/rehan-remade/universal-modder/tree/cda0d76649caa9d9ed6c8b980cdb36f4a4bdf9f8/examples/outer-wilds-portal-gun
- **Licence:** MIT (Rehan and universal-modder contributors; example by charlystereo). LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-portal-gun-in-outer-wilds.yml`](../../.github/workflows/build-portal-gun-in-outer-wilds.yml)

- **Pinned commit:** `cda0d76649caa9d9ed6c8b980cdb36f4a4bdf9f8` of rehan-remade/universal-modder, folder
  `examples/outer-wilds-portal-gun` (manifest version 0.1.0).
- **Built:** the OWML mod with the README's `dotnet build src -c Release` (.NET SDK 9, net48; `-p:ModDir=<folder>` only
  moves the output out of OWML's Mods folder) -> `charlystereo.PortalGun\` (OWPortalGun.dll, manifest.json,
  default-config.json, OWPortalGun.pdb). The converter `tools/convert.py` (with `vpk.py`, `source_mdl.py`, `vtf.py`),
  unchanged, frozen into `owpg-convert.exe` with PyInstaller 6.22.3 on Python 3.12 (numpy 2.3.4, pillow 12.3.0; every
  wheel pinned by SHA-256) so players need no Python. The workflow runs `owpg-convert.exe --help` and a run without
  Portal 2 as a smoke test.
- **Compile-time only:** NuGet `OWML` 2.16.3 and `OuterWildsGameLibs` 1.1.16.1372 (the community's reference package of
  the game's assemblies). **None of their assemblies ship:** the workflow lists every DLL/EXE in both packages with its
  SHA-256 and fails if any of them is in the mod folder or in any released file or archive, by name or by hash.
- **No game files:** the converter reads the player's own Portal 2 (`portal2/pak01_dir.vpk`) at install time and writes
  to `%LOCALAPPDATA%\OWPortalGun`. Nothing from Valve or Mobius is in these files.

## Release files

| File | What it is |
| --- | --- |
| `portal-gun-in-outer-wilds-0.1.0-mod.zip` | `charlystereo.PortalGun\` for OWML's Mods folder: OWPortalGun.dll, manifest.json, default-config.json, OWPortalGun.pdb, LICENSE, NOTICE |
| `portal-gun-in-outer-wilds-0.1.0-converter.zip` | `owpg-convert\owpg-convert.exe` + `_internal\` (Python 3.12, numpy, pillow), LICENSE, NOTICE |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes, the compile-time reference assemblies).

## Draft release

Built by [run 40337988716](https://github.com/yousufkiani99/mashup-builds/actions/runs/40337988716) on 2026-10-26; draft release `portal-gun-in-outer-wilds-v0.1.0`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `BUILD-LOG-SUMMARY.txt` | 52,126 | `24fbebdb3ab052a5220ec008a7fd5f710cb7a54f0743c518d9ac73c8aa6a68b7` |
| `LICENSE.txt` | 1,117 | `1ed1271ce16c501b07bb712dc816864f354b93b6f95620203697e2f5bc2d5023` |
| `NOTICE.txt` | 259,472 | `e8e8fb3705124c95b72b7f1f7e35294bf85f4e4d6b97ce61197d805268bd8dd6` |
| `portal-gun-in-outer-wilds-0.1.0-converter.zip` | 27,895,262 | `8c3f0ed8b76225ea49cd00923bbded0f8e8562380f49f2b8e2e1c196eacd50b4` |
| `portal-gun-in-outer-wilds-0.1.0-mod.zip` | 112,692 | `9e4b835197a8d0ec7bcb653e7dfe53c809113af28b612f5f9f7a5177e66ff1b9` |
| `SHA256SUMS.txt` | 373 | `e59b0d9963598fd2643a1d84e9159ffbd491f68a072ad7ffeebb41b9418547c8` |
