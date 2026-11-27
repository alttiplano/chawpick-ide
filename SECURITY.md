# Security Policy

Thanks for helping keep Chawpick IDE secure. At Alttiplano we take security very seriously, and we
appreciate everyone who finds issues and reports them responsibly.

## ``Important``

**We do not accept automated scanner dumps or unverified AI-generated reports.** We receive many
made-up or unproven reports, and we don't have the resources to review them all.

- A report without a reproducible proof of concept (PoC) that shows real impact may be closed
  without further review.
- Repeated spam may lead to a ban across the whole Alttiplano organization.

You can use AI to help with your research, as long as a person has verified the finding and the
report includes a working PoC.

## Supported versions

Only the **latest release** and the `main` branch receive security fixes. If you're on an older
version, please upgrade.

## Threat model

Chawpick IDE runs on your machine, with your permissions. It reads and edits the files you open,
and only runs what you ask it to. Opening a stranger's project has to be safe.

### What counts as a security issue

- Opening a file or folder runs code without you asking.
- The app reads, writes or deletes files outside what you opened, without you asking.
- Someone gets the app to download or install something Alttiplano didn't publish.
- Your data (files, paths, keys) leaves your machine without your permission.

### Out of scope

| Category | Reason |
|---|---|
| **What you run** | Commands, scripts or builds you start on purpose do what they say |
| **Third-party dependencies** | Report it to the original project, unless it can be exploited through Chawpick IDE |
| **Huge or malformed files** | If they only slow the app down or close it, that's a normal bug: open an [issue](https://github.com/alttiplano/chawpick-ide/issues/new) |
| **Missing best practices** | Missing settings that don't lead to an exploitable issue |
| **Already-compromised machine** | Someone who already controls your machine can do the same without Chawpick IDE |

## How to report

**Don't make the issue public** in issues, PRs, Discord or social media until we have reviewed and
fixed it.

Report it privately through
[Report a vulnerability](https://github.com/alttiplano/chawpick-ide/security/advisories/new). The
form asks for a summary, details, a proof of concept and the impact. Please also add:

- Your Chawpick IDE version (or commit) and operating system.
- The affected files or functions, if you know them.
- A possible fix, if you have one.

Remove passwords, personal paths and any private data from logs. We don't offer a bug bounty.

## Disclosure

We follow coordinated disclosure:

1. We reply to your report within **5 business days**.
2. We aim to publish a fix within **90 days**.
3. When we publish it, we create a GitHub security advisory that credits you, unless you prefer to
   stay anonymous.

If you haven't heard back within 5 business days, or you can't use the form, email
**[security@alttiplano.com](mailto:security@alttiplano.com)**.

---

<sub>Maintained by [Alttiplano](https://alttiplano.com).</sub>
