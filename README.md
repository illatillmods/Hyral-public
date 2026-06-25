# Hyral

Hyral is a renter-first research engine for apartment outreach.

A renter enters a city. Hyral prepares a ready-to-use interest letter, researches reachable landlord contact routes, validates the output, and organizes the result into batches the renter can send manually from their own email client.

This repository is a public review mirror. It does not contain Hyral source code, prompts, ranking logic, datasets, deployment configuration, or private operational notes.

## Current Status

| Area | Status |
| --- | --- |
| Sweden renter flow | Implemented in the private product repository |
| City-first research flow | Implemented: the research run starts from city submit, while the renter finishes the brief |
| One-time checkout and unlock | Implemented through Stripe Checkout |
| Public packages | Implemented: three packages unlock the full contact list; higher tiers sell ordering and guidance |
| Retry path | Implemented for empty or unsuccessful results |
| Scheduled refresh | Not publicly sold in the current release |
| U.S. market | Private beta validation scaffold, not public live |
| Other countries | Planning and beta configuration only unless separately announced |
| Source availability | Not open source |

## Product Surface

Hyral is designed for renters who need a practical outreach system, not another listing site.

- No account is required for the standard renter flow.
- The renter sees a letter and locked contact proof before checkout.
- Checkout only opens when a run has found contacts.
- All public packages unlock the same full contact list.
- Contact batches are prepared for manual sending; Hyral does not automatically send outreach emails for renters.
- Payment is handled by Stripe. Hyral does not store card data.

There is also a verified recipient-address concept for landlords. It is manually reviewed and renter-first: it can point renters to the right recipient, but it does not buy ranking, remove other discovered routes, or create pay-to-win placement.

## What Is Technically Interesting

Hyral's implementation is built around several constraints that are visible in the private codebase and tests:

- City-first execution: the run starts from the city, and personalization is patched in while research is already moving.
- A single delivery authority decides final keep/exclude behavior, separating organization identity from mailbox usability.
- Customer-visible AI paths fail explicitly when required AI is unavailable, instead of showing synthetic fallback content.
- Market context is carried as a first-class country code so an English UI does not silently become the wrong market.
- Beta regions are locked behind operator access until legal text, pricing, and validation are ready.
- Offline validation harnesses and regression fixtures are used for market expansion work.
- Domain research is advisory evidence, not an independent delivery authority.
- Operational tooling tracks pipeline health, weekly analytics, contact reuse, and recovery without exposing those controls publicly.

Those points are described here at a product and architecture level only. The implementation details are intentionally withheld.

## Repository Contents

- `README.md` - public overview and verified status.
- `ARCHITECTURE.md` - non-sensitive system overview.
- `ROADMAP.md` - public roadmap and status boundaries.
- `SECURITY.md` - security and disclosure posture.
- `FAQ.md` - public answers.
- `NOTICE.md` - all-rights-reserved use restrictions.
- `screenshots/` - reserved for approved public screenshots only.

## Not Included

This mirror intentionally excludes:

- source code and backend logic
- prompts, ranking/scoring logic, and validation rules
- datasets, contact data, production diagnostics, and customer/user data
- private docs, strategy, audits, incident notes, and deployment configuration
- environment examples, secret names, admin paths, or infrastructure details

The purpose is product transparency without making the product cloneable.
