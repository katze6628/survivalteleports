# SurvivalTeleports

A lightweight Paper plugin for small survival servers with home teleports and TPA functionality.

## Features

- **Home Teleports**: Set up to 3 home locations per player
- **TPA System**: Request to teleport to other players or request them to teleport to you
- **Configurable Delays**: Optional teleport delay with cancellation on movement or damage
- **Data Persistence**: All homes are saved to disk
- **Fully Configurable**: Customizable messages, limits, and delays

## Commands

### Home Commands
- `/sethome [name]` - Set a home location (default name: "home")
- `/home [name]` - Teleport to a home location
- `/delhome <name>` - Delete a home location
- `/homes` - List all your home locations

### TPA Commands
- `/tpa <player>` - Request to teleport to another player
- `/tpahere <player>` - Request another player to teleport to you
- `/tpaccept` - Accept a pending teleport request
- `/tpdeny` - Deny a pending teleport request

## Permissions

All permissions default to `true` for all players:

- `teleports.home.set` - Allow setting homes
- `teleports.home.use` - Allow using homes
- `teleports.home.delete` - Allow deleting homes
- `teleports.home.list` - Allow listing homes
- `teleports.tpa.send` - Allow sending TPA requests
- `teleports.tpa.respond` - Allow responding to TPA requests

## Configuration

Edit `plugins/SurvivalTeleports/config.yml`:

```yaml
# Maximum number of homes each player can set
max-homes: 3

# Teleport delay in seconds (set to 0 for instant)
teleport-delay: 3

# TPA request timeout in seconds
tpa-timeout: 60

# Cancel teleport if player moves during delay
cancel-on-move: true

# Cancel teleport if player takes damage during delay
cancel-on-damage: true
```

All messages are also customizable in the config file.

## Installation

1. Ensure you're running Paper 1.21.3 or newer
2. Build the plugin:
   ```bash
   mvn clean package
   ```
3. Copy `target/teleports-1.0.0.jar` to your server's `plugins/` folder
4. Restart the server
5. Configure the plugin in `plugins/SurvivalTeleports/config.yml`

## Requirements

- Paper 1.21.3+
- Java 21+

## Building

This plugin uses Maven. To build:

```bash
mvn clean package
```

The compiled JAR will be in the `target/` directory.

## Data Storage

Home data is stored in `plugins/SurvivalTeleports/homes.yml` and is automatically saved when homes are created or deleted.

## Perfect for Small Servers

Designed specifically for small survival servers with a few players. Lightweight, simple to use, and no database required!
