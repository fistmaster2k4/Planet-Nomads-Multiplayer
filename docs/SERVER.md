# Dedicated server

**Current dedicated-server version: 0.3.7.** It runs separately from the original game and is managed by the Windows launcher.

## World folder

The server selects the world by its **folder name**:

```text
<dedicated-server-directory>/
  NomadsDedicated.exe
  server.cfg
  Saves/
    Day1/
      _working.db
      _main.db
      ...
```

For that folder, `server.cfg` must contain `World=Day1`. **Do not put `World=` inside a folder name.** The internal database save name does not replace this configuration mapping.

The manager includes the `Day1` world and preserves existing world saves during upgrades and removal.

## Default world

A ready-to-play **Day1** world is included with the dedicated-server installation. You can launch the server using this world without creating a new save.

## Using your own world

1. Launch the original **Planet Nomads** game.
2. Start a **new single-player game** or create a **custom single-player world**.
3. Once you've entered the world, **save the game**, then quit Planet Nomads.
4. Open File Explorer and paste this into its address bar:

   ```text
   %USERPROFILE%\AppData\LocalLow\Craneballs\PlanetNomads\Saves
   ```

5. Find the folder containing your newly saved world and **copy that entire folder**.
6. Open the dedicated-server installation folder you selected in the manager. Inside its `Saves` folder, paste the copied world folder. For example, if your server was installed to `E:\NomadsDedi`, the result could be:

   ```text
   E:\NomadsDedi\Saves\MyWorld
   ```

7. Open the **Planet Nomads Multiplayer Manager**, select **SERVER**, and choose `MyWorld` from the **SAVE WORLD** dropdown. Click **SAVE SETTINGS**.
8. Select **LAUNCH**, then **LAUNCH SERVER**.

Keep the original single-player world as a backup. The manager lists available worlds when you open the SERVER page, so revisit that page if you copied the folder while the manager was already open.

## Configuration

![Manager SERVER panel showing world, server name, port, player limit, administrator and backup settings](images/server.jpg)

The **SERVER** panel edits `server.cfg` without overwriting unrelated keys or comments.

| Key | Purpose |
| --- | --- |
| `World` | Directory name directly beneath `Saves` |
| `ServerName` | Human-readable server name |
| `Port` | TCP gameplay port; default **6553** |
| `BindIP` | Local network interface; `0.0.0.0` binds all interfaces |
| `MaxPlayers` | Server player limit |
| `Password` | Optional server password |
| `BackupIntervalSeconds` | Server backup frequency, range 60–86400 |
| `BackupKeepCount` | Retained backups (0 = unlimited, maximum 10000) |
| `AdminPlayerId` | Persistent configured administrator identity, provisioned by the manager |

The manager also records the configured admin player name and securely provisions the corresponding local identity token. Player names alone are not trusted as authentication.

## Network ports

For default configuration:

- **6553/TCP:** Game connections (implemented).
- **6554/TCP:** Reserved as the proposed query port (game port + 1); **query listener not yet implemented**.

The manager displays a dynamic reminder of both ports, but **forwarding 6554 alone does not enable querying in 0.3.7**. Forward the gameplay port through the router and permit it through Windows Firewall when accepting external clients.

Use a LAN IP or `0.0.0.0` for `BindIP`. Do not bind to an external WAN address unless it is actually assigned to a local interface.

## Launch and commands

Start via **LAUNCH → LAUNCH SERVER** in the manager to capture the live console inside the application. The manager doesn't attach to servers started independently.

The server currently supports the console commands `status`, `save`, `quit` and `help`. Manager buttons send save/shutdown commands; **RESTART** saves, shuts down and starts the process again.

The current build does **not** provide a query endpoint, authoritative connected-player list, or kick/ban commands.
