# SemCraft 2 0.1.0: community build

Unofficial build for the Mashup Library. Release tag `semcraft-2-v0.1.0` (created as a **draft**; published by hand after review).

- **Source:** https://github.com/animeliodas/SemCraft2/tree/66f022aa5f89f36c7e9019dda5b2a95c687248cd
- **Licence:** GPL-2.0 (animeliodas); the Minecraft frame exporter adapted from universal-modder is MIT. LICENSE.txt and NOTICE.txt (credits, third-party notices) are in the release.
- **Built unchanged:** the creator's code is never modified; the workflow checks the checkout is exactly the pinned commit.
- **Workflow:** [`.github/workflows/build-semcraft-2.yml`](../../.github/workflows/build-semcraft-2.yml)

- **Pins:** SemCraft2 `66f022aa5f89f36c7e9019dda5b2a95c687248cd`; SeriousBridge core
  `4ceff85313f5a8928a1e66f827ae11649f360f91`; Serious Sam Classics Patch SDK (SamClassicPatch/SuperProject) tag `1.9.4` =
  `b7f2ff455c03dcb2ab4dcfd44b0443762864127f` with its submodules (recorded in the build log).
- **Built:** `SemCraft2.dll` for The First Encounter 1.05 and The Second Encounter 1.07 with the creator's `sam/build.sh`
  MSBuild command (`PlatformToolset=v143`, Win32, `Release_TFE105` / `Release_TSE107`) using Visual Studio 2022 on the
  `windows-2022` image; the Fabric mod with `gradlew build` in `mc/` (JDK 25).
- **No game files:** the plugin compiles against the SDK's Serious Engine 1 headers and import libraries from Croteam's
  public 2001-2002 Serious Sam SDK (GPL-2, in the SDK's repository).
- **GPL source:** `semcraft-2-0.1.0-source.zip` holds SemCraft2, SeriousBridge and the SDK tree exactly as built, with
  BUILD.txt.

## Release files

| File | What it is |
| --- | --- |
| `semcraft-2-0.1.0-tfe.zip` | `Bin\Plugins\SemCraft2.dll` (TFE 1.05) + its LICENSE and NOTICE |
| `semcraft-2-0.1.0-tse.zip` | The same for TSE 1.07 |
| `semcraft2-0.1.0.jar` | The Fabric mod for Minecraft 26.3 (Java-WebSocket 1.6.0 inside) |
| `semcraft-2-0.1.0-source.zip` | Complete source as built (GPL-2) |
| `LICENSE.txt`, `NOTICE.txt` | Licence; what this is, credits, third-party notices |
| `SHA256SUMS.txt` | SHA-256 of every file above (checked again before the release is made) |
| `BUILD-LOG-SUMMARY.txt` | Status of each build step, the release checks and the build logs (written after the build, so not in SHA256SUMS.txt) |

Release checks (the `release` job, which runs none of the creator's code): every hash in SHA256SUMS.txt matches,
LICENSE/NOTICE are present, a GPL build has its source zip, and no file or archive entry is a game file (game
archives, Unity/game assemblies, Minecraft classes).

## Draft release

Built by [run 40323754308](https://github.com/yousufkiani99/mashup-builds/actions/runs/40323754308) on 2026-10-26; draft release `semcraft-2-v0.1.0`. Files downloaded from the draft and
hashed again; every hash matches SHA256SUMS.txt.

| File | Size (bytes) | SHA-256 |
| --- | ---: | --- |
| `BUILD-LOG-SUMMARY.txt` | 5,668 | `3be5a93f0ab9ad0086ac09477dc57fb866cc821bbc1b98b638da50b4b2c7a1cf` |
| `LICENSE.txt` | 18,431 | `189b1af95d661151e054cea10c91b3d754e4de4d3fecfb074c1fb29476f7167b` |
| `NOTICE.txt` | 4,975 | `376a5d0783859e175027e0c06f9fb4bc31805640fc4272806a0f0774dcea2d2e` |
| `semcraft-2-0.1.0-source.zip` | 40,379,078 | `fef772555a69d7b3d2160ace18800e9d5e6e55874489f828b91efed199dde4bb` |
| `semcraft-2-0.1.0-tfe.zip` | 352,570 | `20d6bf2a209b798629c980efc1031d13dfab1c31869b84761089e481acfe5f20` |
| `semcraft-2-0.1.0-tse.zip` | 353,728 | `764e05c23e6b72ae2cf6a47dafa4255499056cc7bf3c40e0ba7b58a1e11acb1a` |
| `semcraft2-0.1.0.jar` | 274,676 | `abc06a2398ce62638463c09bcebd3f6a69a7825180b39edca3954238b405ab27` |
| `SHA256SUMS.txt` | 517 | `1dd7ae15998155325c4c8ea66bd37e70c249f266b7379a1171f6eb38b78ea3cf` |
