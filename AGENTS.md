# Agent Instructions

Keep this project as agent-agnostic as possible.

## Rule: Context Maintenance

At the end of every significant task or session, summarize the current state, architectural decisions made, and pending "todo" items into AGENTS.md. Always ensure this file reflects the "ground truth" of the project so future sessions can resume without friction. Use the writeFile tool to overwrite it so the next session starts with current state.
Regularly check the `rwxrob/agentic-ai-template` repo's AGENTS.md and ensure any updated rules have been merged into this file.

## Rule: Commits

- Always fetch latest before beginning any new work
- Always use conventional commits (e.g. `feat:`, `fix:`, `docs:`, `chore:`)
- Never add anything agent related (copilot, claude, etc.) to commit messages or co-authorship
- Committing directly to main is okay in this repo
- When starting work on a new issue, always check if the latest commit on main has been tagged; if not, warn the user before proceeding

## Rule: Environment

- Use `/usr/bin/open` (full path) to open files or URLs on macOS — never plain `open`
- Always pipe URLs or other text to be pasted into `pbcopy` when suggesting them
- Use Obsidian as the default application to open all markdown files (e.g., `/usr/bin/open -a Obsidian <file.md>`)

## Rule: Secrets

- Never commit secrets, config files, or database files

## Rule: Writing tone

- Avoid hyperbolic and superlative language; state facts plainly
- Reference current events and concrete examples whenever possible

## Rule: Code style

- Single-line paragraphs in all markdown files — no multi-line wrapped paragraphs
- Always use sentence case for titles
- Always use `—-` for horizontal rules in markdown (not `—`) to avoid em-dash creation by pandoc and similar tools
- No underscores or spaces in filenames; use hyphens
- No extensions on executable scripts, ever
- Run `gofmt` on all Go source files every time any change is made to Go source code
- Put all Go packages under `internal/` unless otherwise requested, to prevent external dependencies
- Prefer `go install` over `go build`
- Always use an OAuth-enabled HTTP client in Go
- Never enable CGO when compiling Go code no matter what
- Always recover from panics in Go; no program should ever terminate due to an unhandled panic
- In Go `bonzai.Cmd` structs, always put `Long` last so code is easier to read
- In `Cmd.Long`, indent sample/example content by 4 spaces so it renders as verbatim (preformatted) text, not markdown
- In `Cmd.Long`, use single-line paragraphs so text wraps correctly on windows of different dimensions
- `Cmd.Short` must always be less than 50 runes
- Always add `help.Cmd` as the first bonzai subcommand
- Always default to command completion for any Bonzai command

## Rule: Containers

- Never refer to Docker specifically; always refer to OCI-compliant containers

- Always enable branch protection on `main` when creating a new GitHub repo so a PR is always required
- Exception: repos beginning with `notes-` are knowledge repos, not source code — commit directly to main with no branch protection and no PRs required
- Require zero reviews (PRs required but no approvals needed)
- Enable automatic branch deletion after a PR is merged
- After merging a PR, pull the latest changes into the current branch and delete any leftover worktrees

## Rule: Agent specific

- Always use `gh copilot` not `copilot`
- Use Claude Opus 4.6 (high) for all new projects

## Current architecture

TODO

## Current tags / versions

TODO

