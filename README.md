# Resolution Integrity Watch

**A read-only review signal for Jira status and Resolution mismatches.**

Resolution Integrity Watch checks Jira issues visible to the app for a disagreement between the issue's status category and its Resolution. It keeps the latest successful report in Forge so a Jira administrator can review possible workflow inconsistencies without running a manual JQL check each time.

> **Pre-launch publisher notice:** this is product documentation for the current development build. The app has not been submitted to Atlassian Marketplace. The Marketplace seller identity and private privacy contact are still being verified, and production installation and licensing behavior have not been tested. Do not treat this page as an offer for sale.

## Publisher

**Autonomous Revenue Portfolio** is the project display name used for this app. It is not a claim that a company or other legal entity has been incorporated. The legal seller identity is **OWNER_INPUT_REQUIRED** and will be added after Atlassian seller verification.

## What the app does

- Runs one scheduled review per day and supports an administrator-triggered **Run now** scan.
- Compares status category with Resolution and reports possible mismatches for human review.
- Stores the latest bounded report and scan metadata in Atlassian Forge storage.
- Leaves Jira issues and workflows unchanged.
- Uses no external data-transfer destination, AI service, analytics provider, or notification service.

The rule is a review signal, not a universal definition of a correct Jira workflow. Teams may intentionally use different status and Resolution conventions. The scan is limited to 500 issues, and findings require workflow-aware review.

## Public documentation

- [Privacy notice](privacy.md)
- [Data handling](data-handling.md)
- [Support, FAQ, and installation help](support.md)
- [Contact](contact.md)
- [Security](security.md)
- [Product boundaries](disclaimer.md)
- [End-user terms status](terms.md)

## Contact and support

Use the [public support issue form](https://github.com/raulemanuel9697-dev/resolution-integrity-watch-support/issues/new/choose) for non-sensitive questions. Issues are public. **Do not include Jira issue keys, site URLs, customer data, passwords, API tokens, or other confidential information.** A private publisher privacy contact is **OWNER_INPUT_REQUIRED** before Marketplace submission.

## Release status

The reviewed Forge source is deployed to development, staging, and production. Only development is installed and validated. The app is not publicly listed, and its production licensing/runtime path remains unverified. No customer usage, production scan, or commercial performance claim is made here.

## Hosting and visitor privacy

These documentation pages and the issue tracker are hosted by GitHub. GitHub may process visitor and account data under its own [Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement). The Jira app's separate data practices are described in the [privacy notice](privacy.md).
