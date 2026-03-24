# Plugin Structure — Technical Format Reference

## Required Files

Every plugin must have these files for full compatibility with both Cowork and Claude Code:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json          # REQUIRED: Plugin metadata
├── CLAUDE.md                # REQUIRED: Routing for Cowork
├── agents/
│   └── [name]-advisor.md    # REQUIRED: Routing for Claude Code
├── settings.json            # REQUIRED: Agent pointer
├── README.md                # RECOMMENDED: Documentation for the user
├── skills/
│   └── skill-name/
│       ├── SKILL.md         # REQUIRED: Skill instructions with YAML frontmatter
│       └── references/      # OPTIONAL: Deep-dive reference files
│           ├── topic-a.md
│           └── topic-b.md
└── commands/
    └── command-name.md      # OPTIONAL: Slash command definitions
```

## plugin.json Format

**CRITICAL: plugin.json must contain ONLY these three fields. No extra metadata.**

Cowork's plugin parser only recognizes `name`, `version`, and `description`. Any additional fields (skills arrays, commands arrays, references maps, tags, categories, knowledge stats, author, license, targetAudience, etc.) will cause the parser to **fail silently** — the plugin installs but shows "This plugin doesn't have any commands, skills, or agents."

```json
{
  "name": "plugin-name-kebab-case",
  "version": "1.0.0",
  "description": "Clear description of what this plugin covers, its scope, and its source material. Be specific enough that someone reading this knows exactly what they're getting."
}
```

- `name`: kebab-case, matches the directory name
- `version`: semver (1.0.0 for initial release)
- `description`: 1-3 sentences covering scope, key capabilities, and source material
- **NO OTHER FIELDS.** Skills and commands are auto-discovered from the filesystem (SKILL.md and command .md frontmatter), NOT from plugin.json.

## SKILL.md Format

```markdown
---
name: Human-Readable Skill Name
description: "Detailed description of what this skill does and when to use it. Include specific trigger phrases and keywords. Be slightly 'pushy' — Claude tends to under-trigger skills, so make the description generous about when to activate. Explicitly state what this skill covers AND what it doesn't cover to prevent mis-routing. MANDATORY TRIGGERS: keyword1, keyword2, keyword3."
---

# Skill Title

[Skill instructions go here]

## When to Read Reference Files

- For [specific sub-topic A], read `references/topic-a.md`
- For [specific sub-topic B], read `references/topic-b.md`
- For [specific sub-topic C], read `references/topic-c.md`

[Core decision frameworks, routing logic, and essential knowledge]

[Keep total SKILL.md under 500 lines]
```

### YAML Frontmatter Rules

**CRITICAL: Every SKILL.md and command .md MUST have valid YAML frontmatter.** Files without `---` delimited frontmatter at the very top will be invisible to Cowork — the plugin will install but those skills/commands will not appear.

- `name`: Required. **Use human-readable names** (e.g., "Creative Research & Strategy", "Link Authority Building"), NOT kebab-case. The folder name is kebab-case, but the `name` field in frontmatter is what the user sees in the UI.
- `description`: Required. This is the PRIMARY trigger mechanism. Claude sees this in the available skills list and decides whether to activate the skill based on it. Make it comprehensive. **MUST include a "MANDATORY TRIGGERS:" line** listing all keywords/phrases that should activate this skill.

**Common failure mode:** Sub-agents building skills sometimes skip frontmatter entirely and start with a `# Header`. The build agent prompt MUST explicitly require frontmatter and the self-audit phase MUST verify every file starts with `---`.

### Description Writing Tips
- Include the skill's domain AND specific keywords that should trigger it
- List concrete user phrases: "Use when the user mentions X, Y, or Z"
- Explicitly exclude adjacent topics: "Do NOT use for [adjacent topic] — use [other skill] instead"
- Include both formal and casual trigger language

Example description (note human-readable name, MANDATORY TRIGGERS, and explicit exclusions):
```
name: Google Ads Account Setup
description: "Complete Google Ads account setup including Merchant Center configuration, product validation criteria, conversion tracking with enhanced conversions, and Google Tag Manager implementation. Use when setting up Google Ads from scratch, auditing setup, or fixing conversion tracking issues. MANDATORY TRIGGERS: Google Ads setup, Merchant Center, product feed, conversion tracking, Google Tag, GTM. Do NOT use for campaign strategy or optimization — use strategy-google-ads and optimize-campaigns skills instead."
```

## Command File Format

```markdown
---
name: Human-Readable Command Name
description: "What this command does in one sentence. Be specific enough to trigger correctly."
---

# /command-name

[Brief description of what this command produces]

## Questions to Ask

Ask the user these questions before generating output:

1. [Question about platform/tool]
2. [Question about business type/context]
3. [Question about goals/constraints]
4. [Question about budget/scale]

## Output Structure

Using the answers above and knowledge from the **[relevant-skill]** skill, produce:

### Section 1: [Title]
[What to include]

### Section 2: [Title]
[What to include]

### Section 3: [Title]
[What to include]

## References

For deep knowledge on [topic], read the **[skill-name]** skill and its reference files:
- `skills/[skill-name]/references/[file].md` for [specific sub-topic]
```

### Command Design Principles
- Commands are interactive — they ASK before they OUTPUT
- Commands reference skills for deep knowledge (commands are workflows, skills are knowledge bases)
- Commands produce structured, formatted output (tables, checklists, templates)
- Commands should work for different business types and scales

## CLAUDE.md Format

```markdown
# [Plugin Name] — Routing & Operations

## Plugin Overview
[2-3 sentences: what this plugin covers, where the knowledge came from, who it's for]

## Skill Routing Logic

Route user requests to the appropriate skill based on workflow stage and question type:

### [STAGE 1 NAME]
| User Intent | Skill | Notes |
|---|---|---|
| [intent description] | **[skill-name]** | [when/why] |

### [STAGE 2 NAME]
| User Intent | Skill | Notes |
|---|---|---|
| [intent description] | **[skill-name]** | [when/why] |

[Continue for all stages]

## Ambiguous Request Decision Tree

When the user's request could map to multiple skills, use this priority:

IF request mentions a specific workflow stage -> route to that stage's skill
ELSE IF request mentions a specific sub-topic -> route to the skill owning that sub-topic
ELSE IF request is broad ("help with [domain]") -> ask a clarifying question:
  "Are you looking to [option A from skill 1], [option B from skill 2], or [option C from skill 3]?"
ELSE -> route to the most foundational skill in the workflow (earliest stage)

### Execution Priority Order
When multiple skills apply simultaneously, load them in workflow order:
[List skills from earliest workflow stage to latest]

## Cross-References Between Skills
[When one skill should hand off to another — specify the TRIGGER condition, not just that the other skill exists]
Example: "After completing keyword research, if the user has 50+ keywords, hand off to **content-cluster-strategy** to organize into clusters"

## Slash Commands
| Command | Purpose |
|---|---|
| `/command-name` | [What it does] |

## Product Marketing Context
Before asking the user questions, check if `.claude/product-marketing-context.md` exists.
If it does, read it first and skip questions you already have answers to.

## Scope Boundaries
**This plugin covers:** [list]
**This plugin does NOT cover:** [list with pointers to other plugins]
**This plugin replaces:** [any functionality in other plugins that is now redundant]
```

## agents/*.md Format (Claude Code Routing)

The `agents/` directory contains agent files that serve the same purpose as CLAUDE.md but for Claude Code instead of Cowork. Every plugin needs both.

### Required YAML Frontmatter

```yaml
---
name: Human-Readable Agent Name
description: Route [domain] questions to the right skill based on user intent, business stage, and decision type. Provide opinionated [domain]-level guidance for [target audience].
---
```

Both `name` and `description` are required. The description should summarize the agent's routing purpose and audience.

### Agent File Structure

The agent file follows this skeleton (see `agents/cfo-advisor.md` for a real example):

1. **YAML frontmatter** with `name` and `description`
2. **Your Role** section — numbered list of 4-5 responsibilities (understand intent, route to skill, ask clarifying questions, execute in priority order, suggest next steps)
3. **Skill Routing Logic** — organized by intent category, each with example user phrases, primary skill, and slash command
4. **Ambiguous Request Decision Tree** — pattern-matching blocks with "Ask:" clarifying questions and routing arrows
5. **Cross-References Between Skills** — handoff rules with trigger conditions

### How agents/ Differs from CLAUDE.md

| Aspect | CLAUDE.md (Cowork) | agents/*.md (Claude Code) |
|---|---|---|
| Voice | Declarative routing tables | Imperative agent directives |
| Routing format | Markdown tables: Intent / Skill / Notes | Bullet lists with example user phrases |
| Purpose | Reference material read passively | Active instruction set executed by agent |
| Phrasing | "Route to skill X" | "When user says Y -> use skill X" |
| Disambiguation | Decision tree in markdown | Pattern-matching with "Ask:" prompts |

**Both must cover the same intents.** If you add a route to CLAUDE.md, add the equivalent to agents/. If you add a pattern to agents/, add the table row to CLAUDE.md.

## settings.json Format

The `settings.json` file at the plugin root tells Claude Code which agent file to load. It contains exactly one field:

```json
{
  "agent": "agent-name"
}
```

- The value matches the filename in `agents/` without the `.md` extension
- Example: if the agent file is `agents/cfo-advisor.md`, settings.json is `{"agent": "cfo-advisor"}`
- No other fields. No version, no metadata, no configuration options.

## Marketplace Integration Format

When adding a plugin to a marketplace.json file, use the validated format below. Claude Code's plugin validator is strict — extra fields cause rejection.

### Root-Level Fields

```json
{
  "name": "marketplace-name",
  "owner": {
    "name": "Owner Name",
    "email": "optional@email.com"
  },
  "metadata": {
    "description": "Optional description of this marketplace"
  },
  "plugins": []
}
```

- `name` (required): Identifier for the marketplace
- `owner` (required): Object with `name` (required) and `email` (optional)
- `metadata` (optional): Object with `description`
- `plugins` (required): Array of plugin entries
- **NO `$schema` at root** — Claude Code validator rejects it
- **NO `version` at root** — validator rejects it

### Plugin Entry Fields

Each entry in the `plugins` array has exactly three fields:

```json
{
  "name": "plugin-name",
  "source": "./plugins/plugin-name",
  "description": "What this plugin does in one sentence."
}
```

- `name`: kebab-case plugin name
- `source`: Relative path from marketplace.json to the plugin directory
- `description`: One-line summary of capabilities
- **NO `version` on entries** — validator rejects it
- **NO other fields** (no tags, no author, no categories)

### Complete Example

```json
{
  "name": "my-plugins",
  "owner": {
    "name": "Your Name"
  },
  "plugins": [
    {
      "name": "seo-mastery",
      "source": "./plugins/seo-mastery",
      "description": "Keyword research, content strategy, technical SEO, link building, and analytics."
    },
    {
      "name": "paid-ads-mastery",
      "source": "./plugins/paid-ads-mastery",
      "description": "Google Ads and Meta Ads: setup, strategy, creative, optimization, scaling."
    }
  ]
}
```

## Packaging as .plugin File

A `.plugin` file is simply a zip archive of the plugin directory:

```bash
cd /path/to/plugin-directory
zip -r /sessions/modest-trusting-thompson/plugin-name.plugin . -x "*.DS_Store" "*.mcpb-cache*"
```

**CRITICAL: Always write the .plugin file to the SESSION working directory** (`/sessions/modest-trusting-thompson/`), NOT to the user's mounted folder. The mounted folder often has I/O permission restrictions that cause `zip` to fail with "zip I/O error: Operation not permitted" after completing all file additions. After zipping to the session directory, COPY the .plugin file to the user's folder:

```bash
cp /sessions/modest-trusting-thompson/plugin-name.plugin "/path/to/user/folder/plugin-name.plugin"
```

Also:
- Create the zip from INSIDE the plugin directory (so paths start with `.claude-plugin/`, `skills/`, etc.)
- Exclude OS junk files (`.DS_Store`, etc.) and any build artifacts (`*BUILD_SUMMARY*`, `*CREATION_SUMMARY*`)
- The resulting `.plugin` file can be presented to the user via `present_files` for one-click installation

## Quality Checklist Before Packaging

### Structural (installation will break if these fail)
- [ ] plugin.json contains ONLY `name`, `version`, `description` — no extra fields
- [ ] Every SKILL.md file starts with `---` on line 1 (YAML frontmatter delimiter)
- [ ] Every SKILL.md has both `name:` and `description:` in frontmatter
- [ ] Every command .md file starts with `---` on line 1
- [ ] Every command .md has both `name:` and `description:` in frontmatter
- [ ] `name:` values are human-readable (e.g., "Link Authority Building"), NOT kebab-case
- [ ] CLAUDE.md exists at plugin root
- [ ] agents/ directory exists with [name]-advisor.md
- [ ] Agent file has valid YAML frontmatter with `name` and `description`
- [ ] settings.json exists with correct agent name matching agents/ filename

### Content quality
- [ ] Every skill's SKILL.md is under 500 lines
- [ ] Every referenced file in SKILL.md actually exists in references/
- [ ] Every description includes "MANDATORY TRIGGERS:" with keyword list
- [ ] Every description includes exclusions ("Do NOT use for...")
- [ ] Commands reference the correct skill names
- [ ] No broken cross-references between skills
- [ ] CLAUDE.md has an ambiguous-request decision tree
- [ ] CLAUDE.md has execution priority order for multi-skill requests
- [ ] README.md documents all skills and commands
- [ ] Total plugin content is substantial (10K+ lines for a comprehensive plugin)
- [ ] Reference files >= 300 lines each

### Content completeness
- [ ] Cross-reference extraction topics against reference file topics — no major gaps
- [ ] Cutting-edge / conference / forward-looking insights captured (not just fundamentals)
- [ ] Specialized / niche content captured (not just mainstream topics)
- [ ] CLAUDE.md and agents/ cover the same intents (no routing gaps between them)
