---
name: Build Plugin
description: "Build a new plugin from course transcripts. Runs the full 7-phase pipeline: scoping, recon, extraction, architecture, build, recursive audit, marketplace integration."
---

# /build-plugin

Build a new plugin from a folder of course transcripts (MD files). This runs the full autonomous pipeline.

## Questions to Ask

Use the AskUserQuestion tool to gather:

1. **Source folder**: Where are the course transcript files? (full path to folder)
2. **Topic/discipline**: What subject do these courses cover? (e.g., "paid advertising — Google Ads and Meta Ads")
3. **Plugin name**: What should the plugin be called? (kebab-case, e.g., `paid-ads-mastery`)
4. **Workflow scope**: What's the full workflow this plugin should cover? (e.g., "from account setup through optimization and scaling")
5. **Out-of-scope topics**: What should this plugin NOT cover? (Adjacent topics handled by other plugins)

If the user's message already answers some of these, skip those questions.

## Execution

After gathering answers, activate the **course-to-plugin** skill in NEW mode and execute all phases:

1. **Phase 0**: Scoping (already done via questions above)
2. **Phase 1**: Reconnaissance — scan the folder, map all files
3. **Phase 2**: Extraction — spawn sub-agents to extract all knowledge
4. **Phase 3**: Architecture — design the skill structure
5. **Phase 4**: Plugin Build — create all skills, commands, references, CLAUDE.md, agents/
6. **Phase 5**: Plugin Audit — check for overlap with existing plugins
7. **Phase 6**: Recursive Deep Audit — up to 10 cycles until clean
8. **Phase 7**: Packaging — create .plugin zip
9. **Phase 7.5**: Marketplace Integration — copy to marketplace repo, update marketplace.json, ask to push

## Output

- Built plugin folder in the marketplace repo
- `.plugin` zip file for direct Cowork install
- Extraction summary, gap analysis, and README
