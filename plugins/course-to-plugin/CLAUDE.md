# Course-to-Plugin Builder — Routing & Operations

## Plugin Overview

This plugin transforms folders of course transcripts (MD files) into production-ready plugins with skills, slash commands, and reference files. It supports both building new plugins from scratch and updating existing plugins with new course material. Every plugin it builds is dual-compatible (Cowork + Claude Code) and marketplace-ready.

Built from 8+ successful plugin builds across CFO finance, SEO, paid ads, copywriting, design, marketing, sales, and cold outbound domains.

## Skill Routing Logic

| User Intent | Skill | Command | Notes |
|---|---|---|---|
| "Build a plugin from my courses" | course-to-plugin | /build-plugin | New plugin from scratch |
| "Turn my transcripts into a plugin" | course-to-plugin | /build-plugin | New plugin from scratch |
| "I have new courses to add" | course-to-plugin | /update-plugin | Update existing plugin |
| "Update my SEO plugin with new material" | course-to-plugin | /update-plugin | Update existing plugin |
| "Add courses to my plugin" | course-to-plugin | /update-plugin | Update existing plugin |
| "Create plugin from my notes" | course-to-plugin | /build-plugin | New plugin from scratch |
| "Encode my training material" | course-to-plugin | /build-plugin | New plugin from scratch |
| "Build a knowledge plugin" | course-to-plugin | /build-plugin | New plugin from scratch |
| "I want to systematize my courses" | course-to-plugin | /build-plugin | New plugin from scratch |
| "Upgrade my existing plugin" | course-to-plugin | /update-plugin | Update existing plugin |

## Ambiguous Request Decision Tree

```
IF user mentions "new" or "from scratch" or "build" → /build-plugin (new mode)
ELSE IF user mentions "update" or "add to" or "new courses for" → /update-plugin (update mode)
ELSE IF user mentions a specific existing plugin name → /update-plugin
ELSE → Ask: "Are you building a new plugin from scratch, or updating an existing one with new material?"
```

## Scope Boundaries

**This plugin covers:** Transforming course transcripts, training material, ebooks, or educational content into structured plugins with skills, commands, and reference files.

**This plugin does NOT cover:**
- Transcribing video/audio to text (use the `transcribe` skill for that first)
- General plugin development or debugging (use the `plugin-dev` plugin from the official marketplace)
- Creating plugins from non-educational content (code repos, documentation, etc.)

## Product Marketing Context

Before asking the user questions, check if `.claude/product-marketing-context.md` exists. If it does, read it first and skip questions you already have answers to.
