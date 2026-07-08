# Contributing to Mass Cable Remover

Thanks for your interest in improving `Mass Cable Remover`.

---

## Ground Rules

- Be respectful and constructive.
- Keep changes focused and atomic.
- Use **Conventional Commits**.
- Preserve existing gameplay behavior unless the PR explicitly targets behavior changes.

---

## Development Workflow

1. Fork and create a feature branch:
   - `feat/<short-topic>`
   - `fix/<short-topic>`
   - `docs/<short-topic>`
2. Implement the change with minimal scope.
3. Build locally and validate behavior in-game.
4. Open a Pull Request using the PR template.

---

## Commit Message Format

Use Conventional Commits:

- `feat: add safer world purge confirmation`
- `fix: prevent stale target charge completion`
- `docs: update keybind instructions`
- `chore: align project metadata`

Recommended structure:

```text
<type>(optional-scope): short summary
```

Types used in this repo:

- `feat`, `fix`, `docs`, `refactor`, `test`, `chore`

---

## Build references (MelonLoader)

- Put local build DLLs in `references/` before building.
- MelonLoader binaries usually come from `Data Center/MelonLoader/net6`.
- Game, Unity, and IL2CPP assemblies usually come from `Data Center/MelonLoader/Il2CppAssemblies` after running the game once with MelonLoader.
- `gregCore.dll` is optional. If present in `references/`, the project defines `WITH_GREGCORE`.

See [`references/README.md`](references/README.md) for the expected file list.

## Coding Guidelines

- Keep compatibility with current MelonLoader + IL2CPP interop patterns.
- Prefer clear, modular logic over large monolithic methods.
- Avoid introducing new dependencies unless strictly required.
- Keep risky gameplay actions explicit and reversible where possible.

---

## Documentation Guidelines

- Documentation files must be written in **English**.
- Use consistent Markdown structure with clear headings and separators.
- Update docs when behavior, setup, or UX changes.

---

## Pull Request Checklist

Before submitting, ensure:

- [ ] Build succeeds locally
- [ ] Changes are scoped and explained
- [ ] Docs are updated (if relevant)
- [ ] Commit messages follow Conventional Commits
- [ ] No unrelated refactors mixed in

---

## Reporting Bugs / Requesting Features

Use GitHub Issues and include:

- Game version
- Mod version / branch
- Repro steps
- Expected behavior
- Actual behavior
- Logs/screenshots if applicable
