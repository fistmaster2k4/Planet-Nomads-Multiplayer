# Installation

![INSTALL screen](images/install.jpg)

1. Run `PlanetNomadsManager-0.1.21-Setup.exe`.
2. Open **Planet Nomads Multiplayer Manager** using the desktop icon or Start Menu.
3. Under **INSTALL**, select your existing Planet Nomads game folder and a destination for the dedicated server.
4. Enter your player name and install the multiplayer components.
5. Under **SERVER**, choose the world, server name, player limit, port and optional password. Click **SAVE SETTINGS**.
6. Under **LAUNCH**, click **LAUNCH SERVER**. Use **PLAY GAME** to start Planet Nomads.

**Requirements:** Planet Nomads **1.0.7.2** and the **.NET 8 Desktop Runtime (x64)**. The original game is available from [Planet Nomads on GOG](https://www.gog.com/en/game/planet_nomads).

### GOG version: temporary installation fix

The GOG installation does not include the `version.txt` file expected by Multiplayer Manager 0.1.21. The GOG edition has been tested installing the mod, launching the game and joining a dedicated server with this workaround:

1. Download [version.txt](../version.txt) from this repository (open the link and select **Download raw file**).
2. Copy `version.txt` into your **Planet Nomads game installation folder** — the same folder containing `PlanetNomads.exe`.
3. Open the Multiplayer Manager, select that game folder under **INSTALL**, and continue with the steps above.

This file only helps the Manager recognise the GOG installation; it does not modify the game itself.

A ready-to-play server world is included. To use your own single-player world, follow the [world setup instructions](SERVER.md#using-your-own-world).

## Updates and removal

- **UPGRADE** updates installed multiplayer components when newer versions are included.
- **UNINSTALL** in the manager removes its installed client/server components without deleting saved worlds.
- Windows **Uninstall** removes the manager application and shortcuts.

## Player backup

Under **OPTIONS**, use **BACKUP PROFILE** to save your player configuration, local saves and multiplayer identity. **RESTORE PROFILE** restores that backup.

**Keep profile backup ZIPs private.** They contain the identity information used by your multiplayer character.
