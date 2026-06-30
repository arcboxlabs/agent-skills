# Skills

Use this repo as your user skills directory:

```bash
./install.sh
```

`git submodule update --init` populates `vendor/vercel-agent-skills`, which the `skills/react-best-practices` symlink points into. The submodule is declared `shallow = true` in `.gitmodules`, so this fetches only the latest commit.

For Amp, `~/.config/amp/settings.json` can also point directly at this directory with `amp.skills.path`. Keep `~/.agents/skills` linked too; Amp path-scoped guidance `@`-mentions that path.

## Global Instructions

`install.sh` symlinks:

- Amp: `global/AGENTS.md`, `checks/`, and `~/.agents/skills`
- Claude Code: `global/CLAUDE.md` and each skill under `~/.claude/skills/`
- Codex: `global/CODEX.md` and each skill under `~/.codex/skills/`

Check an existing install without changing links:

```bash
./install.sh --check
```

Edit `global/parts/` — the pre-commit hook rebuilds automatically.

`global/claude.settings.json` is a reference settings file. Merge it manually instead of symlinking it over an existing `~/.claude/settings.json`.

Path-scoped guidance uses Claude Code `paths` and Amp `globs` frontmatter in skill files. For Amp, add or remove `@` mentions in `global/parts/20-path-scoped.amp.md`.

## Preferred Tools

The global instructions assume these CLI tools are available:

```bash
brew install ast-grep fd jq ripgrep sd yq
```

## Available Skills

- [better-skill-creator](skills/better-skill-creator/SKILL.md): write better skills than the default
- [browser-testing](skills/browser-testing/SKILL.md): browser automation with Playwright MCP
- [linear](skills/linear/SKILL.md): ArcBox Linear workflow — issue lifecycle, comment-driven sync, status, triage
- [rust-coding](skills/rust-coding/SKILL.md): write high-quality Rust code
- [slides-creator](skills/slides-creator/SKILL.md): create new slide decks and `.pptx` presentations
- [waku-idiomatic](skills/waku-idiomatic/SKILL.md): opinionated Waku patterns and structure

### Vendored

Symlinked from `vendor/vercel-agent-skills` ([vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills)):

- [react-best-practices](skills/react-best-practices/SKILL.md): React and Next.js performance patterns from Vercel Engineering

Symlinked from `vendor/karpathy-skills` ([multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills)):

- [karpathy-guidelines](skills/karpathy-guidelines/SKILL.md): behavioral guidelines to reduce common LLM coding mistakes
