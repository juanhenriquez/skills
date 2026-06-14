# AGENTS.md

This file provides guidance to coding agents (Claude Code, etc.) when working with code in this repository.

> **Source of truth:** This file (`AGENTS.md`) is canonical. `CLAUDE.md` is a symlink to it. Edit `AGENTS.md` only — never edit `CLAUDE.md` directly or replace the symlink with a copy.

## Purpose

This is a personal repository for **authoring and curating reusable agent skills**. Skills written here are meant to be reused across other projects (copied or symlinked into a project's or user's `.claude/skills/` directory, or otherwise distributed).

The work in this repo is *writing skills*, not building an application. There is no build step, server, or test runner — a "change" is a new or revised skill.

## Layout

Skills live in `skills/`, grouped one level deep by category:

```
skills/<category>/<skill-name>/SKILL.md
```

- **Category** is a broad domain folder: `engineering`, `productivity`, `personal`, etc. Add new categories as needed; keep them broad rather than proliferating narrow ones.
- **`<skill-name>`** is the skill's own directory, named in kebab-case, matching the `name` in its frontmatter.
- Each skill is self-contained in its directory, including any scripts, templates, or reference files it needs.

## Skill format

Every skill is a directory containing a `SKILL.md` with YAML frontmatter followed by Markdown instructions:

```markdown
---
name: skill-name
description: One or two sentences stating WHAT the skill does and WHEN to use it, written so an agent can decide whether to invoke it. Start with the capability, then "Use when…".
---

# Skill Title

Instructions the agent follows when the skill is invoked.
```

Conventions:

- **`name`** must be kebab-case and match the skill's directory name.
- **`description`** is the only thing an agent sees when deciding whether to invoke a skill — it must clearly express the trigger conditions ("Use when the user wants to…"). This is the highest-leverage part of a skill; write it for recall, not for marketing.
- Supporting files (scripts, templates, examples) go inside the skill's directory and are referenced by relative path from `SKILL.md`. Keep `SKILL.md` focused; push long reference material into separate files the agent reads on demand.
- Write instructions as direct, imperative guidance to the agent. Prefer concrete steps and decision rules over prose.

## Authoring a new skill

1. Pick or create the right category folder under `skills/`.
2. Create `skills/<category>/<skill-name>/SKILL.md` with the frontmatter above.
3. Make the skill portable — assume it runs in an unrelated project, so avoid hardcoded paths or assumptions specific to this repo.
4. Test by exercising the trigger conditions described in the `description`.
