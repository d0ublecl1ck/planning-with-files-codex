# Planning with Files

> Use persistent markdown files as working memory for long, multi-step Codex tasks.

A Codex skill that transforms your workflow to use persistent markdown files for planning, progress tracking, and knowledge storage.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Codex Skill](https://img.shields.io/badge/Codex-Skill-blue)](https://openai.com)

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=OthmanAdi/planning-with-files&type=Date)](https://star-history.com/#OthmanAdi/planning-with-files&Date)

---

## Why This Skill?

Complex tasks are often long and iterative. This skill provides a simple, repeatable workflow that keeps goals, progress, and findings on disk so they can be re-read at any time.

## The Problem

Codex (and most AI agents) suffer from:

- **Volatile memory** — In-chat notes disappear on context reset
- **Goal drift** — After 50+ tool calls, original goals get forgotten
- **Hidden errors** — Failures aren't tracked, so the same mistakes repeat
- **Context stuffing** — Everything crammed into context instead of stored

## The Solution: 3-File Pattern

For every complex task, create THREE files (and make sure they are ignored by git):

```
task_plan.md      → Track phases and progress
notes.md          → Store research and findings
[deliverable].md  → Final output
```

### The Loop

```
1. Create task_plan.md with goal and phases
2. Research → save to notes.md → update task_plan.md
3. Read notes.md → create deliverable → update task_plan.md
4. Deliver final output
```

**Key insight:** By reading `task_plan.md` before each decision, goals stay in the attention window.

## Installation

### Option 1: Clone directly (Recommended)

```bash
# Navigate to your Codex skills directory
cd ~/.codex/skills  # or your custom skills path

# Clone this skill
git clone https://github.com/d0ublecl1ck/planning-with-files-codex.git
```

### Option 2: Manual installation

1. Download or copy the `planning-with-files` folder
2. Place it in your Codex skills directory:
   - macOS/Linux: `~/.codex/skills/`
   - Windows: `%USERPROFILE%\.codex\skills\`

### Verify Installation

In Codex, the skill will automatically activate when you:
- Start complex tasks
- Mention "planning", "organize", or "track progress"
- Ask for structured work

## Usage

Once installed, Codex will automatically:

1. **Ensure `.gitignore` ignores planning files** (`task_plan.md`, `notes.md`, `[deliverable].md`)
1. **Create `task_plan.md`** before starting complex tasks
2. **Update progress** with checkboxes after each phase
3. **Store findings** in `notes.md` instead of stuffing context
4. **Log errors** for future reference
5. **Re-read plan** before major decisions

### Example

**You:** "Research the benefits of TypeScript and write a summary"

**Codex creates:**

```markdown
# Task Plan: TypeScript Benefits Research

## Goal
Create a research summary on TypeScript benefits.

## Phases
- [x] Phase 1: Create plan ✓
- [ ] Phase 2: Research and gather sources (CURRENT)
- [ ] Phase 3: Synthesize findings
- [ ] Phase 4: Deliver summary

## Status
**Currently in Phase 2** - Searching for sources
```

Then continues through each phase, updating the file as it goes.

## The Principles

This skill implements these key context engineering principles:

| Principle | Implementation |
|-----------|----------------|
| Filesystem as memory | Store in files, not context |
| Attention manipulation | Re-read plan before decisions |
| Error persistence | Log failures in plan file |
| Goal tracking | Checkboxes show progress |
| Append-only context | Never modify history |

## File Structure

```
planning-with-files/
├── SKILL.md        # Core instructions (what Codex reads)
├── reference.md    # Context engineering deep dive
├── examples.md     # Real usage examples
└── README.md       # This file
```

## When to Use

**Use this pattern for:**
- Multi-step tasks (3+ steps)
- Research tasks
- Building/creating projects
- Tasks spanning many tool calls
- Anything requiring organization

**Skip for:**
- Simple questions
- Single-file edits
- Quick lookups

## Acknowledgments

- Inspired by general context engineering patterns for long-running tasks.

## Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## License

MIT License — feel free to use, modify, and distribute.

## Thank You

To everyone who starred, forked, and shared this skill — thank you. This project blew up in less than 24 hours, and the support from the community has been incredible.

If this skill helps you work smarter, that's all I wanted.

---

**Author:** [Ahmad Othman Ammar Adi](https://github.com/OthmanAdi)
