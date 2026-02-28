# Claude Code Workflow & AGENTS.md Template

A starter template for structuring AI-assisted development with Claude Code. Define your project conventions once, get consistent results every session.

## What is AGENTS.md?

`AGENTS.md` is a project-level instruction file that Claude Code reads automatically. It tells Claude:
- How your project is structured
- What conventions to follow
- What tools and commands to use
- What to avoid

Think of it as onboarding docs for your AI pair programmer.

## Quick Start

Copy `AGENTS.md` to your project root:

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/shellsage-ai/claude-code-workflow/main/AGENTS.md
```

Then customize it for your project.

## Template: AGENTS.md

```markdown
# AGENTS.md

## Project Overview
[Your project name] â€” [one-line description]

## Tech Stack
- Language: [e.g., TypeScript 5.x]
- Framework: [e.g., Next.js 15, Express, FastAPI]
- Database: [e.g., PostgreSQL via Prisma]
- Testing: [e.g., Vitest, pytest]
- Package manager: [e.g., pnpm, npm, pip]

## Project Structure
src/
â”œâ”€â”€ components/    # React components
â”œâ”€â”€ lib/           # Shared utilities
â”œâ”€â”€ routes/        # API routes
â”œâ”€â”€ services/      # Business logic
â””â”€â”€ types/         # TypeScript types

## Conventions
- Use named exports (no default exports)
- Prefer `const` arrow functions for components
- Error handling: use Result types, not try/catch for business logic
- All API responses follow { data, error, meta } shape
- Database queries go in services/, never in routes/

## Commands
- `pnpm dev` â€” start dev server
- `pnpm test` â€” run tests
- `pnpm build` â€” production build
- `pnpm lint` â€” lint + type check

## Before Committing
1. Run `pnpm test` â€” all tests must pass
2. Run `pnpm lint` â€” no errors
3. Use conventional commits: feat:, fix:, docs:, chore:
4. Keep PRs focused â€” one feature or fix per PR

## Do NOT
- Modify .env files
- Add dependencies without asking
- Change database schema without migration
- Push directly to main
- Use `any` type in TypeScript
```

## Workflow Tips

### Session Start
Claude reads AGENTS.md automatically. No need to paste instructions every time.

### Multi-File Projects
You can also place context files in subdirectories:
- `.claude/settings.json` â€” Claude Code settings
- `.claude/skills/` â€” Reusable skill definitions

### Team Projects
Commit AGENTS.md to your repo. Everyone on the team (and their AI agents) follows the same conventions.

## Going Further

This free template covers the basics. The **[Claude Code Workflow Kit](https://shellsage-ai.github.io/)** ($19) includes:

- âœ… 6 specialized AGENTS.md templates (monorepo, microservices, data pipeline, CLI tool, library, full-stack app)
- âœ… Multi-agent coordination patterns (lead + specialist agents)
- âœ… Pre-built skill library for common workflows
- âœ… Git hooks for automated quality checks
- âœ… Session management strategies for long-running projects
- âœ… Cost optimization guide (reduce token usage 40-60%)

**[Get the full kit â†’](https://shellsage-ai.github.io/)**

## License

MIT
