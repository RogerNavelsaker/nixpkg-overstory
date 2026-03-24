---
name: overstory
description: Use overstory for multi-agent orchestration, worker coordination, and structured parallel execution.
---

# Overstory

Use this skill when the task benefits from multiple workers, worktree isolation, or explicit orchestration.

Preferred commands:

```bash
overstory --help
overstory status
overstory list
```

Rules:
- Use overstory when work should be split across workers.
- Keep worker scopes disjoint.
- Prefer structured coordination over ad hoc parallel shell sessions.
