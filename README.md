# skills

A personal collection of reusable [agent skills](https://docs.anthropic.com/en/docs/claude-code/skills) for Claude Code and other coding agents — written here, then reused across other projects.

## Layout

Skills live in `skills/`, grouped one level deep by category:

```
skills/<category>/<skill-name>/SKILL.md
```

Categories are broad domains (`engineering`, `productivity`, `personal`, …). Each skill is a self-contained directory whose `SKILL.md` has YAML frontmatter (`name`, `description`) followed by instructions for the agent.

## Using a skill in another project

Copy or symlink a skill's directory into the target project's (or your user-level) `.claude/skills/` directory.

## Available skills

| Skill | Category | Description |
| --- | --- | --- |
| [simplify](skills/engineering/simplify/SKILL.md) | engineering | Simplify and refine recently modified code for clarity and consistency without changing functionality. |

## Authoring

See [AGENTS.md](AGENTS.md) for conventions on writing new skills. `CLAUDE.md` is a symlink to `AGENTS.md`, which is the source of truth.
