# renovate-config

Fleet-wide [Renovate](https://docs.renovatebot.com/) policy for 1REALTOUR (and the josephasmith1 account, whose `renovate-config` repo inherits this one).

- `default.json` — the shared preset (`github>1REALTOUR/renovate-config`).
- `org-inherited-config.json` — picked up automatically by the Mend Renovate app for every repo in the org ([Inherited config](https://docs.renovatebot.com/config-overview/#inherited-config)). No onboarding PRs; repos without a `renovate.json` use the preset as is.

Policy: one batched "weekly updates" PR per repo (Monday before 6am PT), 3-day release age, security fixes immediately. Majors, runtime lines (python/node/php/...) and 0.x minors wait for a tick on the repo's Dependency Dashboard issue.

A repo that needs more (e.g. automerge) keeps a `renovate.json` that starts with `"extends": ["github>1REALTOUR/renovate-config"]`.

Change the policy here, validate with `npx --package renovate -- renovate-config-validator default.json org-inherited-config.json`, and merge.
