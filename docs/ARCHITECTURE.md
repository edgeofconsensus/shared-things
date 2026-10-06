# Shared Things — Architecture

## 1. Core graph

```
People <-> Things <-> Location <-> Availability <-> Trust
```

The system is modeled around persistent physical Things rather than temporary marketplace listings.

## 2. Primary entities

### User

Represents a person or organization participating in the network.

Candidate attributes:

- identity
- approximate location / operating area
- visibility preferences
- trust history
- circles / relationships
- lending and borrowing policies

### Thing

Represents a physical object that already exists.

Candidate attributes:

- owner / custodian
- name and description
- category / tags
- photos
- condition
- visibility
- approximate location
- availability policy
- history / provenance

A Thing remains the same entity while its status changes.

### Need

Represents demand rather than supply.

Examples:

- “Need a wine hydrometer today.”
- “Need an oscilloscope for one evening.”
- “Need someone nearby who owns this programmer and can help use it.”

Candidate attributes:

- requested Thing type or capability
- time window
- search radius
- urgency
- acceptable sharing modes
- optional compensation

### Availability

Describes whether and how a Thing may currently be accessed.

Candidate modes:

- private
- visible
- borrow
- rent
- give away
- co-own
- need help using

### Interaction

Represents a real-world exchange or collaboration around a Thing.

Possible lifecycle:

```
request -> accepted -> reserved -> handed_over -> borrowed -> returned
```

Exceptional outcomes may include:

```
borrowed -> broken
borrowed -> lost
borrowed -> overdue
```

### Trust

Trust is event-derived rather than only a scalar rating.

Examples of events:

- returned_on_time
- returned_late
- returned_damaged
- broke_it
- repaired_it
- replaced_it
- lost_it
- helped_recover

A future trust model may weight context, severity, recency, restitution, and category-specific experience.

### Quest

A cooperative activity spawned by an event.

Initial example:

```
Thing -> lost -> Find Quest -> participants join -> found -> returned
```

This allows failures to create coordination rather than only penalties.

## 3. Matching

The first matching problem is:

```
Need
  x semantic/capability match
  x distance
  x time availability
  x access policy
  x trust constraints
  -> candidate Things
```

The exact physical location should not need to be public. Approximate discovery can happen first; precise exchange details can be disclosed later by consent.

## 4. Non-goals for the initial concept

Shared Things is not defined as:

- a conventional classified-ads marketplace,
- a rental-only application,
- a product catalog,
- an e-commerce storefront.

Those modes may exist at the edges, but the canonical object is the persistent Thing and its social availability.

## 5. Open architectural questions

Still intentionally unresolved:

- centralized vs federated identity
- exact geospatial privacy model
- deposits and payments
- dispute resolution
- insurance / liability
- verification of expensive or regulated items
- trust calculation
- local communities / circles
- moderation
- mobile vs web-first implementation
- federation / ActivityPub-style interoperability
