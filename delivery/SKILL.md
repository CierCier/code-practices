---
name: delivery
description: Prepare application changes for release, deployment, rollout, or operational handoff. Use when a change can affect production behavior, users, or persisted data.
---

# Delivery

- Identify what changes for users and operators, what state is affected, and what failure looks like.
- Keep changes deployable. Separate deployment from release when rollout needs to be gradual; use a feature flag only when staged control has a concrete purpose.
- Plan migration order, compatibility window, rollback, and data recovery for stateful or irreversible changes. Do not promise rollback if data transformations make it impossible.
- Make retries and repeated deploy steps safe where the platform can rerun them. Avoid duplicate side effects on partial failure.
- Verify configuration, secrets, permissions, and environment-specific assumptions without exposing credentials.
- Ensure logs, alerts, and metrics expose actionable failures for new critical paths. Avoid adding telemetry that has no operational consumer.
- Run the relevant pre-release checks and exercise the changed behavior in a representative runtime. State any important environment or integration not tested.
- Document the release procedure and recovery steps where the operator cannot safely infer them.

Before release, answer: how do we know it worked, how do we notice failure, and how do we restore service or data? Keep the procedure proportional to impact.