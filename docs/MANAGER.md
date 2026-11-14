# Multiplayer Manager 0.1.27

## INSTALL

![Manager showing independent client and server updates](images/manager-install-0.1.24.png)


Choose **INSTALL CLIENT** for the Planet Nomads game folder or **INSTALL SERVER** for a dedicated-server destination. Only the selected component and its path are required.

The manager detects each installed component separately. **UPDATE CLIENT** and **UPDATE SERVER** appear when a newer version or payload revision is available. Installing or updating one component leaves the other unchanged.

The manager includes multiplayer client **0.3.27** and dedicated server **0.3.27**. Update both components when moving to this release. Existing worlds and live server configuration are preserved during server updates.

> **Important:** Worlds created using older versions of Planet Nomads Multiplayer are not guaranteed to be compatible with this release. Back up existing worlds before updating. For the best experience, start a new world using one of the included starter worlds.

If managed files were modified outside the Manager, an update asks for confirmation and preserves copies of those files before replacing them. Declining leaves the installation unchanged.

## SERVER

![SERVER screen](images/server.jpg)

Choose the server's world, name, port, password, administrator and backup settings. The redesigned SERVER page uses a two-column layout, with gameplay configuration alongside the server connection and hosting settings.

### World / Gameplay Configuration

![Manager 0.1.27 per-world gameplay configuration](images/manager-world-settings.jpg)

Select a world under **SAVE WORLD**. Its gameplay settings load automatically. You can change these settings for an existing world without generating new terrain:

| Setting | Purpose |
| --- | --- |
| Game Mode | Select Survival, Free Roam or Creative. |
| Day/Night Cycle Length | Length of the day/night cycle in minutes. |
| Night Speed | Night-time progression multiplier. |
| Day Slowdown | Daytime progression slowdown. |
| Player Attributes Effect | Survival attribute difficulty. |
| Ore Excavation by Mining Machines | Mining-machine excavation setting. |
| Gathering Multiplier | Resource gathering yield. |
| Animal Nest Density | Density of animal nests. |
| Bad Weather Reduction | Reduction of bad-weather effects. |
| Aggressive Animals | Enable or disable aggressive animals. |
| Aggressive Flora | Enable or disable aggressive flora. |
| Weather | Enable or disable weather. |

Click **SAVE SETTINGS** to apply changes. Restart a running server to load the saved configuration.

> **Creative mode warning:** Switching an existing Survival or Free Roam world to Creative can permanently unlock technology for that world. Switching back does not undo those unlocks. The Manager displays a warning when Creative is selected; **UNDERSTOOD** dismisses the warning without saving the settings. Back up the entire world before changing to Creative.

The three included [starter worlds](SERVER.md#included-starter-worlds) offer different terrain and resource environments.

## LAUNCH

![LAUNCH screen](images/launch.jpg)

Start the dedicated server inside the manager without opening another console window. Its live output appears here, together with server name, version, world, status and player count.

Buttons: **LAUNCH SERVER**, **SAVE**, **SHUTDOWN**, **RESTART**.

## PLAY GAME

Launches the original Planet Nomads game. The manager stays open on the same page so you can watch server activity on another monitor.

## OPTIONS

![OPTIONS screen](images/options.jpg)

- **LAUNCHER MUSIC** and **UI SFX** — sound on/off.
- **WORLD BACKUPS** — automatic or manual.
- **GAME ARGUMENTS** — additional game launch options.
- **BACKUP PROFILE** and **RESTORE PROFILE** — back up your saves and multiplayer identity.
