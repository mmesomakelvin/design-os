# Using Design OS with Codex CLI

Design OS was originally packaged around Claude Code slash commands. The underlying workflow is agent-friendly markdown plus repository files, so Codex CLI can follow the same process, but the `.claude/commands/design-os/` files are not guaranteed to appear as Codex slash commands automatically.

This guide shows the safe Codex CLI workflow without changing your product files until you intentionally run a Design OS prompt.

## Claude Code compatibility

These Codex files do not replace or modify the Claude Code workflow. The existing `.claude/commands/design-os/` slash commands and `.claude/skills/frontend-design/SKILL.md` remain in place, and Claude Code users can continue to start the project with `claude` and run the original Design OS slash commands.

The Codex prompt shortcuts intentionally reference the Claude command files instead of duplicating their full contents, so there is still one source of truth for the Design OS command behavior.

## 1. Start from a clean branch

Before asking Codex to generate product files, check your git state:

```bash
git status --short --branch
```

If you have uncommitted work, commit it or stash it before starting a new Design OS flow.

## 2. Keep your fork up to date

If your fork says it is behind the upstream repository, sync your fork on GitHub first, or fetch and merge upstream locally before starting new Design OS work.

A typical local setup looks like this:

```bash
git remote add upstream https://github.com/buildermethods/design-os.git
git fetch upstream
git merge upstream/main
```

If your local checkout already has an `upstream` remote, skip the `git remote add` command.

## 3. Install and run the app

```bash
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.

## 4. Start Codex CLI

From the repository root, start Codex CLI:

```bash
codex
```

Codex will see `AGENTS.md`, which now contains the full Design OS guidance for working in this repo.

## 5. Use the Codex prompt shortcuts

The Claude command files remain the source of truth for each Design OS workflow. For Codex, use the prompt shortcuts in `.codex/prompts/design-os/README.md`.

For example, to begin product planning, paste this into Codex:

```text
Read `agents.md` and `.claude/commands/design-os/product-vision.md`, then follow that workflow for my product idea. Ask me the required clarifying questions one step at a time, then create the product overview, roadmap, and data shape files.
```

## 6. Recommended Design OS order in Codex

Follow the same sequence as Claude Code:

1. Product vision
2. Design tokens
3. Application shell
4. Shape section
5. Sample data
6. Design screen
7. Screenshot design, if browser tooling is available
8. Export product

## 7. Review before committing

After each major Design OS step, review what changed:

```bash
git status --short
git diff --stat
git diff
```

Only commit when the generated product plan or screen design looks right.

## Notes for screenshot capture

The Claude screenshot workflow references Claude-specific MCP setup. In Codex, use whatever browser or Playwright tooling is available in your Codex environment, then save screenshots into the matching `product/sections/[section-id]/` folder.
