# Installation

## Windows — Multiplayer Manager 0.1.27

![INSTALL screen](images/install.jpg)

1. Download the **0.1.27 Manager installer** from [GitHub Releases](https://github.com/fistmaster2k4/Planet-Nomads-Multiplayer/releases) and run the setup executable.
2. Open **Planet Nomads Multiplayer Manager** using its desktop icon or Start Menu shortcut.
3. Under **INSTALL**, choose the component you want:
   - **INSTALL CLIENT** — select your existing Planet Nomads game folder (containing `PlanetNomads.exe`), enter your player name, then install.
   - **INSTALL SERVER** — select a dedicated-server destination, then install.
4. You can install either component without installing the other. If you install the second component later, the first installation is left unchanged.
5. For server hosting, open **SERVER**, choose the world, name, player limit, port and optional password, then click **SAVE SETTINGS**.
6. Under **LAUNCH**, click **LAUNCH SERVER**. Use **PLAY GAME** to launch the client if installed locally.

**Manager requirements:** Windows 10/11 and **.NET 8 Desktop Runtime (x64)**. Client installation also requires Planet Nomads **1.0.7.2**. The original game is available from [GOG](https://www.gog.com/en/game/planet_nomads).

Three ready-to-play starter worlds are included: Day1, Day2 and Day3. See [starter worlds](SERVER.md#included-starter-worlds) for their different terrain settings. To use your own single-player world, follow the [world setup instructions](SERVER.md#using-your-own-world).

## Standalone client — manual installation

The [standalone client releases](https://github.com/fistmaster2k4/Planet-Nomads-Multiplayer/releases) provide the client without the manager. Choose the **0.3.27 Standalone Client** package. A matching 0.3.27 dedicated server is required.

1. Download `PlanetNomadsMultiplayer-Client-0.3.27.zip` from the latest standalone client release.
2. Open the Planet Nomads installation folder containing `PlanetNomads.exe`.
3. Extract the ZIP **directly into that folder**, preserving its directory structure. It includes BepInEx 5.4.23.6, the multiplayer plugin, TNet libraries, BepInEx and multiplayer configuration files, Doorstop and `winhttp.dll`.
4. Launch the game and select **Multiplayer** on the main menu.

### SteamOS / Linux using Proton (experimental)

For the standalone client under Proton, set the game's **Steam → Properties → General → Launch Options** to:

```text
WINEDLLOVERRIDES="winhttp=n,b" %command%
```

This makes Proton load the supplied BepInEx `winhttp.dll` proxy before Wine's built-in DLL. Without the override, the game may launch while BepInEx and the multiplayer menu do not.

BepInEx and TNet have loaded and connected under Proton on Steam Deck, but multiplayer world loading has not been confirmed working. SteamOS/Linux client support is experimental.

**Dedicated-server hosting is Windows-only.** The standalone ZIP contains the client, not the server.

## Updates and removal

> **Important:** Worlds created using older versions of Planet Nomads Multiplayer are not guaranteed to be compatible with this release. Back up existing worlds before updating. For the best experience, start a new world using one of the included starter worlds.

![Separate client and server update controls in Manager](images/manager-install-0.1.24.png)

The INSTALL screen has separate client and server destinations. Once a component is installed, its button becomes **UPDATE CLIENT** or **UPDATE SERVER** when a newer version is available.


- The manager detects the client and server independently. **UPDATE CLIENT** or **UPDATE SERVER** appears when the included version is newer than the installed component.
- Updating one component leaves the other unchanged.
- If managed files were changed outside the Manager, the update asks for confirmation and backs up the modified versions before replacement.
- **Manager 0.1.27 includes client and dedicated server 0.3.27.** Update both components for this release; older clients and servers are not supported as a matching pair.
- Server updates preserve existing worlds and live server configuration.
- **UNINSTALL** removes manager-managed client/server files while preserving saved worlds and unrelated files. Modified managed files may be retained.
- Windows **Uninstall** removes the manager application and shortcuts.

## Player backup

Under **OPTIONS**, use **BACKUP PROFILE** to save your player configuration, local saves and multiplayer identity. **RESTORE PROFILE** restores that backup.

**Keep profile backup ZIPs private.** They contain the identity information used by your multiplayer character.
