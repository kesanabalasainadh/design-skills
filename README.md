# Design skills

Design skills for Claude Code, collected 2026-11-18. Each folder under `skills/` is one skill: a `SKILL.md` that Claude loads when the task matches, plus any reference files it uses.

| Skill | What it's for | From |
|---|---|---|
| `design-consultation` | Builds a full design system (aesthetic, type, colour, layout, spacing, motion) and writes `DESIGN.md` | gstack |
| `plan-design-review` | Reviews a plan or spec as a designer before anything is built | gstack |
| `design-shotgun` | Generates several design variants side by side, collects feedback, iterates | gstack |
| `design-html` | Turns an approved design into production HTML/CSS (vendored `pretext.js`) | gstack |
| `design-review` | Visual QA on a live site: finds spacing, hierarchy and consistency issues and fixes them | gstack |
| `frontend-design` | Distinctive, production-grade frontend interfaces; avoids generic "AI" looks | Anthropic (Claude plugins) |
| `motion-design` | Motion principles for UI: timing, easing, choreography, micro-interactions | LottieFiles |

## Install

Copy or symlink the folders you want into your skills directory:

```bash
git clone <this repo> ~/src/design-skills
mkdir -p ~/.claude/skills
for s in ~/src/design-skills/skills/*; do ln -sfn "$s" ~/.claude/skills/"$(basename "$s")"; done
```

Start a new Claude Code session; the skills appear in the skill list and can be invoked as `/design-review`, `/design-consultation`, and so on.

## Notes

- The five gstack skills call gstack's helper tools (the headless browser `$B` and the design generator `$D`) from `~/.claude/skills/gstack/`. Install gstack too if you want them to run end to end; without it they still work as written guidance.
- These are copies of the versions installed on 2026-11-18. Upstream updates are not pulled in automatically.

## Licences

Third-party content, kept under its original licence (see `licenses/`):
- gstack skills: MIT, © 2026 Garry Tan
- frontend-design: Apache 2.0, Anthropic
- motion-design: MIT, © 2025 LottieFiles

This repository is private. Check those licences, and keep the notices, before sharing it more widely.
