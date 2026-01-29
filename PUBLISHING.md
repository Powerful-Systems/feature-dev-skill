# Publishing Guide

This guide explains how to publish the Feature Development Workflow skill as a standalone repository.

## Repository Structure

Your skill is now organized as a complete, publishable repository:

```
feature-dev-workflow/
├── .gitignore              # Git ignore patterns
├── CHANGELOG.md            # Version history
├── CONTRIBUTING.md         # Contribution guidelines
├── EXAMPLES.md             # Real-world usage examples
├── LICENSE                 # MIT License
├── PUBLISHING.md           # This file
├── README.md               # Main documentation
├── SKILL.md                # The skill itself
└── references/
    └── TEMPLATE.md         # Template for project customization
```

## Publishing Steps

### 1. Create GitHub Repository

```bash
# Create a new repository on GitHub (via web or CLI)
gh repo create feature-dev-workflow --public --description "End-to-end feature development workflow skill for Claude Code"

# Or create it via the GitHub web interface
```

### 2. Initialize Git Repository

```bash
cd feature-dev-workflow

# Initialize git
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial release: Feature Development Workflow v1.0.0"

# Add remote (replace YOUR_USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/feature-dev-workflow.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Create Release

```bash
# Tag the release
git tag -a v1.0.0 -m "Release v1.0.0: Initial public release"
git push origin v1.0.0

# Or create a release via GitHub web interface
gh release create v1.0.0 --title "v1.0.0 - Initial Release" --notes "See CHANGELOG.md for details"
```

### 4. Add Topics to Repository

On GitHub, add relevant topics to help users discover your skill:
- `claude-code`
- `claude-skill`
- `ai-agents`
- `development-workflow`
- `feature-development`
- `software-engineering`

### 5. Enable GitHub Features

Consider enabling:
- **Issues**: For bug reports and feature requests
- **Discussions**: For Q&A and community discussions
- **GitHub Pages**: For documentation (optional)
- **GitHub Actions**: For automated testing (optional)

## Distribution

### Installation Instructions for Users

Add this to your README (already included):

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/feature-dev-workflow.git

# Copy to Claude skills directory
cp -r feature-dev-workflow ~/.claude/skills/

# Restart Claude Code or reload skills
```

### Alternative: Direct Download

```bash
# Download and extract
curl -L https://github.com/YOUR_USERNAME/feature-dev-workflow/archive/refs/heads/main.zip -o skill.zip
unzip skill.zip
cp -r feature-dev-workflow-main ~/.claude/skills/feature-dev-workflow
rm -rf feature-dev-workflow-main skill.zip
```

## Promoting Your Skill

### 1. Share on Social Media

Post on:
- X/Twitter with hashtags: #ClaudeCode #AIAgents
- LinkedIn
- Relevant Discord servers
- Reddit (r/ClaudeAI, r/artificialintelligence)

### 2. Submit to Skill Directories

If Anthropic or the community maintains a skill directory, submit your skill for inclusion.

### 3. Write a Blog Post

Share your experience:
- Why you created this skill
- How it improves your workflow
- Real-world examples from EXAMPLES.md
- Lessons learned

### 4. Create a Demo Video

Record a quick demo showing:
- Installation
- Running through all 10 phases
- The self-validation checks
- Customization for a specific project

## Maintaining the Skill

### Versioning

Follow Semantic Versioning (MAJOR.MINOR.PATCH):

- **MAJOR**: Breaking changes to the workflow
- **MINOR**: New phases or significant enhancements
- **PATCH**: Bug fixes and small improvements

### Update Checklist

When releasing a new version:

1. Update CHANGELOG.md with changes
2. Update version in README if mentioned
3. Test the skill end-to-end
4. Create git tag for the version
5. Create GitHub release
6. Announce in discussions/issues

### Accepting Contributions

1. Review PRs against CONTRIBUTING.md guidelines
2. Ensure changes align with core principles
3. Test changes thoroughly
4. Update CHANGELOG.md
5. Thank contributors!

## Analytics (Optional)

Consider tracking:
- GitHub stars (popularity)
- Issues opened (engagement)
- Forks (customization)
- Downloads (via GitHub releases)

## Support Channels

Set up:
- **GitHub Issues**: For bugs and feature requests
- **GitHub Discussions**: For Q&A and community
- **Discord/Slack**: For real-time chat (optional)

## License Compliance

This skill uses MIT License, which means:
- ✅ Anyone can use it commercially
- ✅ Anyone can modify and redistribute
- ✅ No warranty is provided
- ⚠️ Must include copyright notice

Make sure users understand these terms.

## Next Steps

1. [ ] Create GitHub repository
2. [ ] Push initial commit
3. [ ] Create v1.0.0 release
4. [ ] Add repository topics
5. [ ] Enable issues and discussions
6. [ ] Share on social media
7. [ ] Write announcement blog post
8. [ ] Submit to skill directories (if available)

## Example Repository README Badge

Add to the top of your README:

```markdown
![Version](https://img.shields.io/github/v/release/YOUR_USERNAME/feature-dev-workflow)
![License](https://img.shields.io/github/license/YOUR_USERNAME/feature-dev-workflow)
![Stars](https://img.shields.io/github/stars/YOUR_USERNAME/feature-dev-workflow)
```

## Questions?

If you have questions about publishing, open an issue or discussion in the repository.

---

**Good luck with your release! 🚀**
