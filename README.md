# Camp Saranac Young Life — Database Design

School project: database system design for the Saranac Young Life Sleepaway Camp.

## Files

- [`ERD.md`](./ERD.md) — Full Entity-Relationship Diagram with Mermaid diagram, entity descriptions, and design decisions

## System Overview

Centralizes camper information, staff notes, parent communication, and activity tracking across counselors, cabins, and the main office.

**Core problem:** Camp info is scattered. Parents get no regular updates. Staff can't quickly answer parent questions.

**Solution:** One database. Staff record observations → filtered view surfaces to parents → trust built → retention improved.

## Entities

`SESSION` → `CABIN` → `CAMPER` ↔ `PARENT_GUARDIAN`  
`STAFF` → `CAMPER_NOTE` (internal) → `PARENT_UPDATE` (outbound)  
`CAMPER` ↔ `ACTIVITY` via `CAMPER_ACTIVITY`  
`PHONE_LOG` tracks limited phone contact events
