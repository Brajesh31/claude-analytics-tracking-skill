# Analytics Event Taxonomy Template

Use one definition per event. Event names and properties should be stable, understandable, and tied to a measurable user action.

## Measurement context

- Product or application:
- Business objective:
- Decision this measurement should support:
- Primary user journey:
- Analytics destination:
- Measurement owner:
- Taxonomy version:
- Effective date:

## Event definition

| Field | Definition |
|---|---|
| Event name | Stable lower_snake_case identifier |
| User action | What the user actually did |
| Trigger | Exact point at which the event fires |
| Preconditions | State required before firing |
| Properties | Context needed to interpret the action |
| Identity | Approved anonymous or authenticated identifier |
| Destination | Tool, warehouse, or stream |
| Consent condition | Consent state required |
| Owner | Accountable team or role |
| QA method | How the event is tested |

## Event naming rules

- Prefer action-oriented names such as checkout_started or report_exported.
- Use one naming convention consistently.
- Do not encode dynamic values in event names.
- Do not create separate events for trivial UI variations unless they represent a distinct behavior.
- Keep event names stable when labels or visual design change.
- Document whether an event represents an attempt, success, failure, or completion.

## Property contract

| Property | Type | Required? | Allowed values or format | Sensitive? | Notes |
|---|---|---|---|---|---|
| plan_type | string | Yes / No | Defined plan values | No / Review | |
| source | string | Yes / No | Controlled vocabulary | No / Review | |
| currency | string | Yes / No | ISO currency code | No / Review | |
| value | number | Yes / No | Non-negative numeric value | No / Review | |

Do not place passwords, access tokens, payment card data, government identifiers, private message content, or other unnecessary personal data in event properties. Use approved identifiers and privacy controls.

## Example event contract

~~~json
{
  "event_name": "checkout_started",
  "description": "A user begins the checkout flow",
  "trigger": "Checkout page becomes active after a user action",
  "properties": {
    "cart_item_count": "integer",
    "currency": "ISO 4217 string",
    "value": "number"
  },
  "owner": "Product Analytics",
  "consent_required": true
}
~~~

Treat this as a documentation example. Validate the contract against the actual event SDK and platform schema.

## Review

- [ ] Event supports a stated product or business question.
- [ ] Trigger is precise and not dependent on a vague UI condition.
- [ ] Properties have types, allowed values, and ownership.
- [ ] Duplicate and retry behavior is documented.
- [ ] Consent and retention requirements are defined.
- [ ] No unnecessary sensitive data is collected.
- [ ] The event has an owner and a test case.
