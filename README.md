# Hyral

Apartment hunting has too many listings and not enough ways in.

Hyral is a renter-first research engine for direct landlord outreach. A renter
enters a city, Hyral prepares a ready-to-use interest letter, researches reachable
landlord contact routes, validates the result, and organizes contacts into
batches the renter sends manually from their own email client.

This repository is a public review mirror. It does not contain Hyral source
code, prompts, ranking logic, datasets, deployment configuration, contact data,
or private operational notes.

## Snapshot

Verified from the private implementation on June 25, 2026:

| Area | Public-safe status |
| --- | --- |
| Sweden renter flow | Implemented in the private product repository. |
| City-first research | Implemented: discovery starts from the city while the renter finishes the brief. |
| Letter preview | Implemented: the renter sees usable application copy before checkout. |
| Checkout and unlock | Implemented through Stripe Checkout for one-time package purchases. |
| Package model | Implemented: all paid packages unlock the full contact list; higher tiers sell ordering and guidance. |
| Empty-result retry | Implemented as the primary path when a run finds no usable contacts. |
| Scheduled refresh | Not publicly sold in the current release. |
| U.S. market | Private beta validation scaffold, not public live. |
| Source availability | Not open source. |

## Renter-First Rules

Hyral is not another listings portal, landlord ad product, or automatic spam
tool. The product is shaped by a few hard rules:

- No account is required for the standard renter flow.
- Checkout only opens when a run has found contacts.
- All paid packages unlock the same complete contact list.
- Higher tiers improve ordering and guidance, not access to a better hidden
  inventory.
- Hyral prepares contact batches for manual sending; it does not send outreach
  automatically for renters.
- Verified landlord recipient addresses can point renters to the right inbox,
  but they do not buy ranking, remove other discovered routes, or create
  pay-to-win placement.
- Stripe handles payment card data; Hyral does not store it.

## The Product Loop

1. Enter a city.
2. Hyral starts discovery immediately.
3. Fill in the renter brief while research continues.
4. Review the generated interest letter.
5. See proof that contacts were found.
6. Unlock the full list and work through clean sending batches.

The product is designed for people who need a practical route into the rental
market, not another dashboard to babysit.

## Technically Interesting, Public-Safe Version

The private codebase is built around constraints that matter to renters:

- City-first execution so research starts before the profile is fully complete.
- One final delivery authority for keep/exclude decisions.
- Market context carried as a first-class country code so language selection
  does not silently become the wrong legal or search market.
- Customer-visible AI paths fail explicitly when required AI is unavailable
  instead of showing fake fallback content.
- Beta regions stay operator-locked until pricing, legal text, and validation
  are ready.
- Offline validation harnesses and regression fixtures support market expansion
  work.
- Domain research is treated as advisory evidence, not its own delivery
  authority.

Those details are described here at a product and architecture level only. The
implementation remains private.

## Mirror Contents

- [ARCHITECTURE.md](ARCHITECTURE.md) - non-sensitive system overview.
- [ROADMAP.md](ROADMAP.md) - public roadmap and status boundaries.
- [SECURITY.md](SECURITY.md) - security and disclosure posture.
- [FAQ.md](FAQ.md) - public answers.
- [NOTICE.md](NOTICE.md) - all-rights-reserved use restrictions.
- [screenshots/](screenshots/) - reserved for approved public screenshots only.

## Not Included

- Source code and backend logic.
- Prompts, ranking/scoring logic, validation rules, or contact pipeline internals.
- Datasets, contact data, production diagnostics, customer data, or user data.
- Private docs, strategy, audits, incident notes, and deployment configuration.
- Environment examples, secret names, admin paths, or infrastructure details.

The purpose is product transparency without making the product cloneable.
