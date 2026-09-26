# Support and help

## Contact

For non-sensitive product questions, open a [support issue](https://github.com/raulemanuel9697-dev/resolution-integrity-watch-support/issues/new/choose). The issue tracker is public. Do not include Jira issue keys, site URLs, customer data, credentials, tokens, screenshots with customer information, or confidential issue content.

**Response expectation:** the maintainer intends to review requests on business days and aims to acknowledge them within five business days when capacity permits. This is a target, not a guaranteed service level. There is no 24/7 support commitment. A private email/support contact for privacy and seller matters is **OWNER_INPUT_REQUIRED** before Marketplace submission.

## What to include

The support template asks for the app version, safe error code, approximate UTC time, whether the problem occurred on **Run now** or the daily scan, and a short description that contains no customer or issue data. Never send passwords, API tokens, raw issue exports, or private Jira content through GitHub issues.

## Installation help

1. A Jira administrator installs the app from the relevant Atlassian Marketplace listing or approved app-management flow.
2. Open **Settings → Apps → Resolution Integrity Watch**.
3. Review the latest report, or use **Run now** to request a fresh scan.
4. Check the displayed scan time and truncated-scan notice before interpreting the result.

There is no public Marketplace listing yet. Production installation and paid-license behavior remain unverified.

## FAQ

### Does the app repair issues?

No. It only reads Jira data for the check and stores its own bounded report in Forge. It does not change issues or workflows.

### Is each finding definitely a workflow defect?

No. A finding is a review signal. Teams can intentionally use a Done status without Resolution or retain Resolution after reopening. Review local workflow intent before changing anything.

### What does the daily scan cover?

The app schedules one scan per day and supports an administrator-triggered **Run now**. Each scan is limited to 500 issues and reports when that limit is reached.

### Why does a failed scan still show an older report?

The app preserves the latest successful report after a later run fails. Check the current error code and timestamp, then retry later or wait for the next scheduled run.

### What data does the app store?

It keeps the current report, containing issue key, project, issue type, status/category, Resolution, review details, and scan metadata, plus a few scan-state markers. It does not store issue descriptions, comments, attachments, or user identity. See [Data handling](data-handling.md) and the [privacy notice](privacy.md).

## Troubleshooting

- **No report yet:** use **Run now** as a Jira administrator, then refresh after the scan completes.
- **`access_denied`:** ask the Jira site administrator to confirm installation and app access.
- **`rate_limited` or `jira_unavailable`:** the previous successful report is preserved; retry later or wait for the next daily run.
- **Scan truncated:** the app inspected up to 500 issues. Review the displayed limit and issue visibility.
- **A finding looks intentional:** inspect the issue and the project's workflow rules before taking action.
- **License or install issue:** confirm the app's Marketplace evaluation/license on the relevant site. Production licensing has not yet been tested for this app.

## Uninstall

A Jira administrator can remove the app from the site's app management settings. Atlassian's Forge data recovery and deletion behavior after uninstall applies; the app does not maintain a separate historical report archive. See the [Forge storage reference](https://developer.atlassian.com/platform/forge/storage-reference/).

## Known limitations

- Findings are workflow-dependent review signals, not definitive defect labels.
- The maximum scan is 500 issues; larger populations are reported as truncated.
- One sequential duplicate scheduled delivery was verified as idempotent. Concurrent scheduled deliveries may still make duplicate read-only requests.
- Live retry-failure injection and an empty Jira project were not tested.
- The 13 true positives, 0 false positives, 12 ambiguous findings, and 15 true negatives are a bounded manual development-site sample, not a random estimate or global recall claim.
- Narrow mobile, automated contrast measurement, full screen-reader testing, production runtime, and production licensing remain unverified.

## Security reports

Do not post suspected vulnerabilities or exploit details in a public issue. A private security reporting route is **OWNER_INPUT_REQUIRED**; configure it before Marketplace submission.
