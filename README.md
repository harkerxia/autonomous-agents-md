# autonomous-agents-md

A single `AGENTS.md` for AI-native development: coding agents that work autonomously, but cautiously.

English | [简体中文](./README.zh.md)

Based on [andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills), which turns [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) on LLM coding pitfalls into four principles. This version keeps those principles and adapts them for agents that run with less human supervision.

## What's different from the original

The original `CLAUDE.md` assumes a human is at hand to answer questions: when in doubt, the agent stops and asks. This version assumes the agent should keep moving, and stops only when a wrong guess would be costly.

| Area | Original `CLAUDE.md` | This `AGENTS.md` |
|---|---|---|
| Uncertainty | If uncertain, stop and ask | Risk-based: make reversible assumptions on low-risk ambiguity; ask only when interpretations differ materially |
| Refactoring | Don't refactor what isn't broken | Don't refactor unrelated code; refactor when the task requires it |
| Unrelated problems | Mention dead code | Mention dead code, bugs and exposed secrets; don't fix them unasked |
| Others' work | Not covered | Preserve user and agent changes; never discard others' work without permission |
| Tests | Loop until verified | Also: never weaken tests to pass; stop and report when stuck |
| Risky actions | Not covered | Autonomous by default; ask before high-risk or irreversible actions |
| Secrets | Not covered | Never hardcode, commit or output secrets |
| Continuity | Not covered | Progress file for multi-session work; separate files for parallel work |
| Precedence | "Merge as needed" | Project-specific instructions take precedence |

Section 2 (Simplicity First) and the core of sections 3 and 4 are unchanged.

## Usage

Put `AGENTS.md` in your project root. Codex, Cursor and most other coding agents read it directly. Claude Code (v2.1.277+) reads `AGENTS.md` when the project has no `CLAUDE.md`; if you do have a `CLAUDE.md`, add a line `@AGENTS.md` to it.

Project-specific rules take precedence, so you can adjust the defaults by adding a section at the end. For example, for a hackathon demo:

```markdown
## Project

- Hackathon demo: favor speed over caution; verify by running the app; write tests only for core logic.
```

## Files

- `AGENTS.md`: the guidelines
- `AGENTS.zh.md`: Chinese translation, for reference only

## Credits

- [andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills) by forrestchang, the original guidelines (MIT)
- [Andrej Karpathy](https://x.com/karpathy/status/2015883857489522876), the observations behind them

## License

[MIT](./LICENSE)
