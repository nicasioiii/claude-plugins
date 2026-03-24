# Nic's Claude Code Plugins

Private plugin marketplace for custom Claude Code plugins.

## Setup (One-Time)

### 1. Push this folder to a private GitHub repo

```bash
cd claude-plugins
git init
git add .
git commit -m "Initial marketplace with cfo-finance-mastery v1.2.0"
git remote add origin git@github.com:YOUR_USERNAME/claude-plugins.git
git push -u origin main
```

### 2. Add the marketplace in Claude Code

Open Claude Code desktop, go to Settings > Plugins > Add marketplace, and enter:

```
YOUR_USERNAME/claude-plugins
```

Or via CLI:
```bash
/plugin marketplace add YOUR_USERNAME/claude-plugins
```

### 3. Install the plugin

```bash
/plugin install cfo-finance-mastery@nic-plugins
```

## Updating Plugins

When you update a plugin:

1. Make your changes in `plugins/cfo-finance-mastery/`
2. Bump the version in both:
   - `plugins/cfo-finance-mastery/.claude-plugin/plugin.json`
   - `.claude-plugin/marketplace.json`
3. Push to GitHub
4. In Claude Code, run: `/plugin marketplace update`

## Adding New Plugins

1. Create a new folder in `plugins/your-new-plugin/`
2. Add `.claude-plugin/plugin.json` with name, version, description
3. Add your skills/, commands/, agents/ as needed
4. Add an entry to `.claude-plugin/marketplace.json` in the `plugins` array
5. Push and sync

## Current Plugins

| Plugin | Version | Description |
|--------|---------|-------------|
| cfo-finance-mastery | 1.2.0 | CFO-level financial analysis, modeling, forecasting, dashboards, profit optimization |

## Private Repo Auth

For background auto-updates to work, set your GitHub token:

```bash
export GITHUB_TOKEN=ghp_your_token_here
```

For manual installs/updates, Claude Code uses your existing git credentials (gh auth, SSH keys, etc).
