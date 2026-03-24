---
name: Update Plugin
description: "Update an existing plugin with new course material. Reads the current plugin, extracts new knowledge, merges into existing structure, runs recursive audit."
---

# /update-plugin

Update an existing plugin in the marketplace with new course material.

## Questions to Ask

Use the AskUserQuestion tool to gather:

1. **Which plugin to update**: Show the list of plugins in the marketplace repo (`ls /Users/Nic/Documents/GitHub/claude-plugins/plugins/`) and ask which one
2. **New course folder**: Where are the new course transcript files? (full path)
3. **What's new**: Brief description of what the new courses cover
4. **Scope changes**: Should the plugin's scope expand, or is this just deepening existing coverage?

## Execution

After gathering answers, activate the **course-to-plugin** skill in UPDATE mode:

1. **Phase 0**: Scoping — read existing plugin's CLAUDE.md, skills, and references
2. **Phase 1**: Reconnaissance — scan new course folder AND existing plugin, produce comparison report
3. **Phase 2**: Extraction — extract only from new course material
4. **Phase 3**: Architecture — merge new extractions into existing structure (may add new skills or expand references)
5. **Phase 4**: Build — create/update only changed files, preserve unchanged
6. **Phase 5**: Skip (no overlap audit needed for updates)
7. **Phase 6**: Recursive Deep Audit — full audit of the ENTIRE updated plugin (up to 10 cycles)
8. **Phase 7**: Packaging — bump version (patch for content, minor for new skills), create .plugin zip
9. **Phase 7.5**: Marketplace Integration — update plugin in marketplace repo, update marketplace.json, ask to push

## Output

- Updated plugin folder in the marketplace repo
- Updated `.plugin` zip file
- Version bumped in plugin.json
- Change log documenting what was added/modified
