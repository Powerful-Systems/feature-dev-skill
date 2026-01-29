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

## Key Features

- **🎯 Competing Hypotheses** - Evaluate 2-3 approaches before implementation to ensure the simplest solution
- **🛡️ Self-Validation** - Quality checklists at every phase prevent shipping broken code
- **♻️ Triple Simplification** - Dedicated reviews at phases 3, 6, and 7 to reduce complexity
- **🚦 Smart Stops** - Automatically pauses when blocked 3+ times or scope creeps
- **🧠 State Tracking** - Maintains context and decisions across long sessions
- **🔌 Dual Issue Tracking** - Works with Linear and GitHub Issues out of the box

## When to Use

**✅ Perfect for:**
- New features or capabilities
- Complex bug fixes
- Features with unclear requirements
- Projects prioritizing quality and simplicity

**❌ Overkill for:**
- Simple typo fixes or single-line changes
- Quick documentation updates

## Customization

Fork and customize for your project:

1. Copy `references/TEMPLATE.md` to `references/project-patterns.md`
2. Fill in your tech stack, patterns, and standards
3. Update `SKILL.md` Phase 4 to reference your patterns
4. Rename the skill in directory name + YAML frontmatter

See [TEMPLATE.md](references/TEMPLATE.md) for the complete template.

## Documentation

- **[EXAMPLES.md](EXAMPLES.md)** - 5 real-world scenarios
- **[SKILL.md](SKILL.md)** - Complete specification (439 lines)
- **[QUICKSTART.md](QUICKSTART.md)** - Publishing guide
- **[CONTRIBUTING.md](CONTRIBUTING.md)** - Contribution guidelines

## Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

- [Report a bug](https://github.com/Powerful-Systems/feature-dev-skill/issues/new?labels=bug)
- [Request a feature](https://github.com/Powerful-Systems/feature-dev-skill/issues/new?labels=enhancement)
- [Ask a question](https://github.com/Powerful-Systems/feature-dev-skill/discussions)

## License

MIT License - free to use, modify, and distribute commercially or non-commercially.

## Credits

Created by Avery at [Powerful Systems](https://powerfulsystems.com) for Claude Code.

Based on production workflows developed for the Chapter school comparison platform.

---

⭐ **Star this repo** if you find it useful!
