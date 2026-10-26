# PalCraft 0.2.2: community build

Unofficial build for the Mashup Library. Release tag `palcraft-v0.2.2` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/EQQX0/PalCraft/tree/1431332b4cf75603e80cf4ce137347cebf880807
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

Built by [run 40324187634](https://github.com/yousufkiani99/mashup-builds/actions/runs/40324187634) on 2026-10-26; draft release `palcraft-v0.2.2`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `BUILD-LOG-SUMMARY.txt` | 7,618 | `b4cd7f3a0b7369a9e94327c14cbe7cad2d58ea0db80b11853659ceabefcd8107` |
| `LICENSE.txt` | 1,193 | `917e5850ae3c858c08a7cc931a64bb5e209fbac261abb962f1fa350b8a0949e7` |
| `NOTICE.txt` | 1,707 | `ebcfe78fcb45f69d4a7ec2e67b4eef8e2d0b239349b1f40307effc5db8394646` |
| `palcraft-0.2.2.jar` | 309,778 | `ffa782795ac97001c982c513b51830665a0763d65e2e5101a047422e2345007a` |
| `PalCraft-0.2.2.zip` | 89,550 | `89b88fa6beaf02e2d4d408ffe3a0f0df07c9f95631a0809180e48b98c197b28c` |
| `SHA256SUMS.txt` | 325 | `d19665b22bafe3fe0b0bd38652335f65f011db61ad5483f7360e8c68effc99ea` |
