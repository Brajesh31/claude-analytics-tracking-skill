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
