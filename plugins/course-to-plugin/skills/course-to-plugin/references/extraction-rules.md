# Extraction Rules — Zero Knowledge Loss Standard

## Core Principle

The goal is ZERO knowledge loss. After this plugin is built, the user should never need to re-watch, re-read, or re-listen to any of the source courses. Every actionable insight must be captured.

## What to Extract

Each sub-agent must extract ALL of the following from every transcript file:

### 1. Strategies, Tactics, and Techniques
- Every method, approach, or technique described
- Include the full context: when to use it, when NOT to use it, prerequisites
- If a technique has conditions (works for business type A but not B, works at scale X but breaks at scale Y), capture those conditions explicitly

### 2. Frameworks and Templates
- Every fill-in-the-blank template
- Every repeatable framework with its steps
- Every script (sales scripts, ad scripts, email scripts, call scripts)
- Capture the EXACT structure, not a summary of it

### 3. Benchmarks, Metrics, and Data Points
- Every specific number mentioned with full context
- Ranges and thresholds (e.g., "CTR below 1% means X", "at $500/day you should Y")
- Industry benchmarks with the conditions under which they apply
- ROI examples, case study results, conversion rates

### 4. Tools, Platforms, and Integrations
- Every tool recommended with specific use cases
- Platform-specific features, settings, and configurations
- Integration setups and technical requirements
- Specific product names, not generic categories

### 5. Mistakes, Pitfalls, and Anti-patterns
- Every "never do this" warning
- Common mistakes with explanations of WHY they're mistakes
- Money/time-wasting patterns to avoid
- Failure modes and their warning signs

### 6. Step-by-Step Processes and SOPs
- Every walkthrough with exact steps
- Configuration sequences with specific settings at each step
- Decision trees with exact criteria at each branch
- Checklists and verification steps

### 7. Campaign/System Structures and Architectures
- Exact structures with naming conventions
- Account organization patterns
- Hierarchies and their relationships
- Budget allocation models

### 8. Examples and Case Studies
- Real campaign breakdowns with results
- Before/after transformations with specific metrics
- Named companies or industries (anonymized if needed but preserving the lesson)
- Failure case studies and what went wrong

### 9. Contrarian and Non-obvious Insights
- Anything that goes against conventional wisdom — FLAG PROMINENTLY
- Counterintuitive findings backed by data or experience
- "Everyone says X but actually Y" moments
- These are often the most valuable insights in the entire extraction

### 10. Platform-Specific Settings and Configurations
- Exact toggles, switches, and their recommended positions
- UI navigation paths (which menu, which setting)
- Platform-specific terminology and what it means in practice
- Version-specific notes (if the instructor mentions a specific platform version)

## Extraction Quality Standards

### BAD extraction (too vague):
- "Target the right audience"
- "Write compelling ad copy"
- "Optimize your campaigns regularly"
- "Set up tracking properly"
- "Test different creatives"

### GOOD extraction (specific and actionable):
- "Create a 1% lookalike from purchasers with 180+ day window for cold prospecting, then layer interest exclusions to remove existing customers"
- "Lead with a specific number or result in the first 3 words of primary text because Meta truncates after 125 characters on mobile feed"
- "Kill an ad set if CPA exceeds 2x target after spending 2x your target CPA — don't wait longer hoping it'll improve"
- "Set up server-side Conversions API first, then browser pixel as backup — server events are 30% more reliable post-iOS 14.5"
- "Test 3 hooks against 1 body. If all 3 hooks fail, the problem is the body/offer, not the hooks"

### The specificity test
For each extracted insight, ask: "Could someone implement this RIGHT NOW without any additional context?" If not, it needs more detail.

## Handling Multiple Sources on Same Topic

When multiple courses cover the same topic:

1. **Consensus**: If experts agree, capture the definitive version once with a note like "confirmed across [Course A], [Course B], and [Course C]"
2. **Complementary**: If experts cover different aspects, merge into a comprehensive version that takes the best from each
3. **Contradictory**: If experts disagree, capture BOTH perspectives with context on when each applies. Format:
   ```
   EXPERT DISAGREEMENT: [Topic]
   - [Expert A] says: [Position + reasoning]
   - [Expert B] says: [Position + reasoning]
   - Context for when to use each approach: [Conditions]
   ```
4. **Data vs. opinion**: If one expert has data and another has opinions, weight the data-backed version but note the alternative

## Extraction Document Format

Each extraction file should be organized by topic clusters, not by source file order. Use this structure:

```markdown
# Extraction: [Course Name]

## Course Overview
- Instructor: [Name]
- Focus: [What this course primarily covers]
- Files processed: [Count]
- Key strengths: [What this course is best at]

## [Topic Cluster 1]

### [Sub-topic]
[Extracted knowledge with full detail]
- Source: [filename.md]

### [Sub-topic]
[More extracted knowledge]
- Source: [filename.md]

## [Topic Cluster 2]
...

## Contrarian/Non-obvious Insights
[Collected from throughout the course, flagged prominently]

## Extraction Notes
- Files that seemed incomplete or corrupted: [list]
- Topics mentioned but not covered in depth: [list]
- Cross-references to other courses needed: [list]
```

## Validation Checklist

After extraction, verify:
- [ ] Every source file was actually opened and read
- [ ] Line count is proportional to source material (see build-process.md for ratios)
- [ ] No major topics were skipped
- [ ] Specific numbers and benchmarks are captured, not genericized
- [ ] Templates and frameworks retain their exact structure
- [ ] Anti-patterns and warnings are captured
- [ ] Contrarian insights are flagged
