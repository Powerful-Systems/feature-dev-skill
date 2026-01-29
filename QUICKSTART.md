# Quick Start Guide

Get your Feature Development Workflow skill published in 15 minutes.

## Current Structure

Your skill is ready to publish with this structure:

```
feature-dev-workflow/
├── .gitignore              # Git ignore patterns
├── AGENTSKILLS.md          # AgentSkills.io compliance documentation
├── CHANGELOG.md            # Version history
├── CONTRIBUTING.md         # How others can contribute
├── EXAMPLES.md             # 5 real-world usage examples
├── LICENSE                 # MIT License
├── PUBLISHING.md           # Detailed publishing guide
├── QUICKSTART.md           # This file
├── README.md               # Main documentation (installation, features, etc.)
├── SKILL.md                # The skill itself (439 lines, AgentSkills-compliant)
└── references/
    └── TEMPLATE.md         # Template for project customization
```

## ✅ Pre-flight Checklist

Your skill is ready because:

- ✅ AgentSkills.io specification compliant
- ✅ Valid YAML frontmatter with name, description, license, metadata
- ✅ Under 500 lines (439 lines)
- ✅ Progressive disclosure pattern
- ✅ MIT License included
- ✅ Documentation complete
- ✅ Examples included
- ✅ Contribution guidelines
- ✅ Version 1.0.0 ready

## 5-Minute Publishing

### 1. Create Repository (2 minutes)

```bash
cd /Users/avery/code/claude-skills/feature-dev-workflow

# Initialize git
git init
git add .
git commit -m "Initial release: Feature Development Workflow v1.0.0"

# Create GitHub repo (replace YOUR_USERNAME)
gh repo create feature-dev-workflow \
  --public \
  --description "End-to-end feature development workflow skill for Claude Code" \
  --source=. \
  --remote=origin \
  --push
```

**Or via GitHub web:**
1. Go to https://github.com/new
2. Name: `feature-dev-workflow`
3. Description: "End-to-end feature development workflow skill for Claude Code"
4. Public
5. Don't initialize with README/LICENSE (we have them)
6. Create repository
7. Follow the push instructions

### 2. Add Topics (1 minute)

On GitHub, add these topics to help discovery:
- `claude-code`
- `claude-skill`
- `agentskills`
- `ai-agents`
- `development-workflow`
- `software-engineering`

### 3. Create Release (2 minutes)

```bash
# Tag and create release
git tag -a v1.0.0 -m "Release v1.0.0: Initial public release"
git push origin v1.0.0

# Create GitHub release
gh release create v1.0.0 \
  --title "v1.0.0 - Initial Release" \
  --notes "Complete end-to-end feature development workflow for Claude Code. See CHANGELOG.md for details."
```

**Or via GitHub web:**
1. Go to Releases → Draft a new release
2. Tag: `v1.0.0`
3. Title: `v1.0.0 - Initial Release`
4. Description: Copy from CHANGELOG.md
5. Publish release

Done! Your skill is now public at `https://github.com/YOUR_USERNAME/feature-dev-workflow`

## Installation Instructions for Users

Add this to your repository description or pin it:

```bash
# Install the skill
git clone https://github.com/YOUR_USERNAME/feature-dev-workflow.git
cp -r feature-dev-workflow ~/.claude/skills/
```

Or one-liner:

```bash
git clone https://github.com/YOUR_USERNAME/feature-dev-workflow.git ~/.claude/skills/feature-dev-workflow
```

## Post-Publishing (Optional)

### Share (5 minutes)

Post on:
- **X/Twitter**: "Just published a Claude Code skill for end-to-end feature development! 10 phases from issue to PR with self-validation and simplification built-in. #ClaudeCode #AIAgents"
- **LinkedIn**: Professional post about how this improves your workflow
- **Reddit**: r/ClaudeAI, r/SideProject
- **Discord**: Claude/AI agent communities

### Submit to AgentSkills.io (if available)

Once AgentSkills.io has a registry, submit your skill.

### Enable Discussions

On GitHub:
1. Settings → Features → Discussions → Enable
2. Create welcome post
3. Add Q&A and Ideas categories

## Validation

Validate your skill meets the spec:

```bash
# Using npm validator (when available)
npm install -g @agentskills/validator
agentskills validate feature-dev-workflow/

# Or Rust reference (when available)
cargo install skills-ref
skills-ref validate ./feature-dev-workflow
```

## Next Steps

1. [ ] **Today**: Publish to GitHub (steps above)
2. [ ] **This week**: Share on social media
3. [ ] **This month**: Collect feedback and iterate
4. [ ] **Ongoing**: Respond to issues and PRs

## Customization Instructions

For users who want to customize:

1. Clone the skill
2. Copy `references/TEMPLATE.md` to `references/project-patterns.md`
3. Fill in project-specific details
4. Update `SKILL.md` Phase 4 to reference the new file
5. Rename the skill (update directory name, YAML `name` field, etc.)

## Support

After publishing, monitor:
- **GitHub Issues**: Bug reports and feature requests
- **GitHub Discussions**: Q&A and community ideas
- **Stars**: Popularity indicator
- **Forks**: People customizing for their projects

## Marketing Copy

Use these in your posts:

**Short (Twitter/X)**:
"Feature Development Workflow: A Claude Code skill for structured end-to-end development. 10 phases, self-validation, simplification built-in. MIT licensed. [link]"

**Medium (LinkedIn)**:
"Just open-sourced our feature development workflow for Claude Code! It guides AI agents through 10 phases from requirements discovery to PR, with self-validation at each step. Built on patterns from real production use. Check it out: [link]"

**Long (Blog post)**:
See EXAMPLES.md for real-world scenarios you can turn into a blog post.

## FAQ

**Q: Can people use this commercially?**
A: Yes! MIT license allows commercial use.

**Q: Should I accept PRs?**
A: Yes! See CONTRIBUTING.md for guidelines.

**Q: How do I update the version?**
A: Update version in frontmatter metadata, update CHANGELOG.md, create new git tag and GitHub release.

**Q: What if someone wants a feature I don't want to add?**
A: They can fork and customize! That's the beauty of open source.

## Ready to Publish?

```bash
# Final check
cat SKILL.md | head -10  # Verify frontmatter
git status               # Should be clean

# Go for it!
git push origin main
git tag v1.0.0
git push origin v1.0.0
```

🚀 **You're ready to ship!**
