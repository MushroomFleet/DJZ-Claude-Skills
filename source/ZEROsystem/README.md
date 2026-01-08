# Zero-Agency Skill

**Version:** 1.0  
**License:** MIT  
**Based on:** ZERO System Prompt v3.0

---

## Overview

Zero-Agency is a consequence-aware agency framework for Claude Code that prevents reckless planning and actions. It provides a "pancake-thin" safety layer that activates before any consequential action.

---

## Package Contents

This `.skill` file is a self-contained zip archive with **no external dependencies**.

```
zero-agency.skill
└── zero-agency/
    ├── SKILL.md                    (2.6 KB)  — Core skill, always loaded
    └── references/
        └── ZERO-FULL.md            (30 KB)   — Complete framework, loaded on demand
```

| File | Purpose | Token Cost | When Loaded |
|------|---------|------------|-------------|
| `SKILL.md` | Core invocation + quick checks | ~400 tokens | When skill triggers |
| `references/ZERO-FULL.md` | Complete ZERO v3.0 framework | ~4000 tokens | Only when needed for complex situations |

**All references are internal.** The path `references/ZERO-FULL.md` resolves relative to the skill's installation directory—no network fetch, no external files required.

---

## Installation

### Claude Code

```bash
# Install the skill
claude skill install zero-agency.skill
```

Or manually extract to your skills directory.

---

## What It Does

### Triggers On
- File operations (create, modify, delete)
- Code execution
- API calls
- Database modifications
- Multi-step autonomous workflows
- Any action that modifies state or has downstream effects

### Core Behavior

Before consequential actions, the skill prompts internalization of:

```
I am not optimizing for task completion.
I am optimizing for outcomes the user would endorse.
Victory achieved through blindness to consequences is not victory.
```

### Pre-Action Check

Five-point fast verification:
1. **Intent** — Does this match what user actually wants?
2. **Consequences** — What could go wrong?
3. **Affected** — Who/what is impacted beyond the user?
4. **Reversibility** — Can this be undone?
5. **Confidence** — How certain am I?

### Graduated Autonomy

| Action Type | Behavior |
|-------------|----------|
| Read-only, reversible | Proceed |
| Destructive, security-relevant, production | Confirm first |
| Violates safety, harms third parties, bypasses checks | Never execute |

---

## Design Philosophy

### "Pancake-Thin Agency"

Minimal overhead, maximum effect. This is not a comprehensive safety system—it's a cognitive checkpoint that activates before consequential actions.

### Progressive Disclosure

- **Routine tasks**: Load only SKILL.md (~400 tokens)
- **Complex ethical situations**: Reference ZERO-FULL.md (~4000 tokens)

This respects the principle that the context window is a shared resource.

---

## Full Framework

The complete ZERO System v3.0 framework is included in `references/ZERO-FULL.md` and provides:

- 10-level value hierarchy with explicit ordering
- Detailed intent divergence protocol
- Comprehensive adversarial robustness patterns
- Multi-agent interaction governance
- Prompt integrity protections
- Escalation protocols
- Confidence calibration guidelines
- Full failure mode taxonomy

The minimal skill references this automatically when situations exceed the core framework's coverage.

---

## License

MIT License — Free to use, modify, and distribute with attribution.

```
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-08 | Initial release based on ZERO System v3.0 |

---

## Related Documents

- **ZERO System v3.0** — Full framework specification (embedded in `references/ZERO-FULL.md`)
- **Red Team Protocol** — Adversarial testing methodology for ZERO
- **Improvement Plan** — Roadmap for future ZERO development

---

*The goal is not to complete tasks. The goal is to help.*
