# Nic's Claude Plugins

Private plugin marketplace — 8 plugins synthesized from expert courses.

## Plugins

| Plugin | Version | Skills | Commands |
|--------|---------|--------|----------|
| cfo-finance-mastery | 1.2.0 | 7 | 8 |
| cold-outbound-mastery | 1.1.0 | 7 | 8 |
| cro-copywriting-mastery | 1.0.0 | 11 | 8 |
| design-mastery | 1.0.0 | 11 | 8 |
| marketing-skills | 1.4.0 | 18 | 0 |
| paid-ads-mastery | 1.0.0 | 10 | 7 |
| sales-negotiation-mastery | 1.0.0 | 7 | 7 |
| seo-mastery | 1.0.0 | 9 | 7 |

## Setup

### Claude Code Desktop
1. Settings > Plugins > Add marketplace
2. Enter: `YOUR_USERNAME/claude-plugins`
3. Install plugins: `/plugin install plugin-name@nic-plugins`

### Cowork
Upload individual .plugin files, or sync from this repo.

## Updating Plugins

1. Edit files locally
2. Bump version in both `plugins/PLUGIN_NAME/.claude-plugin/plugin.json` AND `.claude-plugin/marketplace.json`
3. Commit and push
4. In Claude Code: `/plugin marketplace update`
