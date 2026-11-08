# claude-active-directory-attacks-skill

A Claude Code skill for understanding Active Directory security risks and conducting authorized domain security assessments.

## Overview

This skill covers Active Directory security concepts and assessment workflows involving domain discovery, identity configuration, Kerberos, authentication protocols, delegation, privilege boundaries, and lateral-movement risk.

Use it only in an authorized lab, internal assessment, or environment where explicit permission has been granted.

## Main Assessment Areas

- Active Directory domain and trust architecture.
- Identity and group membership review.
- Kerberos configuration and ticket-related risks.
- NTLM and authentication policy review.
- Delegation and service account exposure.
- Privileged group and access analysis.
- Domain controller security posture.
- Lateral movement risk assessment.
- Detection and monitoring coverage.
- Evidence and remediation planning.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-active-directory-attacks-skill.git ~/.claude/skills/active-directory-attacks
```

## Usage

Invoke the skill for an authorized Active Directory security review:

```text
/active-directory-attacks
```

Provide the assessment scope, domain environment, permitted test methods, account privileges, and any prohibited actions.

## Recommended Assessment Workflow

1. Confirm written authorization and scope.
2. Identify domain boundaries and assessment objectives.
3. Review identity, group, and trust configuration.
4. Inspect authentication and delegation settings.
5. Identify excessive privileges and risky service accounts.
6. Validate findings with non-destructive methods where possible.
7. Collect sanitized evidence.
8. Assess impact and likely attack paths.
9. Recommend configuration and monitoring improvements.
10. Re-test remediated controls.

## Defensive Focus

- Apply least privilege to users and service accounts.
- Reduce unnecessary domain administrator membership.
- Review delegation configuration.
- Enforce strong authentication policies.
- Monitor privileged operations and unusual authentication.
- Protect domain controllers and administrative workstations.
- Maintain clear ownership of service accounts.
- Review stale identities and unused permissions.

## Reference Guide

The repository includes `references/advanced-attacks.md` for additional technical assessment concepts and defensive considerations.

## Reporting Checklist

- Scope and authorization are recorded.
- Findings are supported by evidence.
- Sensitive credentials and hashes are not exposed.
- Impact is explained in business terms.
- Remediation is specific and testable.
- Limitations and untested areas are disclosed.

## Repository Contents

- `SKILL.md`: Main Active Directory assessment instructions.
- `references/advanced-attacks.md`: Advanced assessment reference.
- `README.md`: Scope, workflow, and defensive guidance.

## Safety Boundaries

Do not attempt domain compromise, persistence, credential extraction, or lateral movement outside the agreed assessment scope. Stop if the activity risks service disruption or exposes unrelated sensitive information.

## Practical Principle

The objective of a security assessment is to identify and reduce risk, not to maximize access. Keep testing proportionate, authorized, and evidence-driven.
