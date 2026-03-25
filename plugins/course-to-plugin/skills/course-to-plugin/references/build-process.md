# Build Process — Detailed Phase Instructions

## Overview

This document contains the detailed step-by-step instructions for each phase of the course-to-plugin build process. The SKILL.md provides the high-level flow; this file provides the operational detail.

Supports two modes:
- **Create mode** — Building a new plugin from course material
- **Update mode** — Adding new course material to an existing plugin

## Directory Structure

All work happens in the user's selected folder. Create these subdirectories as needed:

```
user-folder/
├── _recon.md                    # Phase 1 output
├── _extraction/                 # Phase 2 outputs (one file per course batch)
│   ├── extract_01_coursename.md
│   ├── extract_02_coursename.md
│   └── ...
├── _architecture.md             # Phase 3 output
├── _plugin_audit.md             # Phase 5 output (if applicable)
├── _extraction_summary.md       # Phase 7 deliverable
├── _gap_analysis.md             # Phase 7 deliverable
├── _comparison_report.md        # Phase 1 deliverable (if updating)
├── plugin/                      # The actual plugin
│   ├── .claude-plugin/
│   │   └── plugin.json
│   ├── CLAUDE.md
│   ├── settings.json
│   ├── agents/
│   │   └── [plugin-name]-advisor.md
│   ├── skills/
│   │   ├── skill-name/
│   │   │   ├── SKILL.md
│   │   │   └── references/
│   │   │       ├── ref-file-1.md
│   │   │       └── ref-file-2.md
│   │   └── ...
│   └── commands/
│       ├── command-name.md
│       └── ...
└── [plugin-name].plugin         # Final packaged file
```

---

## Phase 0: Mode Selection

### Create Mode
Ask the user:
1. Where is the course material? (folder path)
2. What should the plugin be called?
3. Any scope constraints? (what to include/exclude)

### Update Mode
1. List plugins in the marketplace repo: `ls /Users/Nic/Documents/GitHub/claude-plugins/plugins/`
2. Ask which plugin to update
3. Ask what new courses/material to add
4. Read the existing plugin's CLAUDE.md, skills, and references to understand current scope

---

## Phase 1: Reconnaissance — Detailed Steps

### Step 1: Full directory scan
```
find [user-folder] -name "*.md" -type f | head -50
```
Get a complete picture of what's in the folder. Count files per subfolder.

### Step 2: Sample reading
Read 15-20 files spread across different course folders to understand:
- Depth of content (surface-level summaries vs. detailed transcriptions)
- Topics covered and their overlap
- Whether files are individual lessons, chapters, or bulk dumps
- Quality and completeness of transcriptions

### Step 3: Recon report
Write `_recon.md` with:
- Total file count and per-course breakdown
- Topic ratio breakdown (what percentage covers which sub-topics)
- Preliminary skill category suggestions
- Proposed extraction batch plan (which courses to group, how many agents)
- Any concerns about file quality or completeness

### Step 4: User confirmation
Present the recon findings. Wait for the user to confirm before proceeding to extraction.

### Phase 1 (Update Mode)
- Recon scans BOTH the new course folder AND the existing plugin
- Produce a comparison report (`_comparison_report.md`): what's already covered vs what's new
- Identify gaps in existing plugin that new material fills
- Identify entirely new topics the existing plugin doesn't touch

---

## Phase 2: Extraction — Detailed Steps

### Sub-agent spawning strategy

| Course size | Agent strategy |
|---|---|
| <30 files | 1 agent for the whole course |
| 30-100 files | 1 agent, but instruct it to be thorough |
| 100-200 files | Split into 2 agents (by module/section) |
| 200+ files | Split into 3+ agents |

### Sub-agent prompt template

Each extraction agent should receive a prompt like:

```
You are extracting actionable knowledge from course transcripts. Your job is COMPREHENSIVE EXTRACTION — not summarization.

Course: [COURSE NAME]
Files to process: [LIST ALL FILES WITH PATHS]
Topic area: [TOPIC]

Read every single file listed above and extract:
[See references/extraction-rules.md for the full extraction checklist]

Save your complete extraction to: [OUTPUT PATH]

CRITICAL: This extraction becomes the foundation for a permanent knowledge plugin.
If you skip something, it's lost forever. When in doubt, include it.
Every specific number, every exact configuration, every step-by-step process — capture it all.
```

### Post-extraction validation

After all agents complete, check:
1. Every source file was actually read (agents sometimes skip files)
2. Line counts are proportional to source material volume
3. No entire topics were missed

Expected extraction ratios:
- Very detailed course (video transcripts with walkthroughs): 30-60 lines extracted per source file
- Moderate course (lecture-style): 15-30 lines per source file
- Light course (overview/theory-heavy): 10-20 lines per source file

If an extraction batch comes in significantly below these ratios, investigate and re-run.

### Phase 2 (Update Mode)
- Extract ONLY from new course material (don't re-extract existing content)
- Tag each extraction file clearly as NEW material

---

## Phase 3: Architecture — Detailed Steps

### Architecture agent prompt template

```
You are designing the skill architecture for a Cowork plugin. Read all extraction files below and design the optimal plugin structure.

Extraction files: [LIST ALL EXTRACTION FILE PATHS]
Plugin name: [NAME]
Plugin scope: [DESCRIPTION OF WHAT IT COVERS]
Out of scope: [WHAT IT DOESN'T COVER]

Your job:
1. Read every extraction file completely
2. Identify natural knowledge clusters and workflow stages
3. Design skills that are organized by WORKFLOW STAGE, not by source course
4. Each skill must be standalone — usable without other skills
5. Each SKILL.md must stay under 500 lines — use references/ for deep content
6. Design slash commands for the most common user workflows

Output an architecture document with:
- Number of skills and their names
- What each skill covers (bullet list of topics)
- What goes in SKILL.md vs references/ for each skill
- Proposed slash commands with brief descriptions
- Cross-references between skills (when one should hand off to another)
- Reasoning for your decisions
```

### Architecture review principles

Before building, verify the architecture against these criteria:
- No skill has fuzzy boundaries with another — clear delineation
- Every major topic from the extractions has a home
- Workflow stages flow logically (setup -> plan -> create -> execute -> optimize)
- Commands map to real user workflows, not abstract processes
- Reference files are scoped tightly — one topic per file

### Phase 3 (Update Mode)
- Architecture agent reads existing plugin + new extractions
- Decides: expand existing skills, add new skills, add new reference files, or combination
- Produces a **change plan** (not a full architecture from scratch)
- Change plan format: list of ADD / MODIFY / EXPAND actions with rationale

---

## Phase 4: Plugin Build — Detailed Steps

### Parallel build strategy

Split skills across 2-4 build agents. Each agent also builds any commands that naturally pair with its skills.

### Build agent prompt template

```
You are building skills for a Cowork plugin. Create the following skills with full SKILL.md files and reference files.

Skills to build: [LIST WITH DESCRIPTIONS]
Commands to build: [LIST WITH DESCRIPTIONS]
Source extraction files to reference: [LIST PATHS — agent should read these]
Architecture doc: [PATH — agent should read this for context]

Plugin name: [NAME]
Output directory: [PATH]/plugin/

CRITICAL FRONTMATTER REQUIREMENT — EVERY FILE MUST START WITH YAML FRONTMATTER:

For each skill, the SKILL.md file MUST begin with exactly this format (no exceptions):
---
name: Human-Readable Skill Name Here
description: "Detailed description. MANDATORY TRIGGERS: keyword1, keyword2, keyword3. Do NOT use for [excluded topics] — use [other-skill] instead."
---

For each command, the .md file MUST begin with exactly this format (no exceptions):
---
name: Human-Readable Command Name Here
description: "What this command does in one sentence."
---

FAILURE MODE TO AVOID: Do NOT start any SKILL.md or command .md with a markdown header (#). The very first line must be --- (the YAML frontmatter opening delimiter). Files without frontmatter will be INVISIBLE to the plugin system — Cowork will not detect them as skills or commands.

NAME FORMAT: Use human-readable names like "Link Authority Building" or "Content Plan", NOT kebab-case like "link-authority-building" or "content-plan". The folder name is kebab-case, but the frontmatter name is human-readable.

For each skill:
1. Create skills/[skill-name]/SKILL.md — MUST start with YAML frontmatter
2. Create skills/[skill-name]/references/ with deep-dive reference files
3. SKILL.md must be under 500 lines — put detailed content in references/
4. Include a "When to read references" section telling Claude which reference to load for which sub-topic

For each command:
1. Create commands/[command-name].md — MUST start with YAML frontmatter
2. Commands should be interactive — ask the user questions, then produce structured output
3. Commands should reference the relevant skills for deep knowledge

Quality standards:
- Opinionated: State best practices as rules, not suggestions
- Practical: Include actual templates, checklists, decision trees with specific thresholds
- Specific: Real numbers, exact configurations, named tools and settings
- Synthesized: Merge the best elements from multiple sources. Note when experts disagree.
```

### CLAUDE.md template

Every plugin needs a CLAUDE.md at the root with:

```markdown
# [Plugin Name] — Routing & Operations

## Plugin Overview
[1-2 paragraph description of what this plugin covers]

## Skill Routing Logic
[Table mapping user intents to skills, organized by workflow stage]

## Ambiguous Request Decision Tree

When the user's request could map to multiple skills:

IF request mentions a specific workflow stage -> route to that stage's skill
ELSE IF request mentions a specific sub-topic -> route to the skill owning that sub-topic
ELSE IF request is broad ("help with [domain]") -> ask a clarifying question:
  "Are you looking to [option A], [option B], or [option C]?"
ELSE -> route to the earliest workflow stage skill

### Execution Priority Order
When multiple skills apply: [list from earliest to latest workflow stage]

## Cross-References
[When one skill should hand off to another — include the TRIGGER CONDITION]
Example: "After keyword research produces 50+ keywords -> hand off to content-cluster-strategy"

## Product Marketing Context
Before asking the user questions, check if `.claude/product-marketing-context.md` exists.
If it does, read it first and use that context to skip questions you already have answers to.

## Scope Boundaries
This plugin covers: [IN SCOPE]
This plugin does NOT cover: [OUT OF SCOPE — with pointers to other plugins if applicable]
```

### Agent File Template (for Claude Code compatibility)

Create `agents/[plugin-name]-advisor.md` with this structure:

```markdown
---
name: [Plugin Name] Advisor
description: Route [domain] questions to the right skill based on user intent. Provide opinionated guidance for [target audience].
---

# [Plugin Name] Advisor Agent

## Your Role
You are a [domain] advisor. Your job is to:
1. Understand what decision the user is trying to make
2. Route them to the right skill based on their intent
3. Ask clarifying questions when the request is ambiguous
4. Execute in priority order: [workflow stages]
5. Suggest next steps after each interaction

## Skill Routing Logic
[Map user intent phrases to skill + command for each skill]

Example format:
**[Intent Category]**
- "user phrase 1" / "user phrase 2"
  - **Primary:** skill-name
  - **Command:** `/command-name`

## Ambiguous Request Decision Tree
[Same decision tree as CLAUDE.md but written as imperative instructions]

Example format:
### Pattern: "ambiguous user phrase"
**Ask:** "Clarifying question?"
- **Option A focus:** -> `/relevant-command`
- **Option B focus:** -> `/other-command`

### Pattern: "multi-step request"
**Routing:** Always [step 1] first, then [step 2]
1. First: `/command-a` (reason)
2. Then: `/command-b` (reason)

## Cross-References
[When to hand off between skills — with TRIGGER CONDITIONS]

Format:
### skill-name
- References: other-skill (when/why), another-skill (when/why)
- Trigger: "What user says that activates this skill"
```

Also create `settings.json` at plugin root:
```json
{"agent": "[plugin-name]-advisor"}
```

### plugin.json format

**CRITICAL: Only these three fields. No extras.**

```json
{
  "name": "plugin-name",
  "version": "1.0.0",
  "description": "Complete description of what this plugin covers and its source material."
}
```

Do NOT add `skills`, `commands`, `tags`, `categories`, `references`, `knowledge`, `author`, `license`, or any other keys. Extra fields cause silent plugin detection failures.

### Phase 4 (Update Mode)
- Build ONLY changed/new files
- Preserve all unchanged files
- Update CLAUDE.md routing if new skills were added
- Update `agents/` if routing changed
- Update `settings.json` only if agent file was renamed

---

## Phase 5: Plugin Audit — Detailed Steps

### Finding installed plugins

Check these locations:
- `/sessions/*/mnt/.local-plugins/` — user-installed plugins
- Browse the available skills list from the system prompt for skill names and descriptions
- The user's selected folder may contain previous plugin builds

### Audit categories

| Overlap Type | Action |
|---|---|
| Full overlap (entire skill is redundant) | Remove skill folder, remove associated commands, update CLAUDE.md |
| Partial overlap (some content overlaps) | Add cross-reference note to top of skill, keep non-overlapping content |
| Tangential (shares keywords but different focus) | No changes needed, just document in audit report |

### Modified plugin packaging

For each modified plugin:
1. Copy the entire plugin to a writable location
2. Make edits (remove skills, add cross-references, update CLAUDE.md)
3. Bump the version number in plugin.json (e.g., 1.1.0 -> 1.2.0)
4. Update the description if skills were removed
5. Package as `.plugin` file: `cd [plugin-dir] && zip -r [output-path]/[name].plugin . -x "*.DS_Store"`

### Phase 5 (Update Mode)
- SKIP overlap audit (we're updating an existing plugin, not creating a new one that might conflict)

---

## Phase 6: Recursive Deep Audit (MANDATORY — up to 10 cycles)

### Audit Loop Logic

```
cycle = 1
previous_issue_count = infinity
while cycle <= 10:
    spawn audit agent with FULL checklist below
    collect report
    issue_count = count of FAIL items

    if issue_count == 0:
        log "AUDIT PASSED — clean on cycle {cycle}"
        break

    fix all issues found
    log "Cycle {cycle}: {issue_count} issues found and fixed"

    if cycle > 2 and issue_count < previous_issue_count * 0.3:
        log "Diminishing returns detected — {issue_count} vs {previous_issue_count} previous"
        # Continue anyway to verify fixes

    previous_issue_count = issue_count
    cycle += 1

if cycle > 10:
    log "WARNING: Still finding issues after 10 cycles. Manual review recommended."
```

### Audit Agent Prompt Template

```
You are auditing a plugin for correctness before packaging. The plugin is at: [PLUGIN PATH]
The extraction files are at: [EXTRACTION PATH]
This is audit cycle {N} of up to 10. Previous cycle found {X} issues.

Run ALL checks below. Report PASS/FAIL for each with specific file paths and issues.

CONTENT ACCURACY CHECKS:
1. Cross-reference extraction files against reference files — verify specific numbers, benchmarks, and formulas match the source material
2. Check for inverted or wrong formulas (e.g., marketing efficiency ratio with swapped numerator/denominator)
3. Check for circular frontmatter logic — descriptions that say "Do NOT use for X" where X is exactly what the skill does
4. Verify specific numbers from extractions made it into the plugin (not genericized from "14.7%" to "typically 10-20%")
5. Verify linking formulas between skills that share concepts (e.g., retained earnings bridge between diagnostics and modeling)
6. Check date validation steps for any data-processing skills
7. Verify formulas reference correct variables (not swapped numerator/denominator)

STRUCTURAL QUALITY CHECKS:
8. plugin.json contains ONLY name, version, description (no extra fields)
9. Every SKILL.md starts with --- on line 1 (YAML frontmatter)
10. Every SKILL.md has name: with HUMAN-READABLE value (not kebab-case)
11. Every SKILL.md has description: with MANDATORY TRIGGERS keyword list
12. Every command .md starts with --- and has name: and description:
13. CLAUDE.md exists with ambiguous-request decision tree
14. agents/ directory exists with properly formatted agent file
15. settings.json exists with correct agent name reference
16. Reference files are >= 300 lines each (we had 8 files under minimum in CFO build)
17. CLAUDE.md routing covers >= 10 common user intents
18. Every skill description includes a WHO (who is this for / what learner type)
19. No vague routing placeholders ("see relevant skill" — must name the SPECIFIC skill)

CROSS-REFERENCE CHECKS:
20. Every cross-reference includes a TRIGGER CONDITION (not just a pointer)
21. Every skill that produces output consumed by another skill has a handoff instruction
22. Commands reference real, existing skill names (not typos or old names)
23. All file references in SKILL.md "When to read references" sections point to real files

README CHECKS:
24a. README.md exists at plugin root
24b. README lists the CORRECT number of skills (count actual skill directories, not what was planned)
24c. README lists the CORRECT number of commands (count actual command files)
24d. README version matches plugin.json version
24e. README includes source material list, workflow description, and audit status
24f. If this is a rebuild/update: README includes "What's New" section

CONTENT COMPLETENESS CHECKS (read extraction files side-by-side with built plugin):
24. TOPIC CLUSTER COVERAGE: For each extraction file, verify every major topic cluster (## heading) has representation in at least one skill or reference file. List any extraction topics that were dropped or have no home.
25. FRAMEWORK/FORMULA SURVIVAL: Extract all named frameworks, formulas, and methodologies from extraction files (e.g., "PMS Formula", "Rule of One", "Bell Theory"). Verify each appears in the built plugin with full tactical detail — not just mentioned by name but actually explained with steps/components.
26. BENCHMARK/DATA POINT SURVIVAL: Extract all specific numbers, percentages, dollar amounts, and benchmarks from extraction files. Verify each appears somewhere in the plugin. Flag any that were genericized (e.g., "47%" became "about 50%") or dropped entirely.
27. CONTRARIAN INSIGHT SURVIVAL: All insights tagged [CONTRARIAN] or [NON-OBVIOUS] in extraction files must appear in the built plugin. These are the highest-value differentiators — losing them defeats the purpose of the plugin.
28. TACTICAL DEPTH RATIO: For each major topic, compare the extraction content depth to the reference file depth. If the extraction has 50+ lines on a topic but the reference file has <15 lines on that same topic, the content was over-summarized. Flag topics where >50% of tactical detail was lost in translation.
29. TEMPLATE/CHECKLIST COMPLETENESS: All step-by-step templates, checklists, decision trees, and fill-in-the-blank frameworks from extractions must be in reference files with full structure intact — not condensed into a single sentence in the SKILL.md.
30. CROSS-INSTRUCTOR SYNTHESIS: Where multiple instructors covered the same topic, verify the plugin synthesizes their perspectives (not just picks one). Where instructors disagree, verify the disagreement is documented with both positions and when each applies.

MARKETPLACE INTEGRATION CHECK:
31. MARKETPLACE.JSON REGISTRATION: Verify the plugin is listed in `/Users/Nic/Documents/GitHub/claude-plugins/.claude-plugin/marketplace.json` with correct name, source path, and description. If the plugin is NOT in marketplace.json, this is a CRITICAL FAIL — the plugin will be invisible in Claude Code/Cowork even if all files are correct. Also verify the root README.md (`/Users/Nic/Documents/GitHub/claude-plugins/README.md`) has a row for this plugin with correct version, skill count, and command count.

OUTPUT: Structured report with:
- PASS/FAIL for each numbered check (1-31)
- For each FAIL: file path, specific issue, recommended fix
- Content completeness score: X/7 completeness checks passed
- List of specific extraction content that didn't make it into the plugin
- Issue count summary (structural vs content completeness breakdown)
- Overall verdict: CLEAN / NEEDS FIXES
```

### Handling Audit Fixes

After each cycle, fix in this priority order:

**Priority 1 — Structural failures (checks 8-19):**
1. Fix missing frontmatter, bad plugin.json, broken file references
2. Fix thin reference files — expand with more detail from extractions
3. Fix missing CLAUDE.md routing entries, WHO clauses, TRIGGERS

**Priority 2 — Content accuracy failures (checks 1-7):**
4. Fix wrong/inverted formulas
5. Fix genericized numbers (restore exact values from extractions)
6. Fix terminology inconsistencies across skills

**Priority 3 — Content completeness failures (checks 24-30):**
7. For dropped topic clusters (check 24): add content to the appropriate skill's reference files, sourced from the extraction files
8. For lost frameworks/formulas (check 25): add the full framework with all steps/components to the relevant reference file
9. For dropped benchmarks (check 26): add the specific numbers to the relevant reference file or skill
10. For lost contrarian insights (check 27): add them to the relevant skill or reference file with [CONTRARIAN] tag
11. For over-summarized topics (check 28): expand the reference file with the tactical detail from the extraction
12. For incomplete templates (check 29): add the full template structure to the reference file
13. For missing synthesis (check 30): add the second instructor's perspective with a "When experts disagree" section

**Priority 0 — Marketplace integration (check 31):**
0. If plugin is missing from marketplace.json, add it IMMEDIATELY — this is why plugins become invisible in Claude Code/Cowork
0b. If root README.md is missing the plugin row, add it with actual filesystem counts

**Then:** Re-run the FULL audit (all 31 checks, not just the failed ones)

### Phase 6 (Update Mode)
- Full recursive audit of the ENTIRE updated plugin (not just new files)
- Verify new content integrates cleanly with existing content
- Check that existing cross-references still point to valid targets after changes

---

## Phase 7: Final Packaging

### Deliverable Outputs

1. **Plugin `.plugin` file** — For Cowork direct install
   - All audit checks must PASS before packaging
   - Package to session dir first (avoids I/O permission errors on mounted folders):
     ```bash
     cd [plugin-dir] && zip -r /sessions/[session-name]/[name].plugin . -x "*.DS_Store" "*BUILD_SUMMARY*" "*CREATION_SUMMARY*"
     ```
   - Then copy to user's folder:
     ```bash
     cp /sessions/[session-name]/[name].plugin "[user-folder]/[name].plugin"
     ```
   - Present via `present_files` for install button

2. **Marketplace folder** — Handled by Phase 7.5
   - Plugin folder copied to marketplace repo
   - marketplace.json updated
   - Ready for git push

3. **Modified plugin `.plugin` files** — For any plugins that were edited in Phase 5
   - Version bumped
   - Changelog included
   - Same packaging approach (zip to session dir, then copy)

4. **Extraction summary** — `_extraction_summary.md`
   - What was extracted from each course
   - Line counts per extraction batch
   - Any files that couldn't be processed

5. **Gap analysis** — `_gap_analysis.md`
   - Topics that were thin in the source material
   - Areas where additional courses would strengthen the plugin
   - Any content that didn't fit cleanly into the skill structure

6. **README.md** — Inside the plugin at `plugin/README.md` (MANDATORY — must be created or updated on EVERY build/rebuild)

   The README is the public-facing documentation. It MUST accurately reflect the current state of the plugin. Generate it from the actual built files, not from memory.

   **Required sections:**
   ```markdown
   # [Plugin Name] v[version]

   [1-2 paragraph description of what this plugin covers and who it's for]

   ## Source Material
   - [List every course/source with instructor name]
   - Total: [X] courses, [Y] files, [Z] lines of source material

   ## Skills ([count])

   | Skill | Description | Reference Files |
   |-------|-------------|-----------------|
   | [skill-name] | [human-readable name] — [1-line description] | [count] |
   [... one row per skill ...]

   ## Commands ([count])

   | Command | Description |
   |---------|-------------|
   | `/[command]` | [What it does] |
   [... one row per command ...]

   ## Workflow
   [Describe the layer/stage organization: Setup → Research → Strategy → Create → Test → Optimize → Scale, or whatever the plugin's workflow is]

   ## What's New in v[version]
   [If this is a rebuild: list new skills, expanded skills, removed/merged skills, key improvements vs previous version]

   ## Audit Status
   - Structural audit (checks 1-23): PASS
   - Content completeness audit (checks 24-30): PASS
   - Total audit cycles: [N]
   ```

   **CRITICAL:** The README must be regenerated from the ACTUAL built plugin files — count the real skills, list the real commands, use the real version number. Do NOT copy-paste from a previous version or from the architecture doc (which may have changed during build).

### Presenting to user

Use `present_files` tool to present `.plugin` files — this gives the user a clickable install button in the chat. Always present the main plugin first, then any modified plugins.

### Phase 7 (Update Mode)
- Bump version in plugin.json:
  - **Patch** (1.0.0 -> 1.0.1) for content additions to existing skills
  - **Minor** (1.0.0 -> 1.1.0) for new skills added
- **REGENERATE README.md** — Do NOT skip this. The README must reflect the current plugin state:
  - Update skill count and table
  - Update command count and table
  - Update source material list if new courses were added
  - Add "What's New in v[version]" section documenting changes
  - Update audit status
- Update marketplace.json entry description if scope changed

---

## Phase 7.5: Marketplace Integration

**CRITICAL: This phase is NOT optional. A plugin that passes all 30 audit checks but is not in marketplace.json will be INVISIBLE to users. This is the #1 cause of "my plugin doesn't show up" issues.**

The marketplace repo is always at `/Users/Nic/Documents/GitHub/claude-plugins/`.

### Steps:

1. Copy the entire built plugin folder to `plugins/[plugin-name]/` in the marketplace repo:
   ```bash
   cp -r [build-dir]/plugin/ /Users/Nic/Documents/GitHub/claude-plugins/plugins/[plugin-name]/
   ```

2. Read the existing marketplace.json:
   ```bash
   cat /Users/Nic/Documents/GitHub/claude-plugins/.claude-plugin/marketplace.json
   ```

3. Update marketplace.json:
   - If the plugin already exists in the `plugins` array: update its `description`
   - If it's new: append to the `plugins` array:
     ```json
     {
       "name": "[plugin-name]",
       "source": "./plugins/[plugin-name]",
       "description": "[1-2 sentence description]"
     }
     ```
   - **CRITICAL FORMAT RULES** (from validated testing):
     - Root level: `name`, `owner` (required), `metadata` with `description` (optional)
     - NO `$schema` at root — the validator rejects it
     - NO `version` at root — the validator rejects it
     - NO `version` on plugin entries — not needed (version lives in plugin.json)

4. Validate:
   ```bash
   cd /Users/Nic/Documents/GitHub/claude-plugins && npx @anthropic-ai/claude-code plugin validate .
   ```

5. **Update the root repo README.md** (`/Users/Nic/Documents/GitHub/claude-plugins/README.md`):
   - This README contains a summary table of ALL plugins with version, skill count, and command count
   - After every plugin build/rebuild/update, regenerate the table row for the affected plugin with ACTUAL counts from the filesystem:
     ```bash
     # Get actual counts for a plugin:
     version=$(python3 -c "import json; print(json.load(open('plugins/[name]/.claude-plugin/plugin.json'))['version'])")
     skills=$(ls -d plugins/[name]/skills/*/ | wc -l)
     commands=$(ls plugins/[name]/commands/*.md | wc -l)
     ```
   - Also update the total plugin count in the description line if a new plugin was added
   - **Do NOT skip this** — stale root README data is visible on GitHub and misleads users

6. **PRE-COMMIT VERIFICATION GATE** — Before committing, run these 3 checks. Do NOT commit until all 3 pass:
   ```bash
   # Check 1: Plugin exists in marketplace.json
   grep -q '"[plugin-name]"' /Users/Nic/Documents/GitHub/claude-plugins/.claude-plugin/marketplace.json && echo "PASS: In marketplace.json" || echo "FAIL: NOT in marketplace.json — add it now!"

   # Check 2: Plugin has a row in root README.md
   grep -q '[plugin-name]' /Users/Nic/Documents/GitHub/claude-plugins/README.md && echo "PASS: In root README" || echo "FAIL: NOT in root README — add row now!"

   # Check 3: Plugin count in README matches actual plugin count
   actual=$(ls -d /Users/Nic/Documents/GitHub/claude-plugins/plugins/*/ | wc -l | tr -d ' ')
   echo "Actual plugin count: $actual — verify README header matches"
   ```
   If any check fails, fix it before proceeding.

7. Ask the user: "Want me to commit and push to the marketplace repo?"
   - If yes: `git add . && git commit -m 'Add/update [plugin-name] v[version]' && git push`
   - If no: leave changes staged for manual review

