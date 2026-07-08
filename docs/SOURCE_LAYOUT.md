# Source layout

This repository follows the same high-level layout convention as the other `gregMod` repositories: entry points and metadata live in `Core/`, feature code is grouped by responsibility, and documentation lives under `docs/`.

All source files currently keep the root namespace **`MassCableRemover`** or existing sub-namespaces. The folders are primarily for navigation and separation of responsibilities.

## Folder overview

| Folder | Role |
|--------|------|
| **`Core/`** | MelonLoader entry point and assembly/Melon metadata. |
| **`Config/`** | Runtime keybind configuration loaded from `MassCableRemover_Keybinds.txt` in the game `Mods` folder. |
| **`Networking/`** | Cable target detection, vanilla hold duration lookup, and cable disconnect operations. |
| **`Patches/`** | Standalone Harmony patches for legacy Unity input compatibility. |
| **`UI/`** | IMGUI charge ring and user-facing visual feedback helpers. |
| **`docs/`** | Repository documentation. |

## File map

### Core/

| File | Role |
|------|------|
| `Main.cs` | MelonLoader entry point (`Mod`), Harmony patching, update loop, device/world purge charge flow, and IMGUI prompt dispatch. |
| `MelonModInfo.cs` | Assembly-level metadata and MelonLoader attributes. |

### Config/

| File | Role |
|------|------|
| `InputBindSettings.cs` | Creates and loads keybind settings, validates Input System key names, exposes aim/charge state helpers. |

### Networking/

| File | Role |
|------|------|
| `LookTargetResolver.cs` | Resolves the switch or patch panel under the center-screen ray. |
| `InteractHoldDuration.cs` | Reads vanilla interact hold duration from the target device ports, with a fallback duration. |
| `CableDisconnectService.cs` | Disconnects all cables on one switch/patch panel or across the loaded world. |

### UI/

| File | Role |
|------|------|
| `MassRemoveChargeRing.cs` | Draws the IMGUI charge ring used by device and world cable removal. |

## Build notes

The project file **`MassCableRemover.csproj`** stays at the repository root. SDK-style project inclusion picks up all `*.cs` files under the project directory, excluding ignored build outputs such as `bin/` and `obj/`.

Copy `Directory.Build.props.example` to `Directory.Build.props` locally and set the Data Center install paths before building.
