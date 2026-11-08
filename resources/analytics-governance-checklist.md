# Analytics Governance Checklist

Use this checklist before launching a new tracking implementation and during periodic audits.

## Purpose and ownership

- [ ] Each tracked event supports a defined product, customer, or business question.
- [ ] Event definitions have an accountable owner.
- [ ] The taxonomy has a version and change history.
- [ ] Deprecated events have a retirement plan.
- [ ] Dashboard and metric definitions have named owners.

## Data minimization and privacy

- [ ] Collect only properties needed for an approved use case.
- [ ] Review event names, URLs, identifiers, and properties for personal or sensitive data.
- [ ] Exclude credentials, payment details, authentication tokens, and unnecessary free text.
- [ ] Document consent requirements for each tracking category.
- [ ] Confirm consent state is applied before optional tracking fires.
- [ ] Define retention and deletion behavior.
- [ ] Review identity stitching and cross-device behavior.
- [ ] Confirm data sharing and destination access are appropriately restricted.

## Event quality

- [ ] Event names follow one naming convention.
- [ ] Trigger conditions are explicit and testable.
- [ ] Required properties have types and controlled values.
- [ ] Attempt, success, failure, and completion events are distinguishable.
- [ ] Duplicate, retry, and offline behavior are defined.
- [ ] Client-side and server-side events have a clear source of truth.
- [ ] Test events are excluded from production reporting.

## Release readiness

- [ ] Events are validated in a staging or test environment.
- [ ] Expected payloads are compared with actual payloads.
- [ ] Consent, identity, and cross-domain scenarios are tested.
- [ ] Data quality alerts exist for critical event streams.
- [ ] Dashboards use documented metric definitions.
- [ ] Rollback or disablement steps are known.

## Ongoing review

- [ ] Review event volume anomalies and missing data.
- [ ] Remove obsolete events and properties safely.
- [ ] Reassess privacy and consent requirements after product changes.
- [ ] Review vendor, destination, and access changes.
- [ ] Confirm business decisions are still supported by the measurement plan.
