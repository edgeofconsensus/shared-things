# Shared Things — Domain Concepts

This file captures product primitives before they harden into schemas or APIs.

## Persistent Thing

A Thing is not an advertisement.

It is a durable digital representation of a physical object that exists in the real world and may change state many times.

Example:

```
wine hydrometer
owner: Alice
condition: good
visibility: nearby community
availability: borrow
```

The Thing may later become reserved, borrowed, broken, repaired, lost, found, transferred, or unavailable without becoming a new listing.

## Need

Users should be able to publish demand directly.

```
Need: wine hydrometer
When: today
Radius: 20 km
```

This matters especially for rare objects whose owners would never think to actively advertise them.

## Broken

`broken` belongs to the Thing's condition/state history.

A break event can also affect interaction history:

```
borrowed
  -> broken
  -> repaired
  -> returned
```

Trust should distinguish between breaking something and failing to take responsibility for it.

Possible events:

```
broke_it
reported_damage
repaired_it
paid_for_repair
replaced_it
```

## Lost

`lost` should not necessarily be a terminal state.

A lost Thing can spawn a **Find Quest**.

```
available
 -> borrowed
 -> lost
 -> quest_started
 -> participants_join
 -> found
 -> returned
```

## Find Quest

A lightweight cooperative object attached to a lost Thing.

Possible fields:

- lost Thing
- approximate last-known area
- time last seen
- photo / identifying details
- visibility
- active participants
- updates
- status: active / found / closed

Possible interaction:

```
Go find quest is currently ongoing -> Join?
```

Positive trust events can be generated from recovery participation:

```
started_recovery
helped_search
helped_recover
returned_recovered_item
```

## Event-derived reputation

Avoid reducing users to one opaque star score.

A profile may summarize real events:

```
38 successful borrows
2 late returns
1 broke_it
1 repaired_it
3 helped_recover
```

The event log preserves context and permits better future scoring models.

## Restitution

Negative events should have repair paths.

Examples:

```
broke_it -> repaired_it
broke_it -> replaced_it
lost_it -> started_find_quest -> recovered_it
```

This supports a central design principle:

> A negative event can generate a cooperative or restorative action rather than only a permanent penalty.

## Sharing modes

A Thing may eventually expose one or more modes:

- private
- visible
- borrow
- rent
- give away
- co-own
- need help using

These are access policies, not separate types of Thing.

## Future concepts

Candidates worth exploring later:

- circles / trusted groups
- shared ownership
- community inventories
- capability search (“I need something that can measure X”)
- scheduled availability
- deposits
- repair quests
- transport / relay quests
- verification for high-value equipment
- item provenance
- local reputation
- community custodianship
