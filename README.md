# SkyGenesis Plugin

(Marked for badges COming Soon)

SkyGenesis is a highly customizable and performance-optimized Minecraft OneBlock plugin designed to offer an immersive SkyBlock experience with dynamic gameplay, island management, team features, and robust admin tools.

---

## Gameplay Features

### OneBlock Core
- **Regenerating OneBlock:** Break a unique block that regenerates with each break, providing continuous gameplay.
- **Dynamic Phases:** Progress through unlimited phases where block types dynamically change using weighted randomization.
- **Block Counter:** Tracks block breaks to trigger phase progression and milestones.
- **Visual Effects:** Optional particles, sounds, and holograms enhance block breaking feedback.
- **Lucky Blocks:** Encounter rare blocks that trigger random rewards, mobs, or buffs.
- **Environmental Effects:** Special blocks can temporarily alter biome or weather conditions.
- **Chest Loot:** Phase-specific configurable loot chests to reward players.
- **Milestones:** Achieve block break goals to unlock rewards and achievements.

### Phase Progression System
- Fully customizable phases defined via YAML files, including blocks, mobs, chest contents, lore, rewards, and commands.
- Players progress naturally by breaking blocks, with the option to revisit phases via a phase selector (admin controlled).
- Challenges add task-based gameplay, such as timed block-breaking quests.
- Leaderboards track player and team progress.
- Dynamic server-wide events (e.g., Double Drops, Mob Rush) create engaging gameplay moments.

### Island System
- Personal floating islands in a void world, customizable by biome and border settings.
- Fast teleportation with `/sg home`.
- Upgrades unlock island expansions, regeneration, and cosmetics.
- Apply thematic visual styles such as Nether or End biomes.
- Islands gain levels based on block values and phase progression.
- Environment presets allow customization of biome and weather themes.

### Team & Co-op Features
- Robust team management with roles like Owner, Co-Owner, Member, Visitor, Co-op, and Trusted.
- Manage teams with `/sg invite`, `/sg promote`, `/sg demote`, `/sg kick`, `/sg leave`, `/sg transfer`, `/sg coop`, and `/sg trust`.
- Shared progression options for teams.
- Team chat functionality via `/sg teamchat`.
- Visitors can leave messages on island guestbooks.
- Team-based competitions encourage friendly rivalry.

### Island Settings & Permissions (GUI)
- Configure island-specific toggles such as PvP, mob spawning, grief protection, visitor access, and block interaction.
- Control time and weather on islands.
- Manage granular island permissions with role-based access control.
- Grant temporary access through co-op permissions.
- Fully configurable presets for easy setup.

### Menus & Player Feedback
- Intuitive GUIs for phases, islands, stats, and upgrades.
- Visual progress bars, holograms, and scoreboards display key information.
- Unlock achievements through milestones.
- Activity logs track significant player and island events.
- Custom crafting recipes exclusive to OneBlock gameplay.

## Commands

**For Players**:
In this list is a total list of commands for players, what they do and the permissions

| Command             | Description                            | Permission          |
|---------------------|----------------------------------------|---------------------|
| `/sg`               | Base command for all player commands   |                     |
| `/sg home`          | Teleport to your island home           | `sg.home`           |
| `/sg invite`        | Invite a player to your island/team    | `sg.invite`         |
| `/sg promote`       | Promote a member's role                | `sg.promote`        |
| `/sg demote`        | Demote a member's role                 | `sg.demote`         |
| `/sg kick`          | Kick a player from your island/team    | `sg.kick`           |
| `/sg leave`         | Leave your current island/team         | `sg.leave`          |
| `/sg transfer`      | Transfer island ownership              | `sg.transfer`       |
| `/sg coop`          | Manage coop members                    | `sg.coop`           |
| `/sg trust`         | Trust a player with island access      | `sg.trust`          |
| `/sg settings`      | Change island/team settings            | `sg.settings`       |
| `/sg permissions`   | Manage island/team permissions         | `sg.permissions`    |
| `/sg phase`         | Opens a GUI to show current phase info | `sg.phase`          |
| `/sg teamchat`      | Use team chat                          | `sg.teamchat`       |
| `/sg stats`         | View island or player stats            | `sg.stats`          |
| `/sg upgrades`      | Manage island upgrades                 | `sg.upgrades`       |
| `/sg guestbook`     | View or write in island guestbook      | `sg.guestbook`      |
| `/sg milestones`    | View or manage island milestones       | `sg.milestones`     |
| `/sg events`        | Manage island or team events           | `sg.events`         |
| `/sg leaderboard`   | View island or player leaderboard      | `sg.leaderboard`    |
| `/sg disband`       | Disband your island/team               | `sg.disband`        |
| `/sg create`        | Create your island                     | `sg.create`         | 
| `/sg panel`         | Open the panel GUI                     | `sg.panel`          |
| `/sg top`           | View top islands                       | `sg.island.top`     |
| `/sg close`         | Close your island to the public        | `sg.island.close`   |
| `/sg open`          | Open your island to the public         | `sg.island.open`    | 


**Administration**:

| Command                      | Description                           | Permission               |
|----------------------------- |---------------------------------------|--------------------------| 
| `/sga`                       | Base command for all admin commands   |                          |
| `/sga phase list`            | List all phases                       | `sga.phase.list`         |
| `/sga phase test`            | Test a specific phase                 | `sga.phase.test`         |
| `/sga setchest`              | Set the island's chest location       | `sga.setchest`           |
| `/sga setcount`              | Set count values (e.g., player count) | `sga.setcount`           |
| `/sga island reset`          | Reset an island                       | `sga.island.reset`       |
| `/sga island teleport`       | Teleport to an island                 | `sga.island.teleport`    |
| `/sga island cleanup`        | Cleanup island chunks or data         | `sga.island.cleanup`     |
| `/sga island stats`          | View island statistics                | `sga.island.stats`       |
| `/sga island lock`           | Lock an island to prevent access      | `sga.island.lock`        |
| `/sga island restore`        | Restore island from backup            | `sga.island.restore`     |
| `/sga island simulate`       | Simulate island state or events       | `sga.island.simulate`    |
| `/sga reload`                | Reload plugin configuration files     | `sga.reload`             |
| `/sga ban`                   | Ban a player from the server          | `sga.ban`                |
| `/sga event start`           | Start an event                        | `sga.event.start`        |
| `/sga event stop`            | Stop an event                         | `sga.event.stop`         |
| `/sga competition start`     | Start a competition                   | `sga.competition.start`  |
| `/sga competition stop`      | Stop a competition                    | `sga.competition.stop`   |

---

## Plugin Architecture & Admin Features

### Phase Editor
- Easy-to-edit YAML phase files stored in `/phases/`.
- Powerful admin commands for creating, deleting, editing, listing, and testing phases.
- Hot reload capability with `/sga reload` for seamless configuration updates.

### Island Management
- Asynchronous island generation using custom templates for minimal server lag.
- Comprehensive admin commands for island reset, teleport, cleanup, statistics, locking, restoration, and simulation.
- Progress simulation tools allow admins to test and preview island phases and progression.

### Configuration & Modularity
- Separate YAML configuration files for ease of management: `config.yml`, `island-settings.yml`, `permissions.yml`, `lang.yml`, `phases/*.yml`, `events.yml`, `upgrades.yml`, `milestones.yml`, `competitions.yml`, `recipes.yml`, and `environments.yml`.
- GUI settings are fully configurable through `config.yml`.
- Modular design facilitates maintenance and extensibility.

### Performance & Data Synchronization
- Asynchronous file handling, world generation, and backup operations to maximize server performance.
- Supports multiple database backends: YAML (default), MySQL, and SQLite.
- Public API enables plugin extensions and third-party integrations.
- Cross-server data synchronization via MySQL or Redis to support networked environments.

### Anti-Grief & Security
- Comprehensive action logging for rollback and auditing purposes.
- Admin tools include island locking and player banning to prevent abuse.
- Exploit detection safeguards the server against griefing and other malicious activity.

---

## Integrations

- **PlaceholderAPI:** Utilize dynamic placeholders for displaying statistics and other info.
- **Vault:** Seamless integration with popular economy plugins.
- **WorldEdit:** Supports custom schematic imports for island templates.
- **Discord Integration:** Webhook support and `/sg discord` command for enhanced community interaction.
- **ProtocolLib:** Advanced packet manipulation enables custom entity behavior, animations, and effects without modifying server core.
- **Compatibility:** Fully compatible with Spigot, Paper, Purpur, Folia across Minecraft versions 1.20 through 1.21+.

### Credits
-    Creator: [djtmk1](https://github.com/djtmk1)
-    Contributors: [OceanTw](https://github.com/OceanTw) , [Lrxh](https://github.com/Devlrxxh)
