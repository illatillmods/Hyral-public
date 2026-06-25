# Public Architecture Overview

This is a high-level overview only. It omits implementation details, prompts, ranking logic, data structures, private routes, and operational controls.

## Flow

1. The renter enters a city.
2. Hyral starts a research run immediately.
3. The renter completes a short brief while research continues.
4. Hyral prepares an interest letter and researches landlord contact routes.
5. The system validates and organizes reachable contacts.
6. The renter reviews locked proof of the result.
7. If contacts were found, checkout unlocks the full letter and contact batches.
8. The renter sends outreach manually from their own email client.

## Main Subsystems

| Subsystem | Public description |
| --- | --- |
| Web app | Mobile-first renter experience with city-first research, questions, progress, results, checkout, and unlocked outreach |
| API | Handles run lifecycle, payments, unlock, export, retry, localization, analytics, and protected operator workflows |
| Research pipeline | Combines configured market knowledge, live discovery, crawling, extraction, validation, and contact organization |
| Delivery authority | Separates organization-level relevance from mailbox-level usability before producing the final delivery set |
| Payments | Uses Stripe Checkout for one-time purchases |
| Localization | Keeps selected region and UI language separate |
| Operations | Includes readiness checks, analytics summaries, recovery, and private admin workflows |

## Design Constraints

- Renter-first: package tiers must not hide the basic contact list.
- Manual send only: no automatic renter outreach.
- AI-required public surfaces must fail explicitly when the required AI path is unavailable.
- Market expansion must not let one country's vocabulary or evidence rules leak into another market.
- Private diagnostics and source data stay out of public artifacts.

## Public Status Boundaries

Sweden is the live baseline market. The U.S. has beta validation scaffolding. Other configured countries should be treated as planning or beta configuration unless separately announced as live.
