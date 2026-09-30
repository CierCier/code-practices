---
name: dependencies
description: Add, upgrade, pin, audit, or remove packages, libraries, frameworks, or external tools. Use to keep dependency choices justified, reproducible, and low-risk.
---

# Dependencies

Before changing the dependency graph:

- Check whether the project already provides the needed capability. Prefer a small local implementation only when it is simpler and safer than an external dependency.
- Identify the concrete requirement, supported runtime/platforms, license, maintenance status, transitive footprint, and security exposure.
- Compare the smallest suitable options. Do not pull a large framework for a small utility or add overlapping libraries without a demonstrated need.
- Use the project's package manager and conventions. Update the lockfile and manifest together; preserve reproducible resolution.
- Pin exact versions only where the project needs repeatable builds or controlled deployments. Otherwise follow the ecosystem's established update policy.
- Audit the package source, install scripts, permissions, and transitive dependencies proportional to risk.
- Remove packages that became unused after a migration. Confirm no remaining imports or build/runtime configuration relies on them.
- Verify a real use of the package plus the relevant build or test path. Review the resulting lockfile diff for unexpected churn.

Record why the dependency is worth its ongoing upgrade, audit, and supply-chain cost. If the benefit is marginal, do not add it.