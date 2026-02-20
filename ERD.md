# Camp Saranac Young Life — Database ERD

> 5 core entities. Centralizes camper data, staff notes, and parent communication.

---

```mermaid
erDiagram
    CABIN {
        int CabinID PK
        string CabinName
        string Area
        int Capacity
    }

    STAFF {
        int StaffID PK
        int CabinID FK
        string FirstName
        string LastName
        string Role
        string Email
    }

    CAMPER {
        int CamperID PK
        int CabinID FK
        string FirstName
        string LastName
        date DateOfBirth
        string MedicalNotes
        string Status
    }

    PARENT_GUARDIAN {
        int ParentID PK
        int CamperID FK
        string FirstName
        string LastName
        string Phone
        string Email
        string Relationship
    }

    CAMPER_NOTE {
        int NoteID PK
        int CamperID FK
        int StaffID FK
        datetime NoteDate
        string NoteType
        string MoodRating
        text Content
        boolean ShareWithParent
    }

    CABIN          ||--o{ CAMPER          : "One cabin houses many campers"
    CABIN          ||--o{ STAFF           : "One cabin has many staff"
    CAMPER         ||--o{ PARENT_GUARDIAN : "One camper has many guardians"
    CAMPER         ||--o{ CAMPER_NOTE     : "One camper has many notes"
    STAFF          ||--o{ CAMPER_NOTE     : "One staff writes many notes"
```

---

## Relationships

| From | Type | To | Description |
|---|---|---|---|
| CABIN | **One-to-Many** | CAMPER | One cabin houses many campers |
| CABIN | **One-to-Many** | STAFF | One cabin is assigned many staff |
| CAMPER | **One-to-Many** | PARENT_GUARDIAN | One camper can have multiple guardians |
| CAMPER | **One-to-Many** | CAMPER_NOTE | One camper accumulates many notes over time |
| STAFF | **One-to-Many** | CAMPER_NOTE | One staff member can write many notes |
