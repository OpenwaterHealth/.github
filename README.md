# `.github` — Openwater organization defaults

This repository holds the **organization-wide health files, templates, and policy stubs** for
[github.com/OpenwaterHealth](https://github.com/OpenwaterHealth). GitHub automatically applies the
files here to **every repository in the org** that does not provide its own copy, so this repo is the
single place to maintain contribution rules, security policy, and issue/PR templates.

It is the first repo stood up under the *Openwater Licensing Architecture* (June 24, 2026) because
everything here propagates downstream — the other program repos (`license-manifest`, `openwater-spec`,
`openwater-conformance`, `openwater-certification`, `openwater-certified-deployments`) inherit these
defaults.

## What's in here

| Path | Applies to | Purpose |
|------|------------|---------|
| `CONTRIBUTING.md` | All repos | How to contribute; licensing/DCO expectations |
| `CODE_OF_CONDUCT.md` | All repos | Contributor Covenant 2.1 |
| `SECURITY.md` | All repos | Coordinated vulnerability disclosure |
| `SUPPORT.md` | All repos | Where to get help |
| `TRADEMARK.md` | All repos | **Policy stub** — "Openwater-Certified" vs. reserved "Openwater" (counsel review required) |
| `PULL_REQUEST_TEMPLATE.md` | All repos | Default PR checklist |
| `CODEOWNERS` | This repo | Review routing (replace with real teams) |
| `.github/ISSUE_TEMPLATE/` | All repos | Bug, feature, license-question, certification-application forms |
| `labels.yml` | Applied per-repo | Canonical org label set |
| `rulesets/require-pr-no-force-push.json` | Org ruleset | Enforce PR-only + no force-push org-wide |
| `snippets/profile-license-section.md` | Org **profile** README | **Paste-in** license section — the org profile README is NOT replaced |
| `scripts/` | Optional (CLI) | Command-line helpers; the browser guide does not use them |

## The org profile README is intentionally NOT included

The community-facing org profile (`profile/README.md`, shown on
[github.com/OpenwaterHealth](https://github.com/OpenwaterHealth)) is Openwater's front door and must
not be overwritten. This scaffold does **not** ship a profile README. Instead,
`snippets/profile-license-section.md` is a small section to **add** to the existing profile README.

## Setup

See **[SETUP.md](SETUP.md)** — step-by-step browser instructions, no terminal required.

## License of content in this repo

Docs/templates: **CC-BY-4.0**; scripts: **Apache-2.0**. See [LICENSE](LICENSE). This does not change
the license of any other repository — canonical assignments live in
[`OpenwaterHealth/license-manifest`](https://github.com/OpenwaterHealth/license-manifest).
