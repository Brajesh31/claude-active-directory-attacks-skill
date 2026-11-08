# Active Directory Security Assessment Skill

A structured skill for reviewing Microsoft Active Directory security, understanding identity attack paths, organizing an authorized assessment, and turning findings into defensible remediation actions.

This repository contains technical material about Active Directory attack techniques. Use it only in an environment you own or are explicitly authorized to assess. Do not run intrusive tests against production systems without written authorization, a defined scope, and an approved test window.

## Scope and Authorized Use

Before any assessment, establish:

- Written authorization from the system owner.
- Exact domains, forests, hosts, networks, and accounts in scope.
- Explicitly permitted and prohibited test activities.
- Test window, emergency contacts, and stop conditions.
- Credential handling, evidence storage, and data-retention rules.
- Whether any validation may modify directory objects or affect authentication.

Use an isolated lab whenever a technique could extract credentials, impersonate an identity, change directory permissions, or affect domain availability. Do not collect or retain real user passwords, hashes, tickets, or private data unless the authorization explicitly permits the activity and a secure handling plan is in place.

## What the Skill Covers

The skill organizes Active Directory security topics across:

- Domain architecture and identity configuration.
- Directory reconnaissance and relationship mapping.
- Kerberos and NTLM security considerations.
- Delegation and privileged-account exposure.
- Active Directory Certificate Services configuration.
- Group Policy and domain trust risks.
- Lateral-movement and privilege-escalation paths.
- Security-control validation and remediation planning.

## When to Use It

Use this skill when preparing an authorized internal security review, assessing an isolated training environment, reviewing identity configuration, documenting directory attack paths, or prioritizing Active Directory hardening work.

It is not a substitute for an approved penetration-test plan, a production change-management process, or an independent security review.

## Installation

~~~bash
git clone https://github.com/Brajesh31/claude-active-directory-attacks-skill.git ~/.claude/skills/active-directory-attacks
~~~

## Invocation

~~~text
/Active-Directory-Attacks
~~~

Provide the assessment objective, authorized scope, environment type, permitted test methods, and operational constraints.

## Recommended Assessment Workflow

### 1. Confirm authorization and scope

Use the [assessment scope template](references/authorized-assessment-scope-template.md). Confirm the exact environment and stop conditions before any validation.

### 2. Establish the environment baseline

Record domain and forest structure, domain controllers, trust relationships, identity systems, critical services, and existing monitoring. Avoid making assumptions based on partial discovery.

### 3. Review identity and privilege configuration

Assess privileged groups, service identities, delegation settings, stale accounts, password policy, authentication controls, and administrative separation. Use read-only methods wherever possible.

### 4. Review high-risk configuration areas

Prioritize Kerberos and NTLM controls, certificate services, Group Policy permissions, trust relationships, legacy protocols, and service-account design. Record evidence and affected assets.

### 5. Map exposure and control gaps

Describe the path from a weakness to potential impact without unnecessarily collecting secrets or changing live directory state. Distinguish confirmed misconfiguration from a theoretical path.

### 6. Validate monitoring and response

Where authorized, verify that identity and directory security events are logged, routed, retained, and investigated. Use non-disruptive test events or simulation procedures where possible.

### 7. Prioritize remediation

Use the [defensive hardening checklist](references/defensive-hardening-checklist.md) to turn findings into changes such as least-privilege corrections, stronger authentication controls, certificate-template hardening, and improved monitoring.

### 8. Report and retest

Document affected systems, business impact, evidence, remediation owner, and retest result. Do not claim a control is effective until the corrected configuration has been verified.

## Defensive Review Areas

| Area | What to review | Defensive outcome |
|---|---|---|
| Privileged groups | Membership, nested groups, standing access | Reduce unnecessary privilege |
| Service accounts | Password age, SPNs, interactive logon, ownership | Use managed identities and least privilege |
| Kerberos | Legacy encryption, delegation, ticket exposure | Reduce ticket abuse opportunities |
| NTLM | Usage, relay exposure, signing requirements | Reduce or phase out NTLM where possible |
| Certificate services | Template permissions, enrollment, issuance | Remove unsafe enrollment paths |
| Group Policy | Edit rights, links, scripts, SYSVOL exposure | Protect policy integrity |
| Domain trusts | Scope, authentication settings, monitoring | Limit trust exposure |
| Monitoring | Directory changes, privileged logons, authentication anomalies | Improve detection and response |

## Included Resources

- [Authorization and assessment scope template](references/authorized-assessment-scope-template.md)
- [Defensive hardening checklist](references/defensive-hardening-checklist.md)
- [Advanced technical reference](references/advanced-attacks.md), use only within approved scope and isolated environments.

## Operational Safety Checklist

- Authorization and scope are documented.
- Production systems are excluded unless expressly approved.
- Potentially disruptive tests have a defined maintenance window.
- Credential and evidence handling are defined.
- No persistence or destructive changes are introduced.
- Directory changes are approved, logged, and reversible.
- Emergency contacts and stop conditions are known.
- Findings are reported without exposing secrets.

## Limitations

Active Directory environments differ by version, configuration, network topology, and security controls. A finding in one lab does not prove the same condition exists in another environment. Validate assumptions, distinguish observed facts from hypotheses, and coordinate any changes with the system owner.

## Repository Structure

~~~text
claude-active-directory-attacks-skill/
├── SKILL.md
├── README.md
├── LICENSE
└── references/
    ├── advanced-attacks.md
    ├── authorized-assessment-scope-template.md
    └── defensive-hardening-checklist.md
~~~

## License

Released under the MIT License. Copyright (c) 2026 Brajesh Kumar. See the root `LICENSE` file for the complete terms.
