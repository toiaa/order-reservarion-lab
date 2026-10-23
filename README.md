# Order Reservation Lab

A small practice system for going deeper on **Redis, Kafka, Docker, Postgres, Flask, and Celery**
by building one focused domain end-to-end: placing an order, reserving stock, confirming or
releasing it, and reacting to that with background work and cache invalidation.

This is **not restaurant table reservations** — it's inventory reservation, like holding stock
for an order until it's confirmed or times out. Think small online shop, not restaurant.

## Start here

Read [`GUIDE.md`](./GUIDE.md) — it has the folder structure, the build order (one step per
sitting), and a checkpoint for each step so you know when to move on.

Everything else in this repo is intentionally empty or stubbed. You write the real code.

## Layout

```
docs/adr/     ADR-style decision notes, one file per decision
migrations/   Hand-written SQL migrations, numbered in order
api/          Flask app (routes / models / services)
workers/      Kafka consumer, outbox publisher, Celery app
scripts/      Seed data, one-off debug scripts
NOTES.md      Your running journal — raw material for ADRs and the final README
```

## Once it's built

Come back and rewrite this README properly: architecture diagram, how to run it, how to demo
the failure modes (duplicate order, killed consumer, expired reservation), and links to the
ADRs in `docs/adr/`.
