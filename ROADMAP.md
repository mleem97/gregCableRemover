# Roadmap

Mass Cable Remover is intentionally small and focused. This roadmap tracks maintenance and UX improvements without expanding the mod into a broader network-management tool.

## Current release

### 0.1.1

- Configurable aim/charge keybinds via `MassCableRemover_Keybinds.txt`
- Device cable removal for switches and patch panels
- 10-second world cable purge when no device is targeted
- IMGUI charge ring and warning prompts
- Legacy Unity input compatibility patches

## Planned focus areas

- Safer UX around the world purge flow
- Clearer in-game messaging for target state and cancellation
- Optional gregFramework integration hooks when `gregCore.dll` is present
- Build and packaging consistency with the other gregMod repositories
- Documentation improvements for install, references, and troubleshooting

## Maintenance rules

- Keep behavior changes explicit and documented.
- Prefer small, reviewable pull requests.
- Keep runtime identity stable unless a migration plan exists.
- Avoid bundling proprietary game or MelonLoader assemblies in release commits.
