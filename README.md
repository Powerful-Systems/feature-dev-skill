# Feature Development Workflow

> A structured 10-phase workflow skill for Claude Code that guides AI agents through complete feature development—from issue to pull request.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-1.0-blue)](https://agentskills.io/specification)

## What is this?

This is a **[Claude Code](https://claude.ai/code) skill** that provides a systematic workflow for feature development. Instead of ad-hoc implementation, Claude follows a structured 10-phase process with built-in quality checks, simplification reviews, and stopping conditions.

Think of it as a "development methodology" for AI agents—ensuring consistent, high-quality feature delivery with proper planning, testing, and documentation.

## Why does this exist?

When working with AI agents on features, we found they often:
- Jump straight to coding without understanding requirements
- Over-engineer solutions
- Skip testing and validation
- Miss opportunities for simplification
- Don't track decisions across long sessions

This skill solves those problems by providing a structured workflow with:
- ✅ **Competing hypotheses** before implementation
- ✅ **Self-validation** at every phase
- ✅ **Mandatory simplification** reviews
- ✅ **Built-in stopping conditions** when blocked
- ✅ **State tracking** for long-horizon reasoning

## Quick Start

### Installation

```bash
# Clone this repository
git clone https://github.com/YOUR_USERNAME/feature-dev-skill.git

# Copy to your Claude skills directory
cp -r feature-dev-skill ~/.claude/skills/

# Restart Claude Code or reload skills
```

### Basic Usage

In Claude Code, invoke the skill with an issue ID:

```
/feature-dev-workflow #123
```

Claude will guide you through all 10 phases, asking for input when needed.

### Example Session

```
You: /feature-dev-workflow #456

Claude: I'll execute the feature development workflow for GitHub issue #456.

[Phase 1: Requirements Discovery]
Fetching issue...
Issue: "Add date range filter to search"

Let me explore existing filter implementations...
[explores codebase]

I've identified 3 competing approaches:
1. Dropdown with presets (simple, limited flexibility)
2. Calendar widget (better UX, more complex)
3. Text input with date parsing (powerful, error-prone)

Which approach do you prefer?

You: Calendar widget

Claude: [Continues through phases 2-10...]
```

## The 10-Phase Workflow

| Phase | Name | Purpose |
|-------|------|---------|
| 1 | **Requirements Discovery** | Transform rough issue into well-defined spec |
| 2 | **Implementation Planning** | Deep understanding of implementation |
| 3 | **Simplification Review** | Reduce complexity before coding |
| 4 | **Implementation** | Build feature incrementally |
| 5 | **Initial Testing** | Working state via end-to-end testing |
| 6 | **Code Simplification** | Reduce implementation complexity |
| 7 | **Design Review** | Optimal UI, design system aligned |
| 8 | **Comprehensive Testing** | End-to-end validation |
| 9 | **Pull Request** | Document work clearly |
| 10 | **Cleanup & Documentation** | Prepare for future sessions |

Each phase includes **self-validation checks** and **stopping conditions** to ensure quality.

## Key Features

### 🎯 Competing Hypotheses
Phase 1 requires evaluating 2-3 alternative approaches before committing to implementation. This prevents premature optimization and ensures the simplest solution is chosen.

### 🛡️ Self-Validation
Every phase includes a checklist of quality checks. If any fail, corrective action is required before proceeding.

### ♻️ Persistent Simplification
Phases 3, 6, and 7 focus on simplification—challenging complexity at multiple points in the workflow.

### 🚦 Smart Stopping Conditions
The workflow automatically stops and asks for help when:
- Blocked on the same issue 3+ times
- Browser automation fails repeatedly
- Approach seems fundamentally wrong
- Scope creep detected

### 🧠 State Tracking
Maintains context across long sessions by documenting:
- Decisions made and rationale
- Open questions and blockers
- Files modified
- What's working vs. not

### 🔌 Dual Issue Tracking
Works with both **Linear** and **GitHub Issues** out of the box.

| Format | System | Example |
|--------|--------|---------|
| `ABC-123` | Linear | Linear ticket ID |
| `#123` or `GH-123` | GitHub | GitHub issue number |
| Full URL | Either | Issue URL |

## When to Use This Skill

### ✅ Perfect for:
- Implementing new features
- Building new functionality
- Adding capabilities
- Complex bug fixes requiring multiple phases
- Features with unclear requirements
- Projects where quality and simplicity matter

### ❌ Overkill for:
- Simple typo fixes
- Single-line changes
- Quick documentation updates
- Exploratory tasks

## Real-World Examples

See [EXAMPLES.md](EXAMPLES.md) for 5 detailed examples including:
- Simple UI feature addition
- Complex backend with database changes
- Bug fix that revealed scope creep
- Workflow stopped early due to architectural issues
- Parallel execution for independent work

## Integration with Other Skills

This workflow works seamlessly with:

- **[code-simplifier](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/code-simplifier)** - Automated code simplification (Phases 6, 7)
- **[frontend-design](https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design)** - UI/UX review (Phase 7)
- **[web-design-guidelines](https://github.com/vercel-labs/agent-skills/tree/main/skills/web-design-guidelines)** - Accessibility audit (Phase 7)
- **TanStack Router/Start** - For TanStack-based projects
- Your custom project skills

## Customization

This skill is designed to be **forked and customized** for your specific project.

### Quick Customization

1. **Fork this repo**
2. **Copy `references/TEMPLATE.md`** to `references/project-patterns.md`
3. **Fill in your tech stack**, coding standards, and patterns
4. **Update `SKILL.md` Phase 4** to reference your patterns
5. **Rename the skill** (directory name + YAML frontmatter)
6. **Install your customized version**

See [TEMPLATE.md](references/TEMPLATE.md) for a complete customization template.

### Example Customization

Want to see a real customized version? Check out the `chapter-dev` skill this was derived from—a production workflow for the Chapter school comparison platform with TanStack, PostgreSQL, and ShadCN patterns.

## Documentation

- **[SKILL.md](SKILL.md)** - The complete skill specification (439 lines)
- **[EXAMPLES.md](EXAMPLES.md)** - 5 real-world usage scenarios
- **[QUICKSTART.md](QUICKSTART.md)** - Get started in 5 minutes
- **[CONTRIBUTING.md](CONTRIBUTING.md)** - How to contribute
- **[AGENTSKILLS.md](AGENTSKILLS.md)** - AgentSkills.io compliance details
- **[CHANGELOG.md](CHANGELOG.md)** - Version history

## Core Principles

This workflow is built on 5 core principles:

1. **Incremental Progress** - Steady advances on few things at a time
2. **Persistent Simplification** - Challenge complexity at every phase
3. **State Tracking** - Document decisions across phases
4. **Self-Validation** - Check work before proceeding
5. **Fail Fast** - Stop and ask when blocked

All contributions and customizations should align with these principles.

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

Quick links:
- [Report a bug](https://github.com/YOUR_USERNAME/feature-dev-skill/issues/new?labels=bug)
- [Request a feature](https://github.com/YOUR_USERNAME/feature-dev-skill/issues/new?labels=enhancement)
- [Ask a question](https://github.com/YOUR_USERNAME/feature-dev-skill/discussions)

## Compatibility

This skill is designed for:
- **Claude Code** (primary)
- Other Claude-based agent systems supporting the AgentSkills format
- Agents with access to file operations, shell commands, and optionally browser automation

## Version

**Current version:** 1.0.0

See [CHANGELOG.md](CHANGELOG.md) for release history.

## License

MIT License - see [LICENSE](LICENSE) for details.

You are free to use, modify, and distribute this skill commercially or non-commercially.

## Credits

Created by **Avery at [Powerful Systems](https://powerfulsystems.com)** for use with Claude Code.

Based on production workflows developed for the Chapter school comparison platform.

## Support

- **Issues:** [GitHub Issues](https://github.com/YOUR_USERNAME/feature-dev-skill/issues)
- **Discussions:** [GitHub Discussions](https://github.com/YOUR_USERNAME/feature-dev-skill/discussions)
- **Twitter:** [@YOUR_HANDLE](https://twitter.com/YOUR_HANDLE)

---

**Ready to try it?** Install the skill and run `/feature-dev-workflow #YOUR_ISSUE_ID` in Claude Code!

⭐ **Star this repo** if you find it useful!
