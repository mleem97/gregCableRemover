# Source layout

This repository follows the same high-level layout convention as the other `gregMod` repositories: entry points and metadata live in `Core/`, feature code is grouped by responsibility, GitHub metadata lives under `.github/`, and documentation lives under `docs/`.

All source files currently keep the root namespace **`MassCableRemover`** or existing sub-namespaces. The folders are primarily for navigation and separation of responsibilities.

## Folder overview

| Folder | Role |
|--------|------|
| **`.github/`** | Funding metadata, issue templates, pull request template, and build workflow. |
| **`Core/`** | MelonLoader entry point and assembly/Melon metadata. |
| **`Config/`** | Runtime keybind configuration loaded from `MassCableRemover_Keybinds.txt` in the game `Mods` folder. |
| **`Networking/`** | Cable target detection, vanilla hold duration lookup, and cable disconnect operations. |
| **`Patches/`** | Standalone Harmony patches for legacy Unity input compatibility. |
| **`UI/`** | IMGUI charge ring and user-facing visual feedback helpers. |
| **`references/`** | Local build reference DLL inputs. |
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

### .github/

| File | Role |
|------|------|
| `FUNDING.yml` | GitHub Sponsors and gregFramework funding links. |
| `pull_request_template.md` | Standard gregMod PR checklist. |
| `ISSUE_TEMPLATE/bug_report.md` | Bug-report issue template. |
| `ISSUE_TEMPLATE/feature_request.md` | Feature-request issue template. |
| `workflows/build.yml` | .NET build workflow that is reference-aware. |

### references/

| File | Role |
|------|------|
| `README.md` | Documents required local reference DLLs for building. |
| `.gitkeep` | Keeps the folder in the repository without committing DLLs. |

## Build notes

The project file **`MassCableRemover.csproj`** stays at the repository root. SDK-style inclusion picks up all `*.cs` files under the project directory, excluding ignored build outputs such as `bin/` and `obj/`.

The project resolves build inputs from **`references/`**, matching the convention used by the other gregMod repositories. Copy the required MelonLoader, IL2CPP, Unity, and game assemblies into that folder before building locally.
