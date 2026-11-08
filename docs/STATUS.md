# Current tested status

Baseline as of **8 November 2026**.

| Area | Status |
| --- | --- |
| Windows manager 0.1.21 installer | **Tested:** installer runs, manager launches, desktop + Start Menu shortcuts exist |
| Server 0.3.7 managed launch | **Tested:** starts without a separate console, output visible in manager |
| Manager save / restart / shutdown | **Tested:** save, clean shutdown and restart workflow demonstrated |
| Game launch | **Tested:** original `PlanetNomads.exe` launches; manager remains available |
| Client 0.3.8 join | **Tested:** joins dedicated server; original single-player menu options restored |
| World selection | **Tested:** custom world loaded from `Saves/<World>` |
| Profile / local admin | **Tested:** configured administrator verified after join; initial legacy `admin: False` log precedes verification |
| Server query TCP +1 | **Not implemented** |
| Player list / kick / ban in manager | **Not implemented** |
| Shared physics, tools, construction, terrain and dropped-item replication | **Incomplete** |
| Fully synchronized multiplayer clock and cryopod sleep | **Future work** |

These are internal development test results, not a general compatibility certification.

## Planned next work

1. Add a server query listener on game port + 1 with explicit machine-readable server/version/world/player status.
2. Feed the manager's real player list and later kick/ban controls from authenticated server data.
3. Continue multiplayer state synchronization: time, terrain/building edits, dropped items, inventories, remote animation and vehicles.
4. Add shared cryopod/player association and coordinated sleep only when all players participate.
5. Test clean installs and upgrades on additional Windows and game distributions.
