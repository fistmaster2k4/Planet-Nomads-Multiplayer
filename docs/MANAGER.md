# Multiplayer Manager 0.1.24

## INSTALL

![Manager 0.1.24 showing independent client and server updates](images/manager-install-0.1.24.png)


Choose **INSTALL CLIENT** for the Planet Nomads game folder or **INSTALL SERVER** for a dedicated-server destination. Only the selected component and its path are required.

The manager detects each installed component and its version separately. **UPDATE CLIENT** and **UPDATE SERVER** appear when the manager contains a newer corresponding version. Installing or updating one component leaves the other unchanged.

The manager includes client **0.3.9** and dedicated server **0.3.8**. Both use the matching `v4-env1` protocol.

If managed files were modified outside the Manager, an update asks for confirmation and preserves copies of those files before replacing them. Declining leaves the installation unchanged.

## SERVER

![SERVER screen](images/server.jpg)

Choose the server's world, name, port, password, administrator and backup settings. Click **SAVE SETTINGS** to apply changes.

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
