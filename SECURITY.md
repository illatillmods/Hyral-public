# Security

This public mirror does not contain source code, secrets, infrastructure configuration, production data, prompts, datasets, or customer data.

## Reporting

If you believe you have found a security issue involving Hyral, report it privately to the project owner through the official contact channel. Do not publish exploit details, customer data, infrastructure details, or reproduction steps in a public issue.

Useful reports include:

- affected surface
- impact
- minimal reproduction steps
- screenshots or logs with secrets and personal data removed
- whether the issue was observed in production, staging, or a public artifact

## Scope

In scope:

- Hyral public web surfaces
- payment/unlock behavior
- data exposure risks
- authentication or authorization flaws
- privacy-impacting behavior

Out of scope:

- social engineering
- denial-of-service testing
- scraping or probing that violates service terms
- reports based only on this documentation mirror not containing source code

## Data Handling Posture

The product is designed around minimal renter friction and data minimization:

- no standard account requirement for the renter flow
- manual renter email sending rather than automatic outreach
- Stripe handles card payments
- public mirror excludes private operational data and source material
