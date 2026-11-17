# Sharing Blueprints — Steam and GOG

Planet Nomads can export construction blueprints locally through the **Replicator**, including on GOG. Steam Workshop publishing is optional: the local blueprint folder can be shared directly.

## Local blueprint directory

Paste this path into Windows File Explorer:

```text
%USERPROFILE%\AppData\LocalLow\Craneballs\PlanetNomads\UserConstructions
```

Each blueprint has its own numbered directory (the creation timestamp) containing `Blueprint.xml`, `MetaData.xml`, and `thumbnail.png`. Use the thumbnail to recognise the construction without opening its XML files.

## Share a construction

1. Use the Replicator to export the blueprint locally.
2. Open `UserConstructions` and find its numbered folder by looking at `thumbnail.png`.
3. **ZIP the entire numbered folder**, not just its contents.
4. Send the ZIP to another player.
5. The recipient extracts that numbered folder into their own `UserConstructions` directory.
6. Launch Planet Nomads and find the construction in the Replicator.

Example:

```text
UserConstructions\
  1794951413\
    Blueprint.xml
    MetaData.xml
    thumbnail.png
```

Keep the original numbered folder name and files intact. If a folder with the same number already exists, back it up first rather than overwriting it.

## Multiplayer Rover example

![Multiplayer Rover blueprint thumbnail](images/multiplayer-rover-blueprint.jpg)

Our Multiplayer Rover was created and tested on GOG, then published to Steam Workshop using the Steam version's Replicator. Its local exported blueprint includes the **undriven rounded cockpit (block 30004)** as well as the standard driven cockpit.

**Custom multiplayer blocks require the matching multiplayer client mod.** For the Multiplayer Rover, use multiplayer **0.3.30 or newer**. A stock game may not recognise custom blocks. Steam Workshop access is not required to share the local files.

This describes the native local blueprint format. For manual imports, check the blueprint appears in the receiving game's Replicator before relying on it.
