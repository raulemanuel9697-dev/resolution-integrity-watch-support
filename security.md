# Security

## Current implementation

- Jira permissions: `read:jira-work` and `storage:app` only.
- No Jira write scope or issue/workflow write route.
- No `external.fetch` allowlist, remote service, or third-party telemetry.
- Stored report is bounded to 500 issues and contains the minimum fields used for the check.
- Logs use aggregate scan counts, timing, size, and safe error codes rather than issue keys or issue content.

The reviewed development source passed the recorded tests, lint, Forge lint, dependency audit, and source review. This is not an independent penetration test or a production security certification.

## Scope of current evidence

Development is installed and validated. The same source is deployed to staging and production, but neither environment is installed on a Jira site. Production runtime, production licensing, and customer configuration have not been tested. The app has not been submitted to Marketplace.

## Reporting a security concern

Do not put vulnerability details, tokens, private Jira data, or exploit steps in a public issue. A verified private security contact is **OWNER_INPUT_REQUIRED** and must be configured before Marketplace submission. Until then, do not transmit sensitive security information through the public issue tracker.
