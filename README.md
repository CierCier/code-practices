# Code Practices

A set of focused, independently installable agent skills for writing and maintaining software without needless complexity. Each directory is a standalone skill. Install only the practices relevant to the task.

## Install

```sh
npx skills add CierCier/code-practices --skill code
bun x skills add CierCier/code-practices --skill code
```

Replace `code` with any skill below. To install several, repeat `--skill`:

```sh
npx skills add CierCier/code-practices --skill thinking --skill testing
bun x skills add CierCier/code-practices --skill architecture --skill code-review
```

`skills add` asks which agent and installation scope to use. Add `--global` for user-wide installation or `--agent <name>` to target an agent. The skills are not coupled to a particular coding agent.

## Skills

| Skill | Use it for |
| --- | --- |
| [`code`](code/SKILL.md) | Writing clear, idiomatic, maintainable code |
| [`thinking`](thinking/SKILL.md) | Scoping a change and choosing the smallest correct solution |
| [`architecture`](architecture/SKILL.md) | Module boundaries, APIs, state, and system design |
| [`testing`](testing/SKILL.md) | Choosing and writing behavior-focused tests |
| [`debugging`](debugging/SKILL.md) | Reproducing failures and tracing root causes |
| [`security`](security/SKILL.md) | Trust boundaries, authorization, secrets, and threat-driven review |
| [`performance`](performance/SKILL.md) | Measuring and improving real performance bottlenecks |
| [`concurrency`](concurrency/SKILL.md) | Shared state, synchronization, cancellation, and backpressure |
| [`dependencies`](dependencies/SKILL.md) | Selecting, pinning, auditing, and removing dependencies |
| [`git`](git/SKILL.md) | Focused commits, safe history operations, and clean diffs |
| [`code-review`](code-review/SKILL.md) | Evidence-based review for correctness and maintainability |
| [`documentation`](documentation/SKILL.md) | Keeping user and maintainer docs accurate and useful |
| [`tooling`](tooling/SKILL.md) | Useful automation, static checks, and reproducible development |
| [`delivery`](delivery/SKILL.md) | Shipping, rollout, rollback, and operational readiness |
| [`maintenance`](maintenance/SKILL.md) | Reducing accumulated complexity and keeping systems healthy |
| [`human`](human/SKILL.md) | Collaborating respectfully and leaving code understandable |

## Design rule

Prefer a change that demonstrably improves correctness, security, ease of understanding, testing, modification, debugging, or operation. Do not add abstraction, ceremony, dependencies, tests, or process without a concrete benefit.
