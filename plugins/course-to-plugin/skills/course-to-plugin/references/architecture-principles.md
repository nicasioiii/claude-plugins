# Architecture Principles — Designing the Skill Structure

## Core Rule: Content Dictates Architecture

Never design the skill structure before reading the extractions. The knowledge itself determines how many skills you need, what each covers, and where the boundaries fall.

## Organizing by Workflow Stage, Not Source Course

Skills should map to how the user works, not where the knowledge came from.

Example (BAD — organized by course):
```
skills/
├── john-smith-course/          # Course-based = useless
├── jane-doe-masterclass/       # User doesn't care which course it came from
└── advanced-webinar-series/    # This tells the user nothing about WHEN to use it
```

Example (GOOD — organized by workflow):
```
skills/
├── account-setup/              # Step 1: Getting infrastructure in place
├── research-and-strategy/      # Step 2: Planning before execution
├── campaign-creation/          # Step 3: Building the thing
├── creative-production/        # Step 4: Making the assets
├── optimization/               # Step 5: Improving what's running
└── scaling/                    # Step 6: Growing what works
```

## Skill Boundary Rules

### Each skill must be standalone
Someone should be able to activate just one skill and get complete guidance on that topic. Don't create skills that are useless without reading another skill first.

### No fuzzy overlap
If you can't clearly articulate where skill A ends and skill B begins, they should probably be one skill (or the boundary needs to be redrawn).

### The "when does the user ask for this?" test
For each skill, answer: "What would the user actually type to trigger this?" If the answer is vague or overlaps with another skill, the boundaries are wrong.

## Splitting vs. Combining Decisions

### When to split into separate skills:
- The sub-topics have different user intents (setup vs. optimization)
- The sub-topics have fundamentally different mechanics (platform A vs. platform B)
- Combined, the SKILL.md would exceed 500 lines even with references/
- A user would reasonably want one without the other

### When to keep combined:
- The topics are always used together in practice
- Splitting would create skills too small to be useful
- The decision framework for choosing between them is simple enough to put in one skill
- A user asking about topic A almost always also needs topic B

### Platform splits
When the source material covers multiple platforms/tools with fundamentally different mechanics:
- If 80%+ of the knowledge is platform-specific -> separate skills per platform
- If 80%+ of the knowledge is universal -> one skill with platform-specific reference files
- If it's a mix -> one skill with routing: "For [Platform A] specifics, read `references/platform-a.md`"

## Reference File Design

### What goes in SKILL.md vs. references/

**SKILL.md** (always loaded, <500 lines):
- Core decision frameworks and routing logic
- High-level process overviews
- The "when to use what" guidance
- Quick-reference tables and checklists
- Pointers to reference files with clear "read this when..." instructions

**references/** (loaded on demand):
- Deep-dive walkthroughs
- Platform-specific configurations
- Complete templates and scripts
- Detailed case studies
- Extended benchmark tables
- Methodology deep-dives

### Reference file sizing
- Each reference file: 200-600 lines (sweet spot)
- Under 200 lines: probably should be in SKILL.md
- Over 600 lines: consider splitting into two reference files
- Include a brief table of contents if over 300 lines

### Reference file naming
Use descriptive, scannable names:
- GOOD: `google-shopping-strategy.md`, `meta-hook-frameworks.md`, `scaling-playbook.md`
- BAD: `ref1.md`, `details.md`, `advanced.md`

## Slash Command Design

### What makes a good slash command
Commands should map to real workflows the user does repeatedly:
- `/build-campaign` — Interactive campaign builder
- `/audit-campaign` — Diagnostic tool for existing campaigns
- `/write-ad` — Creative generation
- `/research-brief` — Pre-work before creating anything

### Command interaction pattern
Every command should:
1. Ask the user 3-5 scoping questions (platform, business type, goal, constraints)
2. Reference the relevant skill(s) for deep knowledge
3. Produce structured, actionable output (not a wall of text)
4. Include next steps or hand off to another command/skill

### Command count guidelines
- Small plugin (3-5 skills): 3-5 commands
- Medium plugin (6-9 skills): 5-8 commands
- Large plugin (10+ skills): 7-10 commands
- Don't create commands for every possible action — just the most common workflows

## Cross-Reference Design

Skills should reference each other when handoffs are natural:

```markdown
## Cross-References
- After completing account setup, proceed to **strategy** for campaign planning
- Before creating ads, run **/research-brief** to build your creative foundation
- If campaign metrics are declining, see **optimization** for diagnostic frameworks
```

### Trigger Condition Rules

Every cross-reference MUST include a TRIGGER CONDITION — when to hand off, not just that the other skill exists.

**BAD:** "See the optimization skill for more"
**GOOD:** "After launching campaigns, if CPA exceeds 2x target after 3 days -> hand off to optimization skill"

**BAD:** "See relevant skill"
**GOOD:** "When keyword list exceeds 50 terms -> hand off to **content-cluster-strategy** to organize into topic clusters"

Additional rules:
- Every skill that produces output consumed by another skill MUST have a handoff instruction with the specific trigger
- No vague pointers like "see relevant skill" — always name the SPECIFIC skill by its kebab-case folder name
- Include measurable conditions where possible (thresholds, counts, time periods)
- If the trigger is subjective, describe the observable signal: "When the user reports declining ROAS for 7+ days -> hand off to **optimization**"

## CLAUDE.md Routing Table

The plugin's CLAUDE.md should include a clear routing table:

```markdown
| User Intent | Route To | Notes |
|---|---|---|
| "Set up my account" | setup skill | Always start here for new accounts |
| "Plan my campaign" | strategy skill | After setup is complete |
| "Write ad copy" | creative skill | Needs research brief first |
| "My campaign isn't working" | optimization skill | Diagnostic mode |
| "I want to spend more" | scaling skill | Only after optimization |
```

### Ambiguous Request Decision Tree (REQUIRED in every CLAUDE.md)

Without this, Claude guesses wrong when requests could map to multiple skills:

```markdown
## Ambiguous Request Handling

IF request mentions a specific workflow stage -> route to that stage's skill
ELSE IF request mentions a specific sub-topic -> route to the skill owning it
ELSE IF request is broad ("help me with my ads") -> ask a clarifying question:
  "Are you looking to [option A], [option B], or [option C]?"
ELSE -> route to the earliest workflow stage skill

### Execution Priority Order
When multiple skills apply: [list from earliest to latest workflow stage]
```

### Cross-Reference Trigger Conditions (REQUIRED)

Cross-references must include WHEN to hand off, not just WHERE:

BAD: "See the optimization skill for more"
GOOD: "After launching campaigns, if CPA exceeds 2x target after 3 days -> hand off to optimization skill"

## Agent Design (for Claude Code Compatibility)

Every plugin needs BOTH a CLAUDE.md (for Cowork) and an agents/ file (for Claude Code). They contain the same routing logic but in different formats.

### CLAUDE.md (Cowork)
- Declarative routing tables
- Markdown tables mapping intent to skill
- Read passively by Cowork when routing requests

### agents/[name]-advisor.md (Claude Code)
- Imperative instructions written as agent directives
- "Your Role" section with numbered responsibilities
- Routing as "When user says X -> use skill Y"
- Active voice: "Route to...", "Ask the user...", "Load skill..."

### Key Differences
- CLAUDE.md uses tables; agents/ uses bullet lists with example phrases
- CLAUDE.md is reference material; agents/ is an active instruction set
- Both must cover the same intents — if you add a route to one, add it to the other
- CLAUDE.md organizes by workflow stage headers with table rows; agents/ organizes by intent category with nested user phrases and primary/secondary skill assignments
- agents/ includes a "Your Role" preamble that CLAUDE.md does not need (Cowork infers role from context)

### Keeping Them in Sync
When building a plugin:
1. Write CLAUDE.md first (the routing table is the canonical source of truth)
2. Generate agents/ from CLAUDE.md by converting each table row into an intent category with example phrases
3. During quality audit, verify every CLAUDE.md table row has a corresponding agents/ entry and vice versa
