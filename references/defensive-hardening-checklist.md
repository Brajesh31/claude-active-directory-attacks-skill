# Active Directory Defensive Hardening Checklist

Use this checklist to review configuration and remediation priorities. Adapt each item to the domain's business requirements and supported operating systems.

## Identity and privilege

- [ ] Privileged group membership has a documented owner and business reason.
- [ ] Nested group membership is reviewed.
- [ ] Separate administrative accounts are used where appropriate.
- [ ] Tiered administration boundaries are enforced.
- [ ] Legacy, dormant, and orphaned accounts are disabled or removed through change control.
- [ ] Privileged access is time-bound where feasible.
- [ ] Service identities have least-privilege permissions.
- [ ] Managed service accounts are used where supported.

## Authentication

- [ ] Multi-factor authentication protects privileged and remote access paths.
- [ ] Password and lockout policies reflect current risk and operational needs.
- [ ] Legacy authentication protocols are inventoried and restricted where possible.
- [ ] NTLM use is measured and reduced according to an approved migration plan.
- [ ] SMB signing and encryption requirements are reviewed.
- [ ] Domain controller time synchronization is monitored.
- [ ] Kerberos encryption settings are reviewed and legacy algorithms are phased out where supported.

## Delegation and service accounts

- [ ] Unconstrained delegation is eliminated unless a documented exception exists.
- [ ] Constrained delegation and resource-based delegation are reviewed.
- [ ] Service principal names are inventoried and have clear owners.
- [ ] Service account passwords are managed and rotated.
- [ ] Service accounts cannot log on interactively unless required and approved.
- [ ] High-privilege service identities are minimized.

## Certificate services

- [ ] Certificate templates are inventoried.
- [ ] Enrollment and template modification permissions are least-privilege.
- [ ] Subject and SAN configuration is reviewed.
- [ ] Issuance requirements and approval workflows are enabled where appropriate.
- [ ] Certificate authority administration is separated from routine server administration.
- [ ] Issued certificates and unusual enrollment activity are monitored.
- [ ] Unused templates and obsolete enrollment endpoints are removed safely.

## Group Policy and trusts

- [ ] GPO edit rights are restricted and reviewed.
- [ ] GPO changes are logged and monitored.
- [ ] Scripts and files distributed through policy are protected.
- [ ] SYSVOL permissions are reviewed.
- [ ] Trust relationships have documented business owners.
- [ ] Trust authentication scope is limited to what is required.
- [ ] Cross-forest and external trust activity is monitored.

## Monitoring and recovery

- [ ] Domain controller security logs are collected centrally.
- [ ] Privileged group changes generate alerts.
- [ ] Unusual authentication patterns are monitored.
- [ ] Certificate issuance and template changes are monitored.
- [ ] Directory replication and policy changes are logged.
- [ ] Backups of directory services are protected and tested.
- [ ] Recovery procedures are documented and exercised.
- [ ] Incident responders know how to handle suspected credential compromise.

## Remediation tracking

| Finding | Affected asset | Risk | Owner | Target date | Verification evidence |
|---|---|---|---|---|---|
| | | | | | |

Do not make production changes based solely on this checklist. Use the organization's approved change-management and recovery procedures.
