### 📖 Introduction

BackTp is a lightweight Minecraft server plugin that allows players to teleport back to their previous locations at a specified time. Whether you've wandered into dangerous areas, fallen into lava, or simply want to quickly return to a previous location, BackTp makes it easy to solve these problems.

### ✨ Key Features

- **Time Travel Teleportation**: Teleport to locations from X seconds ago
- **Smart Location Recording**: Only records positions when players move sufficient distance, saving server resources
- **Multi-language Support**: Supports both Chinese and English interfaces
- **Permission Management**: Flexible permission control system
- **Memory Optimization**: Automatically cleans expired data to prevent memory leaks

### 🚀 Quick Start

#### Installation Steps

1. Download the BackTp.jar file
2. Place the file in your server's `plugins` folder
3. Restart or reload your server
4. The plugin will automatically generate configuration files

#### Basic Usage

```
/backtp 30    # Go back to position from 30 seconds ago
/btp 60       # Go back to position from 60 seconds ago (using alias)
/backtp       # Go back to position from 30 seconds ago (default)
```

### 📋 Command Reference

| Command             | Description                             | Example          | Permission     |
| ------------------- | --------------------------------------- | ---------------- | -------------- |
| `/backtp [seconds]` | Teleport to position from X seconds ago | `/backtp 60`     | `backtp.use`   |
| `/backtp info`      | View your location record statistics    | `/backtp info`   | `backtp.use`   |
| `/backtp reload`    | Reload plugin configuration             | `/backtp reload` | `backtp.admin` |

#### Aliases

- `/btp` - Short alias for `/backtp`

### 🔐 Permission System

| Permission Node | Description                            | Default        |
| --------------- | -------------------------------------- | -------------- |
| `backtp.use`    | Allows using the teleport back feature | All players    |
| `backtp.admin`  | Allows reloading plugin configuration  | Operators only |

### ⚙️ Configuration Files

#### config.yml

```yaml
# Maximum backtracking time (seconds)
max-back-time: 600

# Default language (en/zh)
language: en

# Record interval in seconds
record-interval: 1.0

# Minimum movement distance to record new position (blocks)
min-move-distance: 0.5
```

#### Configuration Explanation

- `max-back-time`: Maximum time players can go back, requests beyond this will be rejected
- `language`: Plugin interface language, supports `en` (English) and `zh` (Chinese)
- `record-interval`: How often to record player positions (recommended 1.0 second)
- `min-move-distance`: How far players need to move before recording a new position, prevents frequent recording

### 💡 Usage Tips

1. **Set Reasonable Backtrack Time**: Don't set excessively long backtrack times as this consumes more memory
2. **Emergency Situations**: Quickly type `/btp` in dangerous situations to use default backtrack time
3. **Check Records**: Use `/btp info` to see how many location records you have
4. **Permission Setup**: You can assign different permissions to different player groups

### 🔧 Troubleshooting

**Q: Why does it show "No location records found for the specified time"?** A: This might be because:

- You haven't been online long enough
- The specified time exceeds the maximum backtrack time
- You didn't move during the specified time period

**Q: Will this plugin affect server performance?** A: No, the plugin is optimized:

- Only records when players move sufficient distance
- Automatically cleans expired data
- Clears data when players go offline

**Q: Can I go back to locations in other dimensions?** A: Yes, the plugin records complete location data including dimension information

### 📊 Version Information

- **Current Version**: 1.3
- **Minecraft Version**: 1.21+
