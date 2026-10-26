# PersonaCraft 0.1.0: community build

Unofficial build for the Mashup Library. Release tag `personacraft-v0.1.0` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/llmandres/PersonaCraft/tree/3f00c03ae7b10785ca467fba31079bc3b870f80a
- **Pinned commit:** `3f00c03ae7b10785ca467fba31079bc3b870f80a`
- **Licence:** MIT (llmandres; the link code is SkyCraft's, MIT, chasmlol). LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-personacraft.yml`](../../.github/workflows/build-personacraft.yml)

- **Built:** the Reloaded-II mod `p5rpc.personacraft` with the creator's command, `dotnet build p5rpc.personacraft -c
  Release` (.NET SDK 9, `windows-latest`). The only addition is `-p:ReloadedModsDir=<folder>`, which moves the output out
  of `%USERPROFILE%\Reloaded-II\Mods`; the code is not changed.
- **Compile-time inputs:** NuGet only (Reloaded.Mod.Interfaces 2.4.0, Reloaded.SharedLib.Hooks 1.9.0,
  Reloaded.Memory.SigScan.ReloadedII.Interfaces 1.2.0, p5rpc.lib.interfaces 1.1.0, p5rpc.inputhook.interfaces 1.0.0,
  CriFsV2Lib 2.1.2, Vortice.Direct3D11 / D3DCompiler 3.8.1). The libraries the mod needs at run time are in the mod
  folder as the build leaves them; each package's licence and SHA-256 is recorded in the build log and in NOTICE.txt.
- **LGPL libraries:** four of those DLLs are LGPL-3.0-or-later and shipped unmodified: `CriFsV2Lib.dll` 2.1.2 and
  `CriFsV2Lib.Definitions.dll` 1.1.0 (Sewer56/CriFsV2Lib tag `2.1.2` = `9bf3b9c`), `p5rpc.lib.interfaces.dll` 1.1.0
  (AnimatedSwine37/p5rpc.lib tag `1.1.0` = `6cb4bda`), `p5rpc.inputhook.interfaces.dll` 1.0.0
  (AnimatedSwine37/p5rpc.inputhook tag `1.0` = `ad78e4d`). Their source (each library project at the tag whose csproj
  has the shipped version) is `personacraft-0.1.0-lgpl-sources.zip`, with the LGPL-3.0 and GPL-3.0 texts. Vortice.* and
  SharpGen.Runtime* are MIT.
- **Not built here:** the Minecraft side (SkyCraft's own jar).
- **No game files:** Persona 5 Royal's data is read at run time from the player's own `BASE.CPK`.

## Release files

| File | What it is |
| --- | --- |
| `personacraft-0.1.0-reloaded-mod.zip` | `p5rpc.personacraft\` for Reloaded-II's Mods folder (ModConfig.json, the mod DLLs, LICENSE.txt, NOTICE.txt, LGPL-3.0.txt, GPL-3.0.txt) |
| `personacraft-0.1.0-lgpl-sources.zip` | Source of the four LGPL-3.0-or-later libraries in the mod folder, at the shipped versions |
| `LGPL-3.0.txt, GPL-3.0.txt` | Licence texts for those libraries |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Built by [run 40319981665](https://github.com/yousufkiani99/mashup-builds/actions/runs/40319981665) on 2026-10-26; draft release `personacraft-v0.1.0`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `BUILD-LOG-SUMMARY.txt` | 37,688 | `c9186daba640f41c1f1d428e51b96a15f78e5653cad6c9edd6d9b493e6df38c8` |
| `GPL-3.0.txt` | 34,674 | `fb981668c18a279e285fc4d83fba1e836cc84dd4daa73c9697d3cfd2d8aca6e0` |
| `LGPL-3.0.txt` | 42,098 | `996af0513df21f7496288951c41428a03c174e9e4a9d63665c57d670f845ccb1` |
| `LICENSE.txt` | 1,196 | `0ef3746e997e61dfd89d777822bb97e68ff4d0cd6a48256e13ebdd8ab56a1440` |
| `NOTICE.txt` | 6,686 | `c123885d80dd4d3115bbe914e42e5f7668f84c9cd9b139cbb13b942c16545bf2` |
| `personacraft-0.1.0-lgpl-sources.zip` | 181,597 | `5281491db916069f5231f2261e0567e6fec2ed90acfa4cebbc092f88dc71fd32` |
| `personacraft-0.1.0-reloaded-mod.zip` | 689,889 | `87ff2e8ba5a35adf37e5e1243d8741c8498161770d84225ae0763bac0422105d` |
| `SHA256SUMS.txt` | 516 | `531031973f3db357846e2fdec4087d72a09d660a2b3a3726536eb841474f553d` |
