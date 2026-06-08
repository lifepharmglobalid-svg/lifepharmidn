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
| https://github.com/remotion-dev/remotion.git | 1 (remotion — the published video-creation skill) |
| https://github.com/VoltAgent/awesome-openclaw-skills.git | 0 — this repo is a curated *index* (an "awesome list" of links), not installable skills |
| https://github.com/anthropics/claude-code.git | 1 (frontend-design) |
| _(authored in-repo — not an upstream import)_ | 1 (simplify) |

**Total installed: 920 skills.**

## Notes
- Skill folder names are flat under `.claude/skills/`; no name collisions occurred across sources.
- `awesome-claude-skills/document-skills/{docx,pdf,pptx,xlsx}` were flattened to top-level `docx/`, `pdf/`, `pptx/`, `xlsx/`.
- From `remotion`, only the published `remotion` video skill was imported; the repo's internal
  `.agents/skills/*` (Remotion's own dev tooling — PR helpers, dependabot fixes, etc.) were intentionally skipped.
- `awesome-openclaw-skills` is a directory/index of skills hosted elsewhere; follow its links if you
  want to install any of those individually.
- `frontend-design` was imported from `anthropics/claude-code` (the repo bundles 10 skills; only the
  `frontend-design` skill was imported). It ships with its own `LICENSE.txt` alongside `SKILL.md`.
