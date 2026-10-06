# Shared Things

**Shared Things is not a marketplace. It is a searchable social inventory of physical things that already exist around us.**

Many useful objects spend most of their lifetime unused: specialist meters, electronics, tools, adapters, lab equipment, hobby gear, agricultural instruments, repair equipment, and countless niche objects. A person nearby may suddenly need exactly one of them for an hour, a day, or once a year.

Shared Things makes those objects discoverable without requiring their owners to turn them into conventional listings.

## Core idea

A person registers a **Thing**, not an advertisement.

A Thing can exist privately, be visible to a trusted circle, or be available for borrowing, renting, giving away, co-owning, or requesting help with its use.

The central graph is:

```
People <-> Things <-> Location <-> Availability <-> Trust
```

The primary question is not:

> What is currently for rent?

It is:

> Where nearby does the thing I need already exist?

Example:

```
Need: wine hydrometer
When: today
Radius: 20 km
```

The system can discover matching Things whose owners permit requests.

## Principles

- Things are persistent entities with their own identity and history.
- Availability is a state, not the identity of the Thing.
- Sharing can be free, paid, reciprocal, temporary, permanent, or collaborative.
- Location can be approximate until both sides agree to exchange.
- Trust should be derived from real interaction history, not only star ratings.
- Negative events can create recovery workflows instead of ending in punishment.
- A Thing may outlive many individual borrow transactions and accumulate provenance.

## Early status vocabulary

Possible availability / condition states include:

`private`, `visible`, `available`, `reserved`, `borrowed`, `unavailable`, `broken`, `lost`, `given_away`.

Interaction events may include:

`returned_on_time`, `returned_late`, `returned_damaged`, `broke_it`, `lost_it`, `repaired_it`, `replaced_it`, `helped_recover`.

A `lost` Thing can create a collaborative **Find Quest** that other nearby users may join.

## Repository stage

This repository currently captures the product model and architecture before implementation choices are fixed.

See:

- [Architecture](docs/ARCHITECTURE.md)
- [Concepts](docs/CONCEPTS.md)

## License

GNU Affero General Public License v3.0.
