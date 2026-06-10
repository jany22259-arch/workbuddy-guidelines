# WorkBuddy Guidelines

> AI coding behavioral guidelines for LLM agents. Inspired by [Andrej Karpathy](https://github.com/karpathy)'s LLM coding philosophy.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

---

## The Problems

As Andrej Karpathy observed, LLM coding agents share common failure patterns:

- **Silent assumptions** — the agent assumes instead of asking, hides confusion, presents no tradeoffs
- **Over-engineering** — bloated abstractions, dead code left behind, 100-line problems get 1000-line solutions
- **Side-effect edits** — changes or deletes code it doesn't understand, irrelevant "improvements" creep in
- **No verification loop** — builds something and calls it done without testing, no measurable success criteria

These problems compound in **Chinese-language development environments**: encoding issues, Windows path quirks, and tools that don't play well with CJK characters.

---

## The Solution

One file with **6 principles** that directly counter each failure pattern:

| Principle | Counters |
|-----------|----------|
| **Think Before Coding** | Silent assumptions, hidden confusion, missing tradeoffs |
| **Simplicity First** | Over-engineering, bloated abstractions, dead code |
| **Surgical Changes** | Irrelevant edits, touching code that isn't yours |
| **Goal-Driven Execution** | No verification, "done" without testing |
| **Security** | Credential leaks, irreversible file operations |
| **Delivery** | Encoding chaos, non-standard output, repeated mistakes |

---

## What We Added

Andrej Karpathy's original guidelines focus on four coding principles. We built on that foundation:

| Addition | Description |
|----------|-------------|
| **Principle 5: Security** | No hardcoded credentials, backup-before-edit, confirm before touching personal dirs — from real-world production experience |
| **Principle 6: Delivery** | Markdown default, UTF-8 encoding, Chinese environment workarounds (`/` for paths, avoid GBK, use Python not PowerShell) |
| **Native Chinese support** | Full localization, not machine-translated — ready to paste into any Chinese-language agent setup |

TL;DR: The original covers "how to code." We added "how to code safely" and "how to code in Chinese environments."

---

## Files

| File | Language | Purpose |
|------|----------|---------|
| [`GUIDELINES.md`](./GUIDELINES.md) | EN | The 6 rules — copy into your agent's system prompt |
| [`GUIDELINES.zh.md`](./GUIDELINES.zh.md) | 中文 | Same rules, native Chinese — copy into your agent's system prompt |

---

## Install

### For WorkBuddy

Copy the guidelines into your WorkBuddy custom instructions:

```
1. Open WorkBuddy → click user avatar → Settings → Personalization → Custom Instructions
2. Paste the content of GUIDELINES.md or GUIDELINES.zh.md
3. Save. Done.
```

### For Other Agents (Claude, Cursor, Copilot, etc.)

Same thing — paste the guidelines into whatever "system prompt" or "rules" mechanism your tool provides.

---

## Key Insight

> *"LLMs are remarkably good at looping until a specific goal is met... Don't tell it what to do. Give it success criteria and let it run."*
> — Andrej Karpathy

This is the foundation of Principle 4 (Goal-Driven Execution). The agent doesn't need step-by-step instructions — it needs a clear, verifiable finish line.

---

## How to Know It's Working

- Diffs are minimal — only the lines that matter changed
- No rewrites from over-engineering
- Clarifying questions come **before** implementation
- PRs are clean, focused, easy to review

---

## Tradeoff Note

These guidelines bias toward **caution over speed**. For trivial tasks (spelling fixes, obvious one-liners), use your judgment and skip the full workflow. The goal is fewer costly mistakes on non-trivial work — not bureaucracy.

---

## License

MIT — see [LICENSE](./LICENSE).
