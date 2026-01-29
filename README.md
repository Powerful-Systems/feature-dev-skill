# Feature Development Workflow

> A structured 10-phase workflow skill for Claude Code that guides AI agents through complete feature development—from issue to pull request.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-1.0-blue)](https://agentskills.io/specification)

## Overview

This [Claude Code](https://claude.ai/code) skill provides a systematic workflow for feature development. Instead of ad-hoc implementation, Claude follows a structured 10-phase process with built-in quality checks, simplification reviews, and stopping conditions.

**Core principles:**
- **Incremental Progress** - Steady advances on few things at a time
- **Persistent Simplification** - Challenge complexity at every phase
- **Self-Validation** - Check work before proceeding
- **Fail Fast** - Stop and ask when blocked

## Installation

```bash
git clone https://github.com/Powerful-Systems/feature-dev-skill.git ~/.claude/skills/feature-dev-skill
```

Restart Claude Code or reload skills.

## Integration

This skill works seamlessly with:
- [code-simplifier](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/code-simplifier) - Automated code simplification (Phases 6, 7)
- [frontend-design](https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design) - UI/UX review (Phase 7)
- [web-design-guidelines](https://github.com/vercel-labs/agent-skills/tree/main/skills/web-design-guidelines) - Accessibility audit (Phase 7)
- Your custom project skills

All integrations are optional but recommended for best results.

## Usage

```
/feature-dev-workflow #123
```

Works with both Linear (`ABC-123`) and GitHub Issues (`#123`, `GH-123`).

**Example:**
```
You: /feature-dev-workflow #456

Claude: [Phase 1: Requirements Discovery]
Issue: "Add date range filter to search"

I've identified 3 competing approaches:
1. Dropdown with presets (simple, limited)
2. Calendar widget (better UX, more complex)
3. Text input parsing (powerful, error-prone)

Which approach do you prefer?
```

## The 10 Phases

| Phase | Focus | Key Activity |
|-------|-------|--------------|
| 1 | Requirements Discovery | Competing hypotheses, scope refinement |
| 2 | Implementation Planning | Deep codebase exploration, dependencies |
| 3 | Simplification Review | Challenge complexity before coding |
| 4 | Implementation | Incremental building with patterns |
| 5 | Initial Testing | End-to-end validation, bug fixes |
| 6 | Code Simplification | Remove unnecessary complexity |
| 7 | Design Review | UI/UX alignment, accessibility |
| 8 | Comprehensive Testing | Full validation, formatter, build |
| 9 | Pull Request | Clear documentation of changes |
| 10 | Cleanup & Documentation | Prepare for future work |

Each phase includes self-validation checks and stopping conditions.

## Customization

Fork and customize for your project:

1. **Add project patterns**: Copy `references/TEMPLATE.md` to `references/project-patterns.md`
2. **Fill in your details**: Tech stack, coding standards, architecture patterns
3. **Reference your patterns**: Update `SKILL.md` Phase 4 to point to your patterns file
4. **Rename the skill**: Update directory name + YAML frontmatter

### Adding Project Documentation

Place your project-specific documentation in the `references/` directory:

```
your-project-skill/
├── SKILL.md
└── references/
    ├── project-patterns.md    # Main patterns (from TEMPLATE.md)
    ├── tech-stack.md          # Technology details
    ├── api-conventions.md     # API design patterns
    ├── database-schema.md     # DB patterns and migrations
    └── common-pitfalls.md     # Things to avoid
```

**Where to document what:**
- **Tech stack & patterns** → `references/project-patterns.md` (use the template)
- **API/endpoint conventions** → `references/api-conventions.md`
- **Database patterns** → `references/database-schema.md`
- **UI/component library** → `references/ui-patterns.md`
- **Common mistakes** → `references/common-pitfalls.md`

Reference these files in `SKILL.md` Phase 4 so Claude knows to read them during implementation.

See [TEMPLATE.md](references/TEMPLATE.md) for the complete customization template.

## License

MIT License - free to use, modify, and distribute commercially or non-commercially.

---

⭐ **Star this repo** if you find it useful!
