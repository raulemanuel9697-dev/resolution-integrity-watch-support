# Data handling

## Data inventory

| Data | Source | Purpose | Stored in the app |
|---|---|---|---|
| Issue key | Jira search | Link to an issue and identify a finding | Yes, in the latest report |
| Project key | Jira | Show project context | Yes, in the latest report |
| Issue type | Jira | Show issue context | Yes, in the latest report |
| Status name and category | Jira | Compare workflow state with Resolution | Yes, in the latest report |
| Resolution name or Unresolved | Jira | Compare resolution state | Yes, in the latest report |
| Scan time, counts, truncation state, and safe result metadata | Forge runtime | Show report freshness and scan outcome | Yes, in the latest report and small state markers |
| Daily success marker | Forge runtime | Avoid a second scheduled scan on the same UTC day | One current value |
| Safe error code and timestamp | Forge runtime | Indicate a failed run while preserving the last successful report | One current value; cleared after success |
| Aggregate runtime counters | Forge runtime | Diagnose execution health | Aggregate logs; no issue keys or issue content |

The scan is bounded to 500 issues. The measured live report for 101 findings was 38,372 bytes; a maximum-size local fixture measured 206,926 bytes. These are build-time observations, not guarantees for future schemas.

## Not collected by the app

The reviewed code does not request or store issue summaries, descriptions, comments, attachments, changelog, reporter/assignee, email addresses, or user identities. It does not keep prior report history.

## Processing boundary

Jira reads use Atlassian Forge's Jira API. App-owned values use Forge KVS. The manifest contains only `read:jira-work` and `storage:app`; it has no external fetch destinations. There is no separate app server, analytics vendor, AI provider, or email provider.

This describes the app's configured calls. Atlassian operates the underlying Jira and Forge services and may process technical information under its own platform terms and privacy notices.

## Lifecycle

- A successful scan replaces the previous successful report.
- A failed scan records a safe error code/time and preserves the previous successful report.
- A successful scan clears the previous error state.
- The app does not retain a product-level history or run a purge schedule.
- Uninstall and platform recovery/deletion behavior follow Atlassian's current [Forge storage documentation](https://developer.atlassian.com/platform/forge/storage-reference/).

## Operational measurements

For the development build, source-level counts for a successful scheduled scan are five KVS reads and three writes. The Jira administrator dashboard reads two KVS values; **Run now** reads three and writes three. A sequential duplicate scheduled run exits without another Jira scan. A live development scan of 101 issues made two Jira search requests and completed in 1,876 ms. These are development observations and source-derived call counts, not production metering or a bill.
