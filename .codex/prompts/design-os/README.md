# Design OS prompts for Codex CLI

This folder mirrors the Claude Code command prompts in `.claude/commands/design-os/` so Codex users have a stable place to find the same Design OS workflows.

Codex CLI may not expose these files as slash commands automatically in every environment. If a slash command is not available, paste one of the prompts below into Codex from the repository root.

## Compatibility note

These prompts are additive. They do not change the existing Claude Code commands in `.claude/commands/design-os/`, and Claude users can continue using the original slash-command workflow.

## Quick start prompts

### Product vision

```text
Read `agents.md` and `.claude/commands/design-os/product-vision.md`, then follow that workflow for my product idea. Ask me the required clarifying questions one step at a time, then create the product overview, roadmap, and data shape files.
```

### Design tokens

```text
Read `agents.md` and `.claude/commands/design-os/design-tokens.md`, then follow that workflow to define my product color and typography tokens.
```

### Design shell

```text
Read `agents.md` and `.claude/commands/design-os/design-shell.md`, then follow that workflow to design the application shell.
```

### Shape a section

```text
Read `agents.md` and `.claude/commands/design-os/shape-section.md`, then follow that workflow for the next product section.
```

### Sample data

```text
Read `agents.md` and `.claude/commands/design-os/sample-data.md`, then follow that workflow to generate sample data and TypeScript types for the selected section.
```

### Design screen

```text
Read `agents.md`, `.claude/commands/design-os/design-screen.md`, and `.claude/skills/frontend-design/SKILL.md`, then follow that workflow to create the selected screen design.
```

### Screenshot design

```text
Read `agents.md` and `.claude/commands/design-os/screenshot-design.md`, then adapt the screenshot workflow for the browser or Playwright tools available in this Codex session.
```

### Export product

```text
Read `agents.md` and `.claude/commands/design-os/export-product.md`, then follow that workflow to generate the `product-plan/` handoff package.
```
