# Dedicated server

**Compatibility: Planet Nomads Multiplayer supports vanilla Planet Nomads 1.0.7.2 only (Steam or GOG). Wand and imported custom blueprints that overwrite existing block IDs are not supported.**

![SERVER screen](images/server.jpg)

The current bundled dedicated server is **0.3.62**, compatible with multiplayer client **0.3.62**, supplied with Manager **0.1.34**. Update both client and server together; older versions are not compatible with 0.3.62.

> **Important:** Worlds created using older versions of Planet Nomads Multiplayer are not guaranteed to be compatible with this release. Back up existing worlds before updating. For the best experience, start a new world using one of the included starter worlds.

### Database maintenance in 0.3.59

The server automatically cleans affected container databases on startup, removing unnecessary persistent inventory transaction records while retaining current inventory and machine state. The cause of excessive database growth has also been fixed. No manual database maintenance is required.

Dropped items use server-owned shared state. Connected players can see and collect items dropped by other players, including partial stacks.

World time is owned by the dedicated server. Joining and reconnecting players must receive and apply a fresh live server-clock reply before loading completes; connected clients then advance their sky phase at the same rate rather than applying different local sun-angle speed multipliers. The server manages independent weather schedules for the game's 25 biome profiles. Client-side sky, shelter and atmospheric rendering remain native.

## Multiplayer gameplay

Small and large flight rotor configurations (idle hover, stabilisation and forward/side steering) are saved by the dedicated server, including settings captured from printed blueprints. Solar beacons use their native internal power supply; their navigation visibility, custom labels and selected icons persist. Existing vehicle physics and controls remain unchanged.

Blocks relocated using the Moving Tool retain their new placement, inventory contents and machine settings. Custom block names and action keybindings are saved by the server and shared with joining players. These settings persist through reconnects and server restarts. Previously lost names and keybindings must be reassigned.

The server maintains **shared quest objectives, completed quests, journals and discovered story logs** for everyone in the world, including returning and late-joining players.

The **Terraformer** restores harvested trees within 100 metres, using electricity and **1 seed and 5 biomass per tree** from its own inventory or connected containers. It unlocks alongside the Nuclear Generator, requires nuclear-generator-level power and takes **two in-game days per tree** at the world's configured day length. Progress persists through server restarts; electricity consumption stops once trees in range are restored. **Overlapping Terraformers cannot operate.**

In 0.3.59, routine countdown updates no longer perform obstruction checks. Restoration sites are validated when needed, and accumulated production progress is retained if no safe site is available. This reduces server processing overhead and improves inventory and vehicle responsiveness.


The server coordinates player respawning, shared sleeping, vehicle physics authority, electrical connections and battery state. Sleeping requires all connected players to agree, using Sleeping Bags or powered Cryopods. Vehicle physics authority can move between players while vehicle and electrical state remain shared.

The Biomass Stove is available from starting technology in multiplayer. It uses its own biomass-fuelled power supply to produce dried fruitage, dried meat and purified water. See the [Biomass Stove description](../README.md#new-construction-from-0327-biomass-stove).

### Vehicle cockpit occupants (introduced in 0.3.30)

Seated-player presentation now covers **both driven and undriven cockpits**, including stationary vehicles and players joining later. When two adjacent rounded cockpits are empty, **either can be occupied**: the remote seated representation follows the cockpit that actually reports occupancy and its native seat pivot. The server/client driver-admission and vehicle physics-leasing rules remain separate; being shown in a seat does not grant vehicle driving authority.

### Biomass Miner in 0.3.34

The automated Biomass Miner now works in shared multiplayer worlds. Position it in contact with terrain, supply power and monitor its drilling progress, hourly yield and output in its inventory interface. The miner uses the game's existing terrain-placement checks to establish terrain contact. Its native interface also provides an option to use connected containers when full. See [the 0.3.34 notes](../README.md#previous-release-0334).

## Included starter worlds

The dedicated server includes three pre-generated worlds, each deliberately created with different terrain settings.

| World | Terrain and starting conditions | Ideal for |
| --- | --- | --- |
| **Day1** | Very flat terrain with a low water table | Large bases, expansive construction and wheeled vehicles |
| **Day2** | Slightly raised terrain with excellent starter materials around the player | Cooperative survival and early progression |
| **Day3** | More rugged terrain | Challenging exploration and specialist vehicle engineering |

Select a world under **SERVER → SAVE WORLD**, click **SAVE SETTINGS**, then launch your server.

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

The **World / Gameplay Configuration** section also provides per-world settings for game mode, day/night cycle length, night speed, day slowdown, player attributes, mining-machine excavation, gathering multiplier, animal nest density, bad weather reduction, aggressive animals, aggressive flora and weather. See [Manager gameplay configuration](MANAGER.md#world--gameplay-configuration) for details and the Creative mode warning.

![World gameplay settings in Manager](images/manager-world-settings.jpg)

Click **SAVE SETTINGS** when finished. Restart the server to load the saved settings if it is running.

## World backups

Back up the entire selected world folder, including `_main.db`, `_working.db` and all multiplayer persistence databases, before updating or changing game modes. The multiplayer databases store construction, containers, drops, electricity, environment, players, technology and quest progression. Copying only the two native databases is appropriate for importing a new single-player world, not for preserving a complete existing multiplayer world.

## Allowing friends to connect

Forward the selected **TCP server port** through your router to the computer running the server, and allow it through Windows Firewall.

The manager also displays the following TCP port as a reminder, but the separate query service is **not active** in this version.
