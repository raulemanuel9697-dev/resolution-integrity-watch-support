# Privacy notice — Resolution Integrity Watch

**Status: public pre-launch notice for the current build.** The legal Marketplace seller identity and private privacy contact are **OWNER_INPUT_REQUIRED**. This notice describes the app's observed data handling; the seller must complete and verify its identity/contact details before Marketplace submission.

**Project publisher name:** Autonomous Revenue Portfolio (display name only; not a claim of incorporation).  
**Effective date:** 2026-09-26.  
**Private privacy contact:** OWNER_INPUT_REQUIRED.

## Data the app processes

The Forge app searches Jira issues available to it and reads only the fields used by the check: issue key, project key, issue type, status name and status category, and Resolution. Its bounded report also contains the check result, review explanation, severity, scan time, counts, and whether the scan reached its limit.

The app does not request or store issue summaries, descriptions, comments, attachments, changelog, reporter, assignee, email addresses, or user identity for this feature.

## Why the data is used

Those fields are used to identify possible mismatches between an issue's Done-category status and its Resolution, and to display an administrator-facing report. Results are review signals; a Jira workflow may intentionally use a different combination.

The app does not modify Jira issues or workflow configuration, send notifications, profile people, train an AI model, sell the report, or use the report for advertising.

## Storage, access, and retention

The latest bounded report and small scan-state markers are stored in Atlassian Forge Key-Value Store (KVS), under the app's `storage:app` permission. Jira reads use `read:jira-work`. The app keeps the current report rather than a history: a later successful scan replaces it. A failed scan records a safe error state and preserves the last successful report. The app has no product-level scheduled report-history purge.

The report is shown in the app's Jira administrator page. Jira access and the app's permissions are administered in the customer's Atlassian site. Atlassian operates the Forge and Jira platform services and applies its own platform data lifecycle and recovery rules. See [Forge storage](https://developer.atlassian.com/platform/forge/storage-reference/) and the [KVS API reference](https://developer.atlassian.com/platform/forge/storage-reference/kvs-api/).

## Disclosure and external services

The app declares no `external.fetch` destination and its reviewed source has no external egress or third-party telemetry. The issue fields and report are processed within Jira and Atlassian Forge. No app-owned backend is used.

The separate documentation site and support issue tracker are hosted on GitHub. GitHub processes visitor/account information under its [Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement). Public support issues can be visible to anyone; do not post issue keys, site URLs, customer information, or confidential content there.

## Choices and removal

The Jira site administrator chooses whether to install or uninstall the app. An administrator can start an on-demand scan with **Run now**; one daily scheduled scan is also configured. The app has no user-level profiling or notification preferences.

To remove the app, a Jira administrator can uninstall it from the site's app management screen. Forge platform app-data recovery and deletion follow Atlassian's current documentation and controls. For a privacy or deletion request, use the verified private publisher contact once it is published; that contact remains **OWNER_INPUT_REQUIRED**. Do not send personal data or private Jira content in a public GitHub issue.

## Accuracy and changes

The notice describes the reviewed development build. Production installation and runtime have not been verified, and this app has not been submitted to Marketplace. The publisher must update this notice if the app's data handling changes and complete the seller/contact fields before public listing.
