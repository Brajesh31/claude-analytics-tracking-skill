# claude-analytics-tracking-skill

A Claude Code skill for planning, implementing, auditing, and improving product and marketing analytics tracking.

## Overview

Analytics is useful only when events and properties support decisions. This skill helps define a measurement plan, map user journeys, implement event tracking, validate data collection, and maintain consistent analytics across web and application experiences.

## Main Capabilities

- Define business and product measurement goals.
- Create event taxonomies and tracking plans.
- Implement page-view and interaction tracking.
- Configure conversion and funnel events.
- Plan UTM parameter conventions.
- Work with analytics platforms and tag managers.
- Validate event payloads and property consistency.
- Audit existing tracking implementations.
- Identify gaps, duplicate events, and unreliable metrics.
- Document ownership and maintenance responsibilities.

## Initial Assessment

Before implementation, establish:

1. Which business or product decisions the data should support.
2. The primary user journeys and conversion actions.
3. Existing analytics tools and event definitions.
4. The application's technical stack.
5. Privacy, consent, and data-retention requirements.
6. Who owns implementation and ongoing maintenance.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-analytics-tracking-skill.git ~/.claude/skills/analytics-tracking
```

## Usage

Invoke the skill when setting up or auditing analytics:

```text
/analytics-tracking
```

Provide the application type, analytics platform, key user journeys, conversion goals, and privacy constraints.

## Tracking Plan Structure

| Field | Description |
|---|---|
| Event name | Stable event identifier |
| Trigger | When the event should fire |
| Properties | Context needed for analysis |
| User context | Relevant anonymous or authenticated identity |
| Destination | Analytics platform or data pipeline |
| Owner | Responsible team or role |
| Validation | How event correctness is tested |

## Recommended Workflow

1. Define the decisions and questions analytics must support.
2. Map the user journey and key conversion points.
3. Create a consistent event naming convention.
4. Define required properties and allowed values.
5. Implement tracking at the correct application layer.
6. Apply consent and privacy controls.
7. Validate events in development and staging.
8. Check for duplicates, missing events, and incorrect values.
9. Document the final tracking plan.
10. Monitor data quality after release.

## Quality Checklist

- Events represent meaningful user actions.
- Names and properties follow a consistent convention.
- Events fire once at the intended point.
- User identity is handled consistently.
- Sensitive information is not collected unnecessarily.
- Consent preferences are respected.
- Conversion definitions are documented.
- Test events are separated from production data.
- Dashboards use validated definitions.

## Repository Contents

- `SKILL.md`: Main analytics implementation and measurement guidance.
- `README.md`: Tracking plan, workflow, and quality checklist.

## Practical Principle

Do not track everything by default. Track what helps answer a real question, and validate the event data before using it to make product or marketing decisions.

## Measurement Design Principles

Treat analytics as a product contract, not a collection of tracking snippets. Define the decisions the data should support before selecting events. A useful measurement plan connects a business objective to a user journey, a measurable action, a stable event definition, and a validation method.

### Event design standards

- Use consistent, action-oriented event names such as checkout_started or account_created.
- Define the precise trigger, including whether an event represents an attempt, success, failure, or completion.
- Give every property a type, meaning, allowed values, and owner.
- Avoid embedding dynamic values in event names.
- Keep UI labels and event definitions separate so a visual redesign does not silently change the analytics contract.
- Document duplicate, retry, offline, and server-confirmation behavior.

### Recommended implementation lifecycle

1. **Define the decision.** Identify the product or marketing question and the metric that will inform it.
2. **Map the journey.** Describe entry points, meaningful actions, conversion steps, and exit conditions.
3. **Specify the taxonomy.** Define events, triggers, properties, identity behavior, destinations, and owners.
4. **Review privacy.** Establish consent requirements, data minimization, retention, deletion, and access controls.
5. **Implement.** Add tracking at a reliable application or server boundary rather than relying only on fragile UI selectors.
6. **Validate.** Compare expected and actual event payloads in a test environment.
7. **Monitor.** Watch event volume, missing properties, duplicates, attribution, and conversion anomalies.
8. **Maintain.** Version the taxonomy, review changes, and retire obsolete events deliberately.

## Supporting Resources

| Resource | Purpose |
|---|---|
| [Event taxonomy template](resources/event-taxonomy-template.md) | Define event names, triggers, property contracts, owners, and review rules. |
| [Tracking QA test matrix](resources/tracking-qa-test-matrix.csv) | Track representative test scenarios and expected event behavior. |
| [Analytics governance checklist](resources/analytics-governance-checklist.md) | Review privacy, consent, quality, launch readiness, and ongoing ownership. |

## Data Quality and Privacy Controls

Do not send passwords, authentication tokens, payment credentials, private message contents, or unnecessary personal data as analytics properties. Treat URLs, user identifiers, and free-text fields as potential sources of sensitive information. Apply consent rules before optional tracking fires, and verify that test traffic is not mixed into production metrics.

Validate critical conversion events against an authoritative application or transaction state. A client-side click is not proof that a payment, subscription, account creation, or other business operation succeeded. Where appropriate, use server-confirmed events as the source of truth and define deduplication behavior between client and server events.

## Handoff Expectations

A tracking implementation is ready for handoff when the event taxonomy is documented, tests cover expected and failure paths, payloads match the schema, privacy controls have been reviewed, dashboards use consistent metric definitions, and each critical event has an owner. The handoff should also identify known gaps and the procedure for disabling or rolling back a broken event stream.
