# Blue Orange Digital — OpenClaw Skills

Shared skills library for Blue Orange Digital's AI-enabled delivery platform.

## Usage

Clone to your local skills directory:

```bash
git clone https://github.com/emmanash-bod/openclaw-skills.git ~/.agents/skills/blueorange
```

Or symlink individual skills:

```bash
ln -s /path/to/openclaw-skills/blueprint-assessment ~/.agents/skills/blueprint-assessment
```

OpenClaw picks up skills automatically from `~/.agents/skills/`.

## Skills

| Skill | Description | Status |
|-------|-------------|--------|
| `blueprint-assessment` | Deliver Blueprint AI readiness assessments to clients | ✅ Ready |
| `client-onboarding` | Standardized client engagement kickoff workflow | ✅ Ready |
| `sow-processor` | Parse, validate, and track SOW lifecycle | ✅ Ready |
| `delivery-report` | Generate client delivery status reports | ✅ Ready |
| `meeting-prep` | Prepare briefing docs for client and partner meetings | ✅ Ready |
| `content-pipeline` | Research, draft, and publish content workflow | ✅ Ready |

## Skill Structure

Each skill follows the [Agent Skills standard](https://github.com/openclaw/openclaw):

```
skill-name/
├── SKILL.md          # Required: frontmatter + instructions
├── scripts/          # Optional: executable automation
├── references/       # Optional: docs loaded into context
└── assets/           # Optional: templates, files
```

## Contributing

1. Create a new directory with your skill name
2. Add a `SKILL.md` with `name` and `description` frontmatter
3. Test locally with your OpenClaw instance
4. Push to this repo — team pulls to update

## Team Setup

```bash
# First time
git clone https://github.com/emmanash-bod/openclaw-skills.git ~/.agents/skills/blueorange

# Update
cd ~/.agents/skills/blueorange && git pull
```
