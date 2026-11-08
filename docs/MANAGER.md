# Multiplayer Manager 0.1.21

## INSTALL

Finds compatible Planet Nomads installations (Steam/common GOG locations or manual selection), installs/upgrades the client plugin and dedicated server payloads, and supports a single managed uninstall action. Client plugin 0.3.8 and server 0.3.7 are bundled with this build.

## SERVER

Edits dedicated-server configuration for server name, world, TCP port, bind IP, player limit, password, administrator and backup policy. The forwarding reminder updates when the configured port changes.

## LAUNCH

The manager launches the dedicated server **silently** (no additional terminal), captures standard output/error into its embedded console and displays:

- Server name, version, world, port and locally observed online/offline status.
- Player count tracked from server connection/disconnection console messages.
- **LAUNCH SERVER**, **SAVE**, **SHUTDOWN**, **RESTART** buttons.

The player list and kick/ban actions are not yet implemented. The displayed online status is derived from the process and its console, **not from a server query listener**.

## PLAY GAME

Immediately launches the configured original `PlanetNomads.exe`, without replacing the currently displayed manager page. The manager can remain open on another monitor showing server logs. Launcher audio is suppressed while the game or server is active.

## OPTIONS

- **LAUNCHER MUSIC** — ON/OFF.
- **UI SFX** — ON/OFF.
- **WORLD BACKUPS** — AUTO/MANUAL selection for player profile backup behaviour.
- **GAME ARGUMENTS** — additional launch arguments.
- **ENVIRONMENT** — semicolon-delimited `NAME=VALUE` entries for the launched game.
- **BACKUP PROFILE** / **RESTORE PROFILE** — player settings, local saves and multiplayer identity.

Settings are saved under `%LOCALAPPDATA%\PlanetNomadsMultiplayerManager\manager.cfg`.

## Known limitation

The embedded console's player count is based on observed connect/disconnect messages and is only authoritative for the server process started by the manager. A future server query endpoint should replace that inference.
