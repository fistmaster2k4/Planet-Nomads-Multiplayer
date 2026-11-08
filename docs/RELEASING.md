# Packaging and release checklist

## Windows manager

Use the **0.1.21 manager build** with its matching `InstallerPayload` and sound files. The known-good installer source uses **NSIS 3 (Unicode)**.

- Installer filename: `PlanetNomadsManager-0.1.21-Setup.exe`
- Internal working folder: `NomadsManagerPrototype` (do not append ad-hoc descriptors to folder names)
- Required alongside EXE: `PlanetNomadsManager.dll`, `.deps.json`, `.runtimeconfig.json`, `InstallerPayload`, `Assets/Sounds`
- Remove compiler debugging `*.pdb` and XML API documentation from distributable payloads, but **do not** delete a runtime DLL merely because its name contains `Pdb` (e.g. `Mono.Cecil.Pdb.dll`).
- Preserve BepInEx's `.doorstop_version` and `winhttp.dll`.
- Preserve the currently required starter-world DBs unless the manager's server installation logic is changed and tested.

An NSIS example for the uninstall registry line (quotes matter):

```nsis
WriteRegStr HKCU "${REGKEY}" "UninstallString" '"$INSTDIR\\Uninstall.exe"'
```

Check the source line against the working installer script before publishing.

## Release validation

- [x] 0.1.21 installer successfully compiled by maintainer.
- [x] Installer starts manager and creates desktop and Start Menu shortcuts.
- [ ] Confirm uninstaller behaviour on a clean test account.
- [ ] Verify client/server upgrade and data preservation on a fresh install.
- [ ] Review redistribution rights for bundled third-party runtimes and game-derived Unity assemblies.
- [ ] Ensure the starter world contains no personal/private gameplay data and can be redistributed.
- [ ] Upload signed/hashed release asset and attach clear release notes.
- [ ] Publish documentation after checking against final binaries.

**Never commit** profiles, `playerConfig.xml`, private multiplayer identity tokens, server passwords, logs, original paid game files, or personal world databases to this repository.

## Distribution policy

The project source remains private. This repository carries documentation and compiled release packages only, after the necessary redistribution review. Build and staging directories stay local to the maintainer; do not commit client, server or manager source.
