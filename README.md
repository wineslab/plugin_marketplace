# WinesLab Claude Code Marketplace

Official Claude Code plugin marketplace for the [WinesLab / Open6G lab](https://github.com/wineslab) at Northeastern University.

## Available Plugins

| Plugin | Description | Repo |
|--------|-------------|------|
| `genesis-testrunner` | Agents and skills for GENESIS 5G testbed automation (Arena/X5G, LCHEM) | [wineslab/genesis_testbed](https://github.com/wineslab/genesis_testbed/tree/plugin) |

## Install

### 1. Add the marketplace (once per machine)

```
/plugin marketplace add wineslab/plugin_marketplace
```

### 2. Install a plugin

```
/plugin install genesis-testrunner@wineslab
```

Skills are then available as `/genesis-testrunner:<skill>` and agents appear under `genesis-testrunner:` in `/agents`.

### CLI alternative

```bash
claude plugin marketplace add wineslab/plugin_marketplace
claude plugin install genesis-testrunner@wineslab
```

## Update

To pull the latest plugin versions:

```
/plugin marketplace update wineslab
```

## Adding a New Plugin

1. Build the plugin in its own repo following the [Claude Code plugin docs](https://code.claude.com/docs/en/plugins)
2. Open a PR to this repo adding an entry to `.claude-plugin/marketplace.json`:

```json
{
  "name": "your-plugin-name",
  "source": {
    "source": "github",
    "repo": "wineslab/your-repo",
    "ref": "plugin"
  },
  "description": "What your plugin does",
  "version": "1.0.0",
  "author": { "name": "Your Name", "email": "you@northeastern.edu" }
}
```

3. Merge the PR — teammates can immediately `/plugin marketplace update wineslab` and install it.
