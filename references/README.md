# Build references

Place local build reference DLLs in this folder before running `dotnet build`.

The project file resolves references from `references/` to match the convention used by the other gregMod repositories.

Required files:

```text
MelonLoader.dll
0Harmony.dll
Il2CppInterop.Runtime.dll
Assembly-CSharp.dll
Il2Cppmscorlib.dll
Il2CppSystem.dll
Il2CppSystem.Core.dll
Il2Cpp__Generated.dll
UnityEngine.CoreModule.dll
UnityEngine.PhysicsModule.dll
UnityEngine.IMGUIModule.dll
Unity.InputSystem.dll
UnityEngine.InputLegacyModule.dll
UnityEngine.TextRenderingModule.dll
UnityEngine.UI.dll
```

Optional:

```text
gregCore.dll
```

Typical source locations after running Data Center once with MelonLoader:

- `Data Center/MelonLoader/net6/` for `MelonLoader.dll`, `0Harmony.dll`, and `Il2CppInterop.Runtime.dll`
- `Data Center/MelonLoader/Il2CppAssemblies/` for game, Unity, and IL2CPP assemblies

Reference DLLs are not committed by default. They are local build inputs copied from the game/MelonLoader installation.
