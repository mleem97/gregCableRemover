# Mass Cable Remover

> Fast switch, patch-panel, and world cable removal for **Data Center** — built for the **gregFramework** ecosystem.

[![Discord](https://img.shields.io/badge/Discord-Join-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/greg)
[![gregFramework](https://img.shields.io/badge/gregFramework-Website-blue?style=for-the-badge)](https://gregframework.eu)
[![License](https://img.shields.io/badge/License-Apache%202.0-green?style=for-the-badge)](./LICENSE)
[![Version](https://img.shields.io/badge/Version-0.1.1-orange?style=for-the-badge)](./ROADMAP.md)
[![GameVersion](https://img.shields.io/badge/Game%20Version-1.1.0-yellow?style=for-the-badge)]()
[![Unity](https://img.shields.io/badge/Unity-6000.5-black?style=for-the-badge&logo=unity&logoColor=white)]()

## Links

- **Website:** [gregframework.eu](https://gregframework.eu)
- **Discord / Support:** [discord.gg/greg](https://discord.gg/greg)
- **Repository:** [github.com/mleem97/gregCableRemover](https://github.com/mleem97/gregCableRemover)
- **Roadmap:** [`ROADMAP.md`](./ROADMAP.md)

## Overview

**Mass Cable Remover** is a MelonLoader IL2CPP mod for **Data Center**.

Hold a configurable aim key, default **LeftCtrl**, and look at a network switch or patch panel. Then hold a configurable charge input, default **RightMouse**, until the charge ring completes. The mod disconnects all cables on that device.

When you are **not** looking at a switch or patch panel, holding the same two inputs for **10 seconds** removes all cables in the loaded world. Release the keys or look at a device to cancel the world purge.

The project is structured like the other gregMod repositories while keeping the existing runtime identity (`MassCableRemover`) for compatibility.

## Current Features

- Switch cable mass-removal
- Patch-panel cable mass-removal
- World cable purge after a 10-second hold with no target
- Configurable aim and charge bindings via a text file in the game `Mods` folder
- IMGUI charge ring feedback
- Legacy Unity input compatibility patches for Input System-only mode
- Optional `gregCore.dll` compile-time detection

## Installation

1. Install **MelonLoader** for **Data Center**.
2. Copy the release DLL into the mod folder:

   ```text
   Game/Mods/MassCableRemover.dll
   ```

3. Start the game.
4. Hold the configured aim key while looking at a switch or patch panel, then hold the configured charge input.

## Keybinds

On first run the mod creates this file in the game `Mods` folder:

```text
MassCableRemover_Keybinds.txt
```

Edit the file while the game is closed, then restart.

| Setting | Default | Accepted values |
|---------|---------|-----------------|
| `AimHoldKey` | `LeftCtrl` | Any Unity Input System `Key` name, for example `LeftCtrl`, `LeftShift`, `RightAlt`. |
| `ChargeHold` | `RightMouse` | `RightMouse`, `LeftMouse`, `MiddleMouse`, or any Unity Input System `Key` name such as `Space` or `E`. |

## Dependencies

- **MelonLoader**

### Build only

- **Il2CppInterop**
- **Harmony**
- Unity / game interop assemblies from a local Data Center installation
- Optional: `gregCore.dll`

## Build from Source

Requirements:

- .NET 6 SDK
- local Data Center / MelonLoader installation
- local reference DLLs copied into [`references/`](references/README.md)

Build:

```bash
git clone https://github.com/mleem97/gregCableRemover.git
cd gregCableRemover
dotnet build MassCableRemover.sln -c Release
```

Release output:

```text
bin/Release/MassCableRemover.dll
```

## Project Structure

- **`Core/`** — MelonLoader entry point and mod metadata
- **`Config/`** — keybind config loading and input binding helpers
- **`Networking/`** — target detection and cable disconnect logic
- **`Patches/`** — Harmony compatibility patches
- **`UI/`** — IMGUI charge ring and prompt helpers
- **`references/`** — local build reference inputs
- **`docs/SOURCE_LAYOUT.md`** — detailed source layout

## Community & Support

Questions, feedback, testing, and modding coordination happen on the greg Discord:

- [discord.gg/greg](https://discord.gg/greg)

## Sponsors & Thanks

- **[@tobiasreichel](https://github.com/tobiasreichel)** — main sponsor

## Credits

| Role | Contributor |
|------|-------------|
| **Original Mod** | [mochimus](https://github.com/mochimus) |
| **Repository / gregMod alignment** | [mleem97](https://github.com/mleem97) / TeamGreg Modding |

## Contributing

Contributions are welcome. Useful starting points:

- report bugs or regressions as issues
- provide reproducible test cases for cable removal flows
- keep pull requests small and easy to review
- update docs when behavior, setup, or UX changes

See [`CONTRIBUTING.md`](./CONTRIBUTING.md).

## License

This project is licensed under the **Apache License 2.0**. See [`LICENSE`](./LICENSE).

## Join the gregFramework Team

Building the ultimate modding framework for Data Center is a large undertaking. gregFramework is maintained by a small core team and welcomes contributors across code, assets, documentation, testing, infrastructure, and community work.

Interested in joining the project? Send an email to **apply@gregframework.eu**, send a DM, or drop a message on [Discord](https://discord.gg/greg).

---

**gregFramework — powered by the community.**
