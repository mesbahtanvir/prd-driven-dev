# PRD-004: Claude Code Command Integration

**Status:** Draft
**Created:** 2026-01-29

---

## Problem Statement

Users currently have to manually copy prompt content or reference prompt files when working with Claude Code. This creates friction:

1. **Discovery** — Users don't know which prompts exist without checking the repo
2. **Invocation** — Copy-pasting prompts is tedious and error-prone
3. **Arguments** — No way to pass context (PRD number, file paths) to prompts
4. **Updates** — No way to get latest prompts without manual copying
5. **Per-project setup** — Having to configure each project is tedious

## Solution

Create an npm package that installs PDD commands **globally** to `~/.claude/commands/`, making them available in all projects with a single installation.

### Installation

```bash
# Install globally (one-time setup)
npm install -g pdd

# Or use npx for one-off
npx pdd install
```

### Updates

```bash
# Update to latest version
npm update -g pdd

# Or check and update
pdd update

# Check current version
pdd --version
```

### What Gets Installed

```
~/.claude/
└── commands/
    ├── prd.md              # /prd [type] — Create a new PRD
    ├── prd-init.md         # /prd-init — Initialize PDD in current project
    ├── prd-status.md       # /prd-status — Show all PRDs and status
    ├── audit-features.md   # /audit-features [prd] — Audit implementation
    ├── audit-tests.md      # /audit-tests [prd] — Audit test coverage
    ├── audit-alignment.md  # /audit-alignment — PRD vs code alignment
    ├── audit-ux.md         # /audit-ux — UX audit
    └── audit-qa.md         # /audit-qa — Quality audit
```

### Example Usage (After Installation)

```bash
# In any project, these commands are now available:

/prd feature          # Create a new feature PRD
/prd bugfix           # Create a bugfix PRD
/prd-init             # Set up docs/prd/ in current project
/prd-status           # Show PRD dashboard
/audit-features 005   # Audit PRD-005 implementation
/audit-qa             # Find bugs and quality issues
```

## Acceptance Criteria

### AC1: npm Package
- [ ] Package published to npm as `pdd` (or `prd-driven-dev`)
- [ ] `npm install -g pdd` installs commands to `~/.claude/commands/`
- [ ] `npm update -g pdd` updates commands to latest version
- [ ] Package includes version number in installed commands

### AC2: CLI Commands
- [ ] `pdd install` — Install/reinstall commands to ~/.claude/commands/
- [ ] `pdd update` — Check for updates and install if available
- [ ] `pdd --version` — Show installed version
- [ ] `pdd uninstall` — Remove commands from ~/.claude/commands/

### AC3: Slash Commands Created
- [ ] `/prd [type]` — Create PRD (feature/bugfix/refactor)
- [ ] `/prd-init` — Initialize PDD in current project (creates docs/prd/, CLAUDE.md)
- [ ] `/prd-status` — Show all PRDs with status
- [ ] `/audit-features [prd]` — Audit feature implementation
- [ ] `/audit-tests [prd]` — Audit test coverage
- [ ] `/audit-alignment` — Check PRD vs code alignment
- [ ] `/audit-ux` — Audit UX issues
- [ ] `/audit-qa` — Find bugs and quality issues

### AC4: Update Mechanism
- [ ] Commands include version comment for tracking
- [ ] `pdd update` compares installed vs npm version
- [ ] Update preserves user customizations (or warns before overwriting)

### AC5: Documentation
- [ ] README updated with installation instructions
- [ ] `pdd --help` shows usage
- [ ] Each command includes usage comment at top

## Out of Scope

- VS Code extension (future PRD-005)
- MCP server integration (future PRD)
- Per-project installation (only global)
- Auto-update (manual update only)

## Technical Notes

### Package Structure

```
pdd/
├── package.json
├── bin/
│   └── pdd.js           # CLI entry point
├── commands/            # Command templates
│   ├── prd.md
│   ├── prd-init.md
│   ├── audit-features.md
│   └── ...
└── lib/
    ├── install.js       # Copy commands to ~/.claude/commands/
    ├── update.js        # Check and update commands
    └── version.js       # Version management
```

### Version Tracking

Each installed command includes a version comment:

```markdown
<!-- pdd v1.0.0 -->
# /prd — Create a new PRD
...
```

This allows `pdd update` to detect outdated commands.

### Cross-Platform Paths

```javascript
const homeDir = os.homedir();
const claudeCommandsDir = path.join(homeDir, '.claude', 'commands');
```

## Success Metrics

1. One-command global installation works
2. Commands available in all projects after install
3. `pdd update` successfully updates to latest version
4. Users don't need to configure per-project

---

## Changelog

| Date | Change |
|------|--------|
| 2026-01-29 | PRD created |
| 2026-01-29 | Updated to global installation + npm package |
