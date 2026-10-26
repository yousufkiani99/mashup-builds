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
- **Not built here:** the Minecraft side (SkyCraft's own jar).
- **No game files:** Persona 5 Royal's data is read at run time from the player's own `BASE.CPK`.

## Release files

| File | What it is |
| --- | --- |
| `personacraft-0.1.0-reloaded-mod.zip` | `p5rpc.personacraft\` for Reloaded-II's Mods folder (ModConfig.json, the mod DLLs, LICENSE.txt, NOTICE.txt) |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Not built yet.
