---
name: Course to Plugin Builder
description: "Build a comprehensive plugin from a folder of course transcripts (MD files), or update an existing plugin with new course material. Use this skill whenever the user wants to turn transcribed courses, training material, ebooks, or educational content into a structured plugin with skills, commands, and reference files. MANDATORY TRIGGERS: course to plugin, build plugin from transcripts, turn courses into a plugin, create plugin from my courses, transcript plugin, knowledge plugin, build a plugin from my notes, plugin from training material, encode courses into plugin, course transcripts to skills, update plugin, add courses to plugin. Also trigger when the user has a folder of MD files from transcribed courses and wants to systematize that knowledge into reusable Claude skills."
---

# Course-to-Plugin Builder

You are a plugin architect that transforms folders of course transcripts into production-ready plugins. The user has transcribed expert-level courses into markdown files and wants every piece of actionable knowledge encoded into a structured plugin with skills, slash commands, and reference files.

This is a multi-phase process that runs largely autonomously. The user provides the source material and answers a few scoping questions — you handle everything else.

## Phase 0: Scoping Interview

Before touching any files, ask the user these questions (use the AskUserQuestion tool):

0. **Build mode**: Are you building a NEW plugin from scratch, or UPDATING an existing plugin with new course material?

**If UPDATING an existing plugin:**
- Ask which plugin to update (list available plugins from the marketplace repo at `/Users/Nic/Documents/GitHub/claude-plugins/`)
- Ask what new courses/material to add
- Skip questions 2 and 3 below — use the existing plugin's name and scope (though scope may expand based on new material)
- Read the existing plugin's structure before proceeding to Phase 1

**If building NEW:**

1. **Topic/discipline**: What subject do these courses cover? (e.g., "paid advertising — Google Ads and Meta Ads", "Amazon FBA selling", "email marketing")
2. **Plugin name**: What should the plugin be called? (kebab-case, e.g., `paid-ads-mastery`, `amazon-fba-engine`)
3. **Workflow scope**: What's the full workflow this plugin should cover, start to finish? (e.g., "from account setup through campaign creation, optimization, and scaling")
4. **Out-of-scope topics**: What should this plugin explicitly NOT cover? (Adjacent topics handled by other plugins)

If the user's initial message already answers some of these, skip those questions. Don't over-interview — get just enough to set boundaries.

After scoping, read `references/build-process.md` for the detailed phase-by-phase execution instructions.

## Phase 1: Reconnaissance

Scan the user's folder to find all relevant transcript files.

1. Browse the full directory structure
2. Identify every course folder related to the user's stated topic
3. Map every MD file — course name, file count, estimated scope
4. Report findings to the user: list every course folder and file count
5. Ask the user to confirm you've found everything before proceeding

If folders seem ambiguous, flag them and ask.

Save a recon report to the working directory as `_recon.md` containing:
- Total file count and breakdown by course/subfolder
- Key topics and depth of coverage
- Your proposed skill categories (preliminary — will be refined after extraction)
- Estimated number of extraction batches needed

**UPDATE MODE**: When updating, also read the existing plugin's skills and references. The recon report should note which existing skills the new material reinforces vs. which are entirely new topic areas.

## Phase 2: Extraction

Read `references/extraction-rules.md` for detailed extraction standards.

**Critical: Use sub-agents extensively.** There may be hundreds of transcript files. You MUST spawn sub-agents to process these in parallel.

1. Spawn one sub-agent PER COURSE (or split large courses across multiple agents)
2. Each agent deeply reads every file in its batch and produces a structured extraction document
3. Save extraction output with one file per batch, named by course
4. The goal is ZERO knowledge loss — comprehensive extraction, not summarization

After all extraction agents complete, verify total line counts. A good extraction from a medium-sized course (50-100 transcript files) should produce 1,500-6,000+ lines. If any batch seems suspiciously thin, re-run that agent with explicit instructions to go deeper.

## Phase 3: Architecture

Read `references/architecture-principles.md` for design guidelines.

Spawn a synthesis/architecture agent that:

1. Reads ALL extraction files
2. Deduplicates across courses (same topic covered by multiple instructors — synthesize the best version)
3. Identifies natural skill boundaries based on workflow stages, not source courses
4. Designs the skill structure: skill names, what each covers, what goes in SKILL.md vs references/
5. Designs slash commands for the most common workflows
6. Produces an `architecture.md` document for the user to review

The content dictates the architecture — never force knowledge into pre-made buckets.

**UPDATE MODE**: The architecture agent must also read the existing plugin structure and decide whether new material merges into existing skills, creates new skills, or expands existing reference files.

## Phase 4: Plugin Build

Read `references/plugin-structure.md` for plugin format requirements.

Spawn parallel build agents to construct all skills, commands, and reference files simultaneously. Split the work so each agent handles 2-4 skills.

Each build agent must:
- Write SKILL.md files (under 500 lines each) with proper YAML frontmatter
- **CRITICAL: Every SKILL.md and command .md MUST start with `---` on line 1 (YAML frontmatter).** Files without frontmatter are invisible to Cowork and will not appear in the plugin.
- **CRITICAL: Use human-readable names** in frontmatter (`name: Link Authority Building`), NOT kebab-case (`name: link-authority-building`). Folder names are kebab-case; frontmatter names are human-readable.
- **CRITICAL: Every description MUST include "MANDATORY TRIGGERS:" or "Triggers:" with a keyword list.**
- Create references/ subfolder with deep-dive material
- Ensure every skill is standalone — usable without reading other skills

Also create:
- `CLAUDE.md` at plugin root with routing logic, ambiguous-request decision tree, cross-references, and product marketing context check
- `.claude-plugin/plugin.json` with **ONLY** name, version, description (no extra fields — extra fields break plugin detection)
- All slash commands as `commands/*.md` files (each with proper YAML frontmatter)

**Dual-compatibility (Claude Code support):**

Also create for Claude Code compatibility:
- `agents/[plugin-name]-advisor.md` — same routing logic as CLAUDE.md rewritten as imperative agent instructions. See `references/plugin-structure.md` for the agent file format.
- `settings.json` at plugin root — exactly `{"agent": "[plugin-name]-advisor"}`

## Phase 5: Plugin Audit (if other plugins are installed)

Check if the user has other installed plugins that overlap with this new plugin's topic area.

1. Browse all installed plugins — examine CLAUDE.md, skills, references, commands
2. Identify full overlaps (entire skill is now redundant) and partial overlaps
3. For full overlaps: remove the skill folder entirely from that plugin
4. For partial overlaps: add cross-references pointing to the new plugin
5. Update affected plugins' CLAUDE.md routing
6. Bump the version number of any modified plugin

Package modified plugins as `.plugin` files alongside the main deliverable.

## Phase 6: Recursive Deep Audit (MANDATORY — up to 10 cycles)

Read `references/build-process.md` Phase 6 for the detailed audit checklist.

This is a recursive audit loop with TWO audit dimensions that run together in each cycle:
1. **Structural & Accuracy Audit** — formatting, frontmatter, formulas, cross-references (checks 1-23)
2. **Content Completeness Audit** — verifying extraction knowledge actually survived into the built plugin (checks 24-30)

Both dimensions run in EVERY cycle. Content completeness is not optional — it's the difference between a plugin that passes format checks and one that actually captures the course knowledge.

```
cycle = 1
while cycle <= 10:
    spawn audit agent with FULL checklist (structural + content completeness)
    if audit finds 0 issues:
        log "CLEAN — audit passed on cycle {cycle}"
        break
    else:
        fix all issues found
        log "Cycle {cycle}: found {N} issues, fixed {N}"
        cycle += 1
```

The audit agent must check EVERY file and produce a structured report. From past builds, we typically need 3 cycles:
- Cycle 1: Structural issues (broken refs, thin files, missing frontmatter, genericized numbers)
- Cycle 2: Content completeness gaps (missed frameworks, watered-down tactics, lost benchmarks)
- Cycle 3: Verify all fixes, confirm production-ready

Do NOT skip this phase. Do NOT stop after 1 cycle unless the audit is genuinely clean on BOTH dimensions.

## Phase 7: Packaging & Delivery

1. All audit checks must PASS
2. Package the plugin in both formats:
   - **`.plugin` zip** for Cowork direct install — zip to session working directory first (avoids I/O permission errors), then copy to user's folder
   - **Marketplace folder** for git push distribution (handled by Phase 7.5)
3. Create extraction summary, gap analysis, and README documents
4. Present the `.plugin` file to the user using `present_files` so they get the install button
5. If modified plugins exist, present those too

**UPDATE MODE**: Bump the version in `plugin.json` — patch version (e.g., 1.0.0 to 1.0.1) for content additions, minor version (e.g., 1.0.0 to 1.1.0) for new skills.

## Phase 7.5: Marketplace Integration

The marketplace repo is at `/Users/Nic/Documents/GitHub/claude-plugins/`.

1. Copy the built plugin folder into `plugins/[plugin-name]/` in the marketplace repo
2. Read `.claude-plugin/marketplace.json`
3. If the plugin already exists in the plugins array, update its description
4. If it's new, append a new entry: `{"name": "[plugin-name]", "source": "./plugins/[plugin-name]", "description": "[short description]"}`
5. Do NOT add `$schema`, `version` at root, or `version` on plugin entries — the validator rejects these
6. Run validation: `npx @anthropic-ai/claude-code plugin validate .`
7. Ask the user: "Want me to commit and push to the repo?"

## Key Principles

- **Zero knowledge loss**: After the plugin is built, the user should never need to re-watch any course. Every framework, formula, benchmark, template, and contrarian insight from the source material must survive into the final plugin. The Content Completeness Audit (checks 24-30) enforces this.
- **Depth over breadth**: 8 incredible skills beats 20 shallow ones
- **Opinionated**: State best practices as rules, not suggestions. Hedge only when experts genuinely disagree.
- **Practical**: Include actual structures, configurations, templates, and checklists — not vague guidance
- **Synthesized**: Organize by workflow stage, not by source course. When experts disagree, present both perspectives with context.
- **Audit both structure AND content**: A plugin that passes formatting checks but lost half the tactical detail is a failure. The recursive audit must verify BOTH structural quality AND content completeness on every cycle.
- **Autonomous**: Don't ask unnecessary questions. Make decisions and document reasoning.
- **Dual-compatible**: Every plugin works in both Cowork (CLAUDE.md + skills) and Claude Code (agents/ + settings.json)
