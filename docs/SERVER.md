# Dedicated server

![SERVER screen](images/server.jpg)

The current bundled server is **v0.3.8**, compatible with multiplayer client **v0.3.10** (`v4-env1`).

The earlier v0.3.10 remote-player flashlight enhancement used the existing player-data relay without a server rebuild. **The newer v0.3.10 Dropped Items Update does require the updated dedicated server payload** supplied with Manager 0.1.26. The component version strings were not incremented for this fix; an older server reporting the same version is not sufficient.

Dropped items now use server-owned shared state. Either connected player can see and collect an item dropped by another player (verified in-game). Partial pickups, concurrent collection safeguards, reconnect/late-join recovery and restart persistence passed automated regression tests; full in-game verification of those edge cases is still pending.

World time is owned by the dedicated server. Joining and reconnecting players receive its current time, and the server manages independent weather schedules for the game's 25 biome profiles. Existing client-side sky, shelter and atmospheric presentation remain native.

## Included world

The dedicated server includes a ready-to-play world named **Day1**. Select it under **SERVER → SAVE WORLD**, save settings and launch your server.

## Using your own world

1. Launch the original **Planet Nomads**.
2. Create a new single-player game or custom single-player world.
3. Enter the world, **save**, then quit the game.
4. In Windows File Explorer, paste this location into the address bar:

   ```text
   %USERPROFILE%\AppData\LocalLow\Craneballs\PlanetNomads\Saves
   ```

5. Copy **`_main.db`** and **`_working.db`**. You don't need the numbered `save_*.db` files.
6. In your dedicated-server installation's **Saves** folder, create a new folder named after your world, such as **MyWorld**.
7. Paste the two copied files into **MyWorld**.
8. Open the manager's **SERVER** page, choose **MyWorld** from **SAVE WORLD**, then click **SAVE SETTINGS**.
9. Select **LAUNCH → LAUNCH SERVER**.

**Copy the files; don't move them.** Your original single-player save stays in place.

## Server settings

The **SERVER** screen lets you choose:

- **Save World** — the world to load.
- **Server Name** — the name of your server.
- **Max Players** — player limit.
- **Server Port** — default **6553**.
- **Bind IP** — **0.0.0.0** for all available local network interfaces.
- **Admin Player** — your chosen administrator character.
- **Backup Frequency / Rolling Backup Max** — automatic server-save backups.
- **Server Password** — optional password for joining.

Click **SAVE SETTINGS** when finished.

## Allowing friends to connect

Forward the selected **TCP server port** through your router to the computer running the server, and allow it through Windows Firewall.

The manager also displays the following TCP port as a reminder, but the separate query service is **not active** in this version.
