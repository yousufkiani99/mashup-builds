# PalCraft 0.2.2: community build

Unofficial build for the Mashup Library. Release tag `palcraft-v0.2.2` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/EQQX0/PalCraft/tree/1431332b4cf75603e80cf4ce137347cebf880807
- **Pinned commit:** `1431332b4cf75603e80cf4ce137347cebf880807`
- **Licence:** MIT (PalCraft contributors; with siddoff's and justbustin's MIT notices). LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-palcraft.yml`](../../.github/workflows/build-palcraft.yml)

- **Pinned commit:** `1431332b4cf75603e80cf4ce137347cebf880807` (0.2.2 code).
- **Built with the creator's own scripts:** `python tools/gen.py --check`; `bash tools/build_native.sh` with llvm-mingw
  20261006 (the official `llvm-mingw-20261006-ucrt-x86_64.zip`, SHA-256 `317492c4…f52d17a`, pinned) unpacked where the
  script looks for it (`.tools/compiler/`), and the generated files it rewrites must equal the commit; `gradlew build` in
  `mc/` (JDK 25); the mod zip from `tools/package.py`'s `build_host()`, which never packs `runtime_dir.txt` or `dev.lua`.
- **No game files:** the Lua side uses UE4SS reflection at run time; the DLL hooks D3D11. UE4SS is not included.

## Release files

| File | What it is |
| --- | --- |
| `PalCraft-0.2.2.zip` | `Pal\Binaries\Win64\Mods\PalCraft\`: enabled.txt, palcraft.dll, Scripts\*.lua, notices |
| `palcraft-0.2.2.jar` | The Fabric mod for Minecraft 1.21.1 |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Not built yet.
