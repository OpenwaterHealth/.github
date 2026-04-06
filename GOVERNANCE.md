# Openwater Governance

This document describes the governance model for the Openwater open-source medical device ecosystem. It defines how contributions are evaluated, decisions are made, and community members participate in the project's direction.

Openwater builds open-source platforms for medical imaging and neuromodulation. Because our technology operates in a regulated healthcare environment, our governance balances open innovation with patient safety, regulatory compliance, and manufacturing feasibility.

## Table of Contents

- [Guiding Principles](#guiding-principles)
- [Community Roles](#community-roles)
- [Organizational Structure](#organizational-structure)
- [Contribution Evaluation Process](#contribution-evaluation-process)
- [Decision-Making Framework](#decision-making-framework)
- [Intellectual Property and Licensing](#intellectual-property-and-licensing)
- [Safety and Regulatory Governance](#safety-and-regulatory-governance)
- [Recognition and Attribution](#recognition-and-attribution)
- [Code of Conduct](#code-of-conduct)
- [Amendment Process](#amendment-process)

---

## Guiding Principles

1. **Openness**: All platform software, hardware designs, and safety data are developed in the open. Decisions and their rationale are documented publicly.
2. **Patient Safety First**: No contribution is merged into a production branch without appropriate safety review. Innovation is encouraged, but never at the expense of patient welfare.
3. **Collaborative Evaluation**: Every contribution of substance receives thoughtful technical review. We assume good faith and lead with acknowledgment of the contributor's effort and intent.
4. **Regulatory Awareness**: Medical device development operates under regulatory constraints. Our governance accounts for FDA pathways, ISO standards, and biocompatibility requirements as first-class considerations — not afterthoughts.
5. **Meritocratic Participation**: Influence in the project is earned through sustained, quality contributions. All community members — regardless of affiliation — can advance through the contributor ladder.

---

## Community Roles

### Observer

Anyone who follows the project, reads documentation, or participates in discussions. No formal requirements.

### Contributor

A community member who has submitted at least one accepted contribution (code, documentation, research data, bug report, protocol, or hardware design). Contributors sign the [Contributor License Agreement (CLA)](#intellectual-property-and-licensing) before their first contribution is merged.

### Maintainer

A trusted contributor with write access to one or more repositories. Maintainers are responsible for reviewing pull requests, triaging issues, and ensuring code quality within their area. Maintainers are nominated by existing Maintainers or TSC members and approved by the Technical Steering Committee.

**Responsibilities:**
- Review and merge contributions within their repository scope
- Ensure contributions meet quality, safety, and documentation standards
- Mentor new contributors
- Flag contributions that require TSC or regulatory review

### Technical Steering Committee (TSC) Member

TSC members set the technical direction of the project, make architectural decisions, and serve as the final decision authority on contributions that affect safety, regulatory status, or strategic direction.

**Responsibilities:**
- Approve or reject contributions with regulatory, safety, or strategic implications
- Define the project roadmap and release criteria
- Resolve disputes escalated by Maintainers
- Oversee the licensing transition and IP governance
- Represent the project in external partnerships

---

## Organizational Structure

### Technical Steering Committee (TSC)

The TSC is the project's governing body. It operates with the following structure:

**Composition**: The TSC includes representatives from Openwater's engineering, regulatory affairs, manufacturing, and clinical advisory functions, along with elected community representatives. The target size is 5–9 members.

**Community Seats**: At least two TSC seats are reserved for community-elected members. Elections are held annually and are open to any Maintainer who has been active for at least six months.

**Chair**: The TSC elects a Chair from among its members. The Chair facilitates meetings, sets agendas, and serves as the public point of contact for governance matters.

**Meetings**: The TSC meets biweekly. Meeting agendas are posted at least 48 hours in advance. Minutes are published within one week.

### Review Panels

For contributions that require specialized evaluation (e.g., novel materials, new clinical applications, significant architectural changes), the TSC may convene a Review Panel. Review Panels are temporary, cross-functional groups with domain expertise relevant to the contribution under review. They report findings and recommendations to the TSC but do not hold decision-making authority.

---

## Contribution Evaluation Process

All contributions follow a standard lifecycle. The depth of review scales with the contribution's scope and risk profile.

### Tier 1: Standard Contributions

Bug fixes, documentation improvements, test coverage, minor feature additions, and code quality improvements.

**Process:**
1. Contributor opens a pull request following the [Contribution Guidelines](CONTRIBUTING.md)
2. A Maintainer reviews for code quality, test coverage, and documentation
3. Maintainer merges upon approval

**Typical timeline:** 1–2 weeks.

### Tier 2: Significant Contributions

New features, architectural changes, new integrations, protocol changes, or contributions that affect multiple repositories.

**Process:**
1. Contributor opens a proposal issue or RFC (Request for Comments) describing the change, its rationale, and its impact
2. Two-week community review period for feedback and discussion
3. At least two Maintainers review the implementation
4. TSC reviews proposals that affect project architecture or direction

**Typical timeline:** 2–4 weeks.

### Tier 3: High-Impact Contributions

Contributions involving new materials, novel clinical applications, significant cost or manufacturing changes, regulatory pathway implications, or safety-critical modifications.

These contributions trigger the full four-phase evaluation process:

#### Phase 1: Acknowledgment and Community Review (Weeks 1–2)

- The contribution is acknowledged publicly, with explicit recognition of its potential value
- The proposal is posted to the community forum for transparent peer review
- Independent validation or replication is requested where applicable
- Potential collaborators are identified

#### Phase 2: Technical Steering Committee Review (Weeks 3–4)

The TSC convenes a Review Panel with relevant domain expertise. The panel evaluates:

- **Technical Merit**: Has the claimed improvement been validated? What methodologies were used? What is the underlying mechanism?
- **Safety Assessment**: What are the thermal, mechanical, or biocompatibility risks? Are there trade-offs that affect patient safety?
- **Regulatory Pathway**: Does this require a new FDA submission, or can it qualify as a modification to existing clearance? What is the timeline and cost to achieve regulatory approval? Does the material or method meet ISO 10993 or equivalent standards?
- **Manufacturing Feasibility**: What is the cost impact? Are qualified suppliers available? What are realistic procurement timelines?
- **Commercial Viability**: Does the cost-benefit analysis support adoption? Should this be offered as a premium configuration rather than a standard replacement? What do clinical partners say about willingness to adopt?

#### Phase 3: Decision (Week 5)

The TSC selects one of three pathways:

1. **Research Branch**: The contribution is accepted into a dedicated research branch for community experimentation without commercial commitment. This enables innovation while managing risk.
2. **Sponsored Development**: If the value proposition is strong but regulatory or manufacturing hurdles remain, Openwater may fund the contributor to resolve those challenges through a sponsored development agreement.
3. **Decline with Explanation**: If the contribution does not align with the current roadmap or presents unacceptable risk, the TSC provides a clear, written rationale. The contributor retains full rights to pursue the work independently.

#### Phase 4: Recognition (Ongoing)

Regardless of the decision outcome, the contributor is recognized for their work. See [Recognition and Attribution](#recognition-and-attribution).

---

## Decision-Making Framework

### Consensus-Seeking

The TSC operates on a consensus-seeking basis. Proposals are discussed until general agreement is reached. Silence after a reasonable discussion period (typically one week) is treated as consent.

### Voting

When consensus cannot be reached, the TSC may call a formal vote. Decisions require a simple majority of TSC members present, provided a quorum (more than half of TSC membership) is met. Each TSC member has one vote. The Chair votes only to break ties.

### Escalation

If a Maintainer or Contributor disagrees with a TSC decision, they may request a formal review by submitting a written appeal. The TSC must respond within two weeks with a written explanation of its decision. Appeals are documented in the project's decision log.

### Conflict of Interest

TSC members must disclose conflicts of interest (financial, institutional, or personal) relevant to any decision. Members with a conflict recuse themselves from voting on that matter.

---

## Intellectual Property and Licensing

### Current Licensing

Openwater's software is currently licensed under AGPL v3.0. The project is actively transitioning to Apache 2.0 to encourage broader commercial adoption and align with the open-source service revenue model.

### Contributor License Agreement (CLA)

All contributors must sign the Openwater CLA before their first contribution is merged. The CLA:

- Grants Openwater a perpetual, worldwide, non-exclusive license to use, modify, and distribute the contribution
- Preserves the contributor's rights to use their own work for any purpose
- Enables Openwater to manage the AGPL-to-Apache 2.0 licensing transition without needing to contact every contributor individually

The CLA is designed to protect both the contributor and the project. It is a standard practice in open-source projects undergoing license transitions.

### Patent Grant

Contributions that include patentable innovations are covered by the CLA's patent grant clause. Contributors retain ownership of their patents but grant Openwater and downstream users a royalty-free license to practice those patents within the scope of the project.

### Hardware and Safety Data

Hardware designs and safety data contributed to the project are shared under the same licensing terms as the software. Contributors who share safety data (adverse events, calibration data, testing protocols) retain the right to publish and use that data independently.

---

## Safety and Regulatory Governance

Because Openwater develops medical devices, our governance includes provisions that go beyond typical open-source projects.

### Safety Review Requirements

Any contribution that could affect device behavior, acoustic output, electrical safety, or biocompatibility must pass a safety review before merging into any branch that feeds production releases. Safety reviews are conducted by Maintainers with relevant domain expertise or by the TSC.

### Adverse Event Reporting

Community members who observe unexpected device behavior, safety concerns, or adverse events during research use must report them through Openwater's adverse event reporting process. Reports are reviewed by the TSC and shared (in anonymized form) with the broader community. Openwater champions shared safety data as a core principle — pooled adverse event data accelerates regulatory timelines for everyone using the platform.

### Regulatory Impact Assessment

Contributions that introduce new materials, modify acoustic parameters, change transducer geometry, or alter the device's intended use trigger a regulatory impact assessment. The TSC evaluates whether the change requires a new FDA submission, a modification to existing clearance, or falls within the scope of research-use-only operation.

### Research Use Disclaimer

All Openwater devices are for research use only. They are not cleared or approved by the FDA for clinical use. This status applies to all branches, including research branches containing community contributions. Contributors and users are responsible for obtaining appropriate institutional approvals (IRB, ethics board) for their research activities.

---

## Recognition and Attribution

Openwater believes that contributors should be recognized regardless of whether their specific contribution is integrated into the production platform. The learning and relationship-building that comes from every contribution strengthens the ecosystem.

### Recognition Mechanisms

- **Contributor Attribution**: All accepted contributions are attributed in release notes and the project's CONTRIBUTORS file
- **Co-Authorship**: Contributors whose work leads to publications are offered co-authorship
- **Featured Contributor Profiles**: Significant contributors are featured on the Openwater community website
- **Conference Invitations**: Contributors may be invited to present at the annual OpenWater Summit and other community events
- **Consulting and Employment**: Openwater actively considers contributors for consulting engagements and employment opportunities

### Contributor Ladder

Community members advance through roles (Observer → Contributor → Maintainer → TSC Member) based on sustained, quality participation. The criteria for advancement are:

| Role | Requirements |
|------|-------------|
| Observer | None — follow the project and participate in discussions |
| Contributor | At least one accepted contribution and a signed CLA |
| Maintainer | Sustained contributions over 6+ months, nominated by a Maintainer or TSC member, approved by TSC |
| TSC Member | Demonstrated technical leadership and community stewardship, elected by community or appointed by TSC |

---

## Code of Conduct

All community members are expected to follow the [Openwater Code of Conduct](CODE_OF_CONDUCT.md). The Code of Conduct applies to all project spaces, including GitHub repositories, community forums, chat channels, and events.

Violations are reported to the TSC, which is responsible for enforcement. Reports are handled confidentially, and the TSC will communicate outcomes to the reporter.

---

## Amendment Process

This governance document is a living document. Amendments may be proposed by any Contributor through a pull request to this file. Amendments require:

1. A two-week community comment period
2. TSC approval by simple majority vote
3. Public documentation of the rationale for the change

Minor clarifications (typo fixes, formatting) may be merged by any Maintainer without a formal vote.

---

## Document History

| Date | Change | Author |
|------|--------|--------|
| 2026-04-06 | Initial version | Openwater Community Team |

---

*This governance framework is inspired by practices from the Cloud Native Computing Foundation (CNCF), the Linux Foundation, and the Apache Software Foundation, adapted for the unique requirements of open-source medical device development.*
