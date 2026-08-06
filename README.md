# WinesLab Claude Code Marketplace

Official Claude Code plugin marketplace for the [WinesLab / Open6G lab](https://github.com/wineslab) at Northeastern University.

## Available Plugins

| Plugin | Description | Repo |
|--------|-------------|------|
| `genesis` | Stage agents, domain specialists and skills for the AI-RAN life-cycle: OAI gNB, Foxconn RUs, Sierra/soft UEs, OpenShift, RIC xApps, across Arena/X5G and LCHEM | [wineslab/genesis](https://github.com/wineslab/genesis) |

## Install

### 1. Add the marketplace (once per machine)

```
/plugin marketplace add wineslab/plugin_marketplace
```

### 2. Install a plugin

```
/plugin install genesis@wineslab
```

Skills are then available as `/genesis:<skill>` and agents appear under `genesis:` in `/agents`.

> `wineslab/genesis` is a **private** repository — installing requires access to it,
> and Claude Code clones with your own git credentials.

### CLI alternative

```bash
claude plugin marketplace add wineslab/plugin_marketplace
claude plugin install genesis@wineslab
```

## Update

To pull the latest plugin versions:

```
/plugin marketplace update wineslab
```

## Adding a New Plugin

1. Build the plugin in its own repo following the [Claude Code plugin docs](https://code.claude.com/docs/en/plugins).
   Add `.claude-plugin/plugin.json` and check it with `claude plugin validate .`
2. Open a PR to this repo adding an entry to `.claude-plugin/marketplace.json`:

```json
{
  "name": "your-plugin-name",
  "source": {
    "source": "github",
    "repo": "wineslab/your-repo"
  },
  "description": "What your plugin does",
  "author": { "name": "Your Name", "email": "you@northeastern.edu" }
}
```

3. Merge the PR — teammates can immediately `/plugin marketplace update wineslab` and install it.
