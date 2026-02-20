# Camp Saranac Young Life — Database Design

School project: database system design for the Saranac Young Life Sleepaway Camp.

## Files

- **[View Styled ERD →](https://rhinehart514.github.io/camp-saranac-db/erd.html)** — Red PKs, blue FKs, full relationship table
- [`ERD.md`](./ERD.md) — Mermaid diagram + entity descriptions + design decisions
- [`erd.html`](./erd.html) — Styled HTML version

## System Overview

Centralizes camper information, staff notes, parent communication, and activity tracking across counselors, cabins, and the main office.

**Core problem:** Camp info is scattered. Parents get no regular updates. Staff can't quickly answer parent questions.

**Solution:** One database. Staff record observations → filtered view surfaces to parents → trust built → retention improved.

## Entities

`SESSION` → `CABIN` → `CAMPER` ↔ `PARENT_GUARDIAN`  
`STAFF` → `CAMPER_NOTE` (internal) → `PARENT_UPDATE` (outbound)  
`CAMPER` ↔ `ACTIVITY` via `CAMPER_ACTIVITY`  
`PHONE_LOG` tracks limited phone contact events
