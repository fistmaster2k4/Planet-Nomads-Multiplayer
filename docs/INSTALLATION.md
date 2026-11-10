# Installation

## Windows — Multiplayer Manager 0.1.22

![INSTALL screen](images/install.jpg)

1. Download the **0.1.22 Manager installer** from [GitHub Releases](https://github.com/fistmaster2k4/Planet-Nomads-Multiplayer/releases) and run the setup executable.
2. Open **Planet Nomads Multiplayer Manager** using its desktop icon or Start Menu shortcut.
3. Under **INSTALL**, choose the component you want:
   - **INSTALL CLIENT** — select your existing Planet Nomads game folder (containing `PlanetNomads.exe`), enter your player name, then install.
   - **INSTALL SERVER** — select a dedicated-server destination, then install.
4. You can install either component without installing the other. If you install the second component later, the first installation is left unchanged.
5. For server hosting, open **SERVER**, choose the world, name, player limit, port and optional password, then click **SAVE SETTINGS**.
6. Under **LAUNCH**, click **LAUNCH SERVER**. Use **PLAY GAME** to launch the client if installed locally.

**Manager requirements:** Windows 10/11 and **.NET 8 Desktop Runtime (x64)**. Client installation also requires Planet Nomads **1.0.7.2**. The original game is available from [GOG](https://www.gog.com/en/game/planet_nomads).

A ready-to-play server world is included. To use your own single-player world, follow the [world setup instructions](SERVER.md#using-your-own-world).

## Standalone client — manual installation

The [Standalone Client v0.3.8 release](https://github.com/fistmaster2k4/Planet-Nomads-Multiplayer/releases) provides the client without the manager.

1. Download `Planet Nomads Client 0.3.8.zip` from the standalone client release.
2. Open the Planet Nomads installation folder containing `PlanetNomads.exe`.
3. Extract the ZIP **directly into that folder**, preserving its directory structure. It includes BepInEx 5.4.23.6, the multiplayer plugin, TNet libraries, BepInEx configuration, Doorstop and `winhttp.dll`.
4. Launch the game and select **Multiplayer** on the main menu.

### SteamOS / Linux using Proton (experimental)

For the standalone client under Proton, set the game's **Steam → Properties → General → Launch Options** to:

```text
WINEDLLOVERRIDES="winhttp=n,b" %command%
```

This makes Proton load the supplied BepInEx `winhttp.dll` proxy before Wine's built-in DLL. Without the override, the game may launch while BepInEx and the multiplayer menu do not.

SteamOS/Linux client support is experimental.

**Dedicated-server hosting is Windows-only.** The standalone ZIP contains the client, not the server.

## Updates and removal

- The manager detects the client and server independently. **UPDATE CLIENT** or **UPDATE SERVER** appears when the included version is newer than the installed component.
- Updating one component leaves the other unchanged.
- **UNINSTALL** removes manager-managed client/server files while preserving saved worlds and unrelated files. Modified managed files may be retained.
- Windows **Uninstall** removes the manager application and shortcuts.

## Player backup

Under **OPTIONS**, use **BACKUP PROFILE** to save your player configuration, local saves and multiplayer identity. **RESTORE PROFILE** restores that backup.

**Keep profile backup ZIPs private.** They contain the identity information used by your multiplayer character.
