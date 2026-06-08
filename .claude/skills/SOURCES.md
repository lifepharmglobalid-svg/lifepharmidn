# Installed Skills — Sources

These skills were imported into `.claude/skills/` from the following upstream repositories.
Each skill lives in its own directory containing a `SKILL.md` (Claude Code auto-discovers them).

| Source repo | Skills imported |
|-------------|-----------------|
| https://github.com/nextlevelbuilder/ui-ux-pro-max-skill.git | 7 (banner-design, brand, design, design-system, slides, ui-styling, ui-ux-pro-max) |
| https://github.com/blader/humanizer.git | 1 (humanizer) |
| https://github.com/AgriciDaniel/banana-claude.git | 1 (banana) |
| https://github.com/coleam00/context-engineering-intro.git | 1 (build-with-agent-team) |
| https://github.com/coreyhaines31/marketingskills.git | 43 (marketing skill set) |
| https://github.com/ComposioHQ/awesome-claude-skills.git | 864 (32 curated + 832 `*-automation` Composio app skills) |
| https://github.com/remotion-dev/remotion.git | 19 (remotion video-creation skill + 18 internal agent skills from `.agents/skills/`) |
| https://github.com/VoltAgent/awesome-openclaw-skills.git | 0 — this repo is a curated *index* (an "awesome list" of links), not installable skills |
| https://github.com/anthropics/claude-code.git | 1 (frontend-design) |
| _(authored in-repo — not an upstream import)_ | 1 (simplify) |

**Total installed: 938 skills.**

## Notes
- Skill folder names are flat under `.claude/skills/`; no name collisions occurred across sources.
- `awesome-claude-skills/document-skills/{docx,pdf,pptx,xlsx}` were flattened to top-level `docx/`, `pdf/`, `pptx/`, `xlsx/`.
- From `remotion`, the published `remotion` video skill plus the repo's 18 internal agent skills under
  `.agents/skills/` were imported: add-cli-option, add-effect, add-expert, add-new-package, add-sfx,
  docs-demo, fix-dependabot, issue, issue-management, pr, pr-name, pr-ready, update-version, version,
  video-report, visual-mode, web-renderer-test, writing-docs. NOTE: these are Remotion-specific
  development/maintenance skills (CLI/option scaffolding, monorepo package creation, Dependabot fixes,
  PR/issue workflows, version bumps, docs authoring) and are intended for developing Remotion itself,
  not general-purpose use.
- `awesome-openclaw-skills` is a directory/index of skills hosted elsewhere; follow its links if you
  want to install any of those individually.
- `frontend-design` was imported from `anthropics/claude-code` (the repo bundles 10 skills; only the
  `frontend-design` skill was imported). It ships with its own `LICENSE.txt` alongside `SKILL.md`.
