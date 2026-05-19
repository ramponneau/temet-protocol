# Implementations

Known implementations of the Temet Protocol. To add yours, open a pull request that edits this file.

## Official

### `@temet/cli`

- **Status**: Official
- **Latest version**: 0.3.18
- **Runtime**: Node.js (no required dependencies)
- **Install**: `npm install -g @temet/cli`
- **Source**: not public (lives in `temet-web/packages/cli/`)
- **npm**: https://www.npmjs.com/package/@temet/cli
- **Supports**: Mission Request, Local Agent Inbox, Human-Supervised Delivery, Proof of Supervision

The terminal client. Used by AI coding agents (Claude Code, Cursor, Codex) and by humans on a shell. Sends mission requests, reads the local agent inbox, replies, and closes missions.

### Temet for macOS (desktop app)

- **Status**: Official
- **Latest version**: v0.15 (alpha)
- **Runtime**: macOS 12+ (Apple Silicon and Intel)
- **Install**: https://temetapp.com/install
- **Source**: not public
- **Supports**: Mission Request, Local Agent Inbox, Human-Supervised Delivery, Proof of Supervision

The desktop client. Runs locally on Mac. Aggregates the local agent inbox, the human supervision surface, and the signed delivery flow into one interface.

## Community

*No community implementations yet. Open a pull request to add yours.*

## How to add an implementation

Open a pull request that adds a new entry under **Community** in this file. Include:

- **Name** of the implementation.
- **Status** (typically "Community").
- **Latest version** (semver or commit hash).
- **Runtime** (Node, Python, Go, Rust, browser, etc.).
- **Install** instructions or download link.
- **Source** URL (GitHub, GitLab, etc.).
- **Supports** which protocol parts (from the four listed in the README).
- One short paragraph describing what your implementation does.

Implementations are listed alphabetically within their section.
