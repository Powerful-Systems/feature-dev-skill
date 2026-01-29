# AgentSkills.io Specification Compliance

This skill follows the [AgentSkills.io specification](https://agentskills.io/specification).

## Structure

```
feature-dev-workflow/
├── SKILL.md              # Required: Main skill file with YAML frontmatter
├── references/           # Optional: Additional documentation
│   └── TEMPLATE.md       # Project-specific pattern template
├── README.md             # Repository documentation
├── EXAMPLES.md           # Usage examples
├── CONTRIBUTING.md       # Contribution guidelines
├── CHANGELOG.md          # Version history
├── LICENSE               # MIT License
└── AGENTSKILLS.md        # This file
```

## Validation

To validate this skill against the specification:

```bash
# Install the reference validator
npm install -g @agentskills/validator

# Validate the skill
agentskills validate feature-dev-workflow/
```

Or using the Rust reference implementation:

```bash
# Install skills-ref
cargo install skills-ref

# Validate
skills-ref validate ./feature-dev-workflow
```

## Progressive Disclosure

This skill follows the progressive disclosure pattern:

1. **Metadata** (~100 tokens): `name` and `description` loaded at startup
2. **Instructions** (439 lines, ~3000-4000 tokens): Full `SKILL.md` loaded when activated
3. **Resources** (as needed): `references/TEMPLATE.md` loaded only when customizing

## File References

All file references use relative paths from skill root:

- [Project patterns template](references/TEMPLATE.md)

## Frontmatter Fields

### Required
- ✅ `name`: `feature-dev-workflow` (valid: lowercase, hyphens, no consecutive hyphens)
- ✅ `description`: Describes what the skill does and when to use it

### Optional
- ✅ `license`: `MIT` (references bundled LICENSE file)
- ✅ `metadata.author`: `powerful-systems`
- ✅ `metadata.version`: `1.0.0`

## Installation

### Standard Installation

```bash
# Clone or download the skill
git clone https://github.com/YOUR_USERNAME/feature-dev-workflow.git

# Copy to Claude skills directory
cp -r feature-dev-workflow ~/.claude/skills/

# Restart Claude Code or reload skills
```

### Alternative: Direct Download

```bash
curl -L https://github.com/YOUR_USERNAME/feature-dev-workflow/archive/refs/heads/main.zip -o skill.zip
unzip skill.zip
cp -r feature-dev-workflow-main ~/.claude/skills/feature-dev-workflow
rm -rf feature-dev-workflow-main skill.zip
```

## Publishing to AgentSkills.io

To submit this skill to the AgentSkills.io registry:

1. Ensure the repository is public on GitHub
2. Validate the skill structure
3. Submit via the AgentSkills.io submission form
4. Tag your repository with `agentskills` topic

## Compatibility

This skill is designed for:
- Claude Code (primary)
- Other Claude-based agent systems that support the AgentSkills format
- Agents with access to:
  - File system operations (Read, Write, Edit)
  - Shell commands (Bash, git, gh)
  - Browser automation (optional, for testing)
  - Linear MCP or GitHub CLI (for issue tracking)

## Version History

See [CHANGELOG.md](CHANGELOG.md) for complete version history.

Current version: **1.0.0**

## License

This skill is released under the MIT License. See [LICENSE](LICENSE) for details.

## Support

- Issues: https://github.com/YOUR_USERNAME/feature-dev-workflow/issues
- Discussions: https://github.com/YOUR_USERNAME/feature-dev-workflow/discussions
- Documentation: [README.md](README.md)
