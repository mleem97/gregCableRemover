# Mass Cable Remover

Mass Cable Remover is a MelonLoader IL2CPP mod for **Data Center**.

Hold the configurable aim key, default `LeftCtrl`, and look at a network switch or patch panel. Then hold the configurable charge input, default `RightMouse`, until the charge ring completes. The mod disconnects all cables on that device.

When you are **not** looking at a switch or patch panel, holding the same two inputs for **10 seconds** removes all cables in the loaded world. Release the keys or look at a device to cancel the world purge.

## Current version

`0.1.1`, originally created by Mochimus.

## Keybinds

On first run the mod creates this file in the game `Mods` folder:

```text
MassCableRemover_Keybinds.txt
```

Edit the file while the game is closed, then restart.

Supported values:

| Setting | Default | Accepted values |
|---------|---------|-----------------|
| `AimHoldKey` | `LeftCtrl` | Any Unity Input System `Key` name, for example `LeftCtrl`, `LeftShift`, `RightAlt`. |
| `ChargeHold` | `RightMouse` | `RightMouse`, `LeftMouse`, `MiddleMouse`, or any Unity Input System `Key` name such as `Space` or `E`. |

## Source layout

The repository is organized in the same style as the other gregMod repositories.

| Folder | Role |
|--------|------|
| `Core/` | MelonLoader entry point and Melon metadata. |
| `Config/` | Keybind config loading and input binding helpers. |
| `Networking/` | Target detection and cable disconnect logic. |
| `Patches/` | Harmony compatibility patches. |
| `UI/` | IMGUI charge ring and prompt helpers. |
| `docs/` | Source layout and project documentation. |

See [`docs/SOURCE_LAYOUT.md`](docs/SOURCE_LAYOUT.md) for the detailed file map.

## Local build

Copy `Directory.Build.props.example` to `Directory.Build.props` and set the paths for your Data Center installation.

```bash
dotnet build MassCableRemover.sln -c Release
```

To also copy the built DLL into the game `Mods` folder when `DataCenterGameDir` is configured:

```bash
dotnet build MassCableRemover.sln -c Release /p:CopyToGameMods=true
```
