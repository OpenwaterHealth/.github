# Contributing to Openwater

Thanks for your interest in contributing. These guidelines apply org-wide unless a repository
overrides them.

## Before you start: understand the licensing layers

Openwater uses a deliberate two-layer license architecture. **Which layer your change touches
determines the license of your contribution.**

- **AGPL-3.0 core (permanent):** device firmware, sensing/measurement algorithms, beamforming,
  reconstruction, signal processing, calibration core, and hardware reference designs. Contributions
  to these are AGPL-3.0. The core boundary does not move without explicit board approval.
- **Apache-2.0 extensions:** 3D Slicer extensions, wellness/veterinary modules, partner SDKs, and
  language bindings. Contributions to these are Apache-2.0.

The authoritative, per-path assignment is in
[`license-manifest`](https://github.com/OpenwaterHealth/license-manifest). If you are unsure which
license applies to the file you're changing, **open a License question issue before you invest work.**

## Developer Certificate of Origin (DCO)

All commits must be signed off under the [DCO](https://developercertificate.org/). Add a
`Signed-off-by` line to each commit:

```
git commit -s -m "your message"
```

By signing off you certify that you wrote the contribution or otherwise have the right to submit it
under the license of the file(s) you changed. Contributions to relicensable areas may additionally
require a Contributor License Agreement (CLA); the repository will tell you if so.

## Workflow

1. **Open or find an issue** describing the change. For anything non-trivial, discuss the approach first.
2. **Fork and branch** from `main`. Use a descriptive branch name.
3. **Make focused commits**, each signed off (`-s`).
4. **Keep license headers correct.** New files must carry the correct SPDX identifier for their layer
   (`SPDX-License-Identifier: AGPL-3.0-only` or `SPDX-License-Identifier: Apache-2.0`).
5. **Open a pull request** using the PR template. Direct pushes to `main` are disabled org-wide.
6. **Pass CI.** Required checks must be green; a reviewer (per `CODEOWNERS`) must approve.

## Pull request expectations
- One logical change per PR; keep diffs reviewable.
- Update docs and tests alongside code.
- Do not add third-party code without confirming its license is compatible with the target layer.
- Changes that would move a file between the AGPL core and the Apache layer are **not** ordinary PRs —
  they require the manifest change process and, for the core, board approval.

## Code of conduct
All participation is governed by our [Code of Conduct](CODE_OF_CONDUCT.md).

## Questions
Open a **License question** issue for licensing, or see [SUPPORT.md](SUPPORT.md) for everything else.
