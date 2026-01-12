# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a **documentation-only repository** containing development standards and best practices for all Stark Tech Group projects. It uses `markdown-include` to compile modular markdown files into a single `README.md`.

## Build Commands

```bash
# Install dependencies (first time only)
npm install

# Build README.md from source files
npx markdown-include ./markdown.json

# Or use the full path if npx fails
node ./node_modules/markdown-include/bin/cli.js ./markdown.json
```

## Critical Editing Rules

**Never edit `README.md` directly** - it is auto-generated and will be overwritten.

To modify documentation:
1. Edit source files in `general/` subdirectories OR `_README.md` for structure changes
2. Run the build command to regenerate `README.md`
3. Commit both the source changes and regenerated `README.md`

## Architecture

```
_README.md              # Master template with #include directives
    ↓ (build)
README.md               # Generated output (DO NOT EDIT)

general/                # Modular content sections
├── general/            # g1-g25 general coding standards
├── security/           # sec-1 to sec-32 security standards
├── tests/              # test-1 to test-8 testing standards
├── PRs/                # pur-01 to pur-18 pull request standards
├── logging/            # log-1 to log-16 logging standards
├── source-control/     # scm-1 to scm-12 source control standards
├── devops/             # devop-1 to devop-8 CI/CD standards
├── dependencies/       # dep-1 to dep-6 dependency standards
├── design/             # des-1, des-2 design standards
├── datastore/          # ds-1 database standards
├── code-smells/        # Code smell reference
├── operations/         # Operations working agreements
├── resources/          # Learning resources
└── project init/       # Microservice setup checklist
```

## Include Syntax

The `_README.md` uses include directives:
```markdown
# Security
#include "general/security/README.md"
```

## Adding New Standards

1. Create/edit a `README.md` in the appropriate `general/` subdirectory
2. If adding a new section, add `#include "general/new-section/README.md"` to `_README.md`
3. Build and verify the output
4. Create PR following `feature/TICKET-description` naming convention

## GitHub Actions Workflow

The `.github/workflows/publish.yml` triggers on:
- Push to `feature/**` branches
- Manual dispatch

It automatically rebuilds `README.md` and publishes changes back to the branch.

## Standard Code Format

Standards use a table format with codes like `g1`, `sec-1`, `test-1`, etc. When adding new standards, follow the existing numbering and table structure in each section's README.
