# Nic's Claude Plugins

Private plugin marketplace — 9 plugins synthesized from expert courses.

## Plugins

| Plugin | Version | Skills | Commands |
|--------|---------|--------|----------|
| cfo-finance-mastery | 1.2.0 | 7 | 8 |
| cold-outbound-mastery | 2.0.0 | 11 | 14 |
| course-to-plugin | 2.1.0 | 1 | 2 |
| cro-copywriting-mastery | 2.0.0 | 14 | 12 |
| design-mastery | 1.0.0 | 11 | 8 |
| marketing-skills | 1.4.0 | 18 | 0 |
| paid-ads-mastery | 2.0.0 | 16 | 8 |
| sales-negotiation-mastery | 2.0.0 | 12 | 8 |
| seo-mastery | 2.0.0 | 16 | 9 |

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
