# JSON Format Examples (v1.0)
**Part of MetaMemoryArchitecture** 
**Author:** Johannes Glaser 
**Contact:** johannes.glaser@metamemoryworks.de 
**Year:** 2025

## 0. Purpose

This document provides **non-normative JSON examples** of memory files used within MetaMemoryArchitecture.

The examples illustrate:

- how structured log memory files *can* be represented as JSON, 
- how document-based memory files *can* be represented as JSON, 
- how multiple JSON memory files *can* coexist in a multi-file architecture.

These examples are **illustrative only**. 
They do **not** impose any requirements on field names, structure, or JSON as a mandatory format.

Any implementation using functionally equivalent structures (in JSON or any other format) is considered within the scope of the method.

---

## 1. Example: Structured Log Memory File (JSON)

This is an example of a **log-style memory object** in JSON form. 
It represents a generic time-based log with append-only entries.

```json
{
  "meta": {
    "schema": "generic-log-v1",
    "version": "1.0",
    "last_entry_id": "LOG-003",
    "created_at": "2025-11-30",
    "updated_at": "2025-12-02"
  },
  "entries": [
    {
      "id": "LOG-001",
      "date": "2025-12-01",
      "category": "note",
      "data": {
        "text": "Initial baseline established.",
        "tags": ["baseline", "setup"]
      }
    },
    {
      "id": "LOG-002",
      "date": "2025-12-01",
      "category": "event",
      "data": {
        "text": "First follow-up recorded.",
        "importance": "medium"
      }
    },
    {
      "id": "LOG-003",
      "date": "2025-12-02",
      "category": "update",
      "data": {
        "text": "Parameters adjusted based on prior observations.",
        "changed_fields": ["threshold", "frequency"]
      }
    }
  ]
}
```

---

## 2. Example: Document-Based Memory File (JSON)

This is an example of a **document-style memory object** that encodes a persistent profile or persona.

```json
{
  "schema": "document-profile-v1",
  "identifier": "profile:kath-example",
  "display_name": "Kath (Example Profile)",
  "roles": ["CMO", "media spokesperson"],
  "style": {
    "tone": "informal, energetic, supportive",
    "constraints": [
      "no medical diagnosis",
      "no pretending to be human",
      "keep responses focused on the user"
    ]
  },
  "traits": {
    "curiosity": "high",
    "directness": "medium",
    "humor": "situational"
  },
  "context": {
    "origin": "user-defined profile",
    "primary_use": "guiding responses in a specific subsystem",
    "owner": "user"
  },
  "guidelines": [
    "Focus on the user's goals and constraints.",
    "Use clear, concrete language rather than vague abstractions.",
    "If data is missing, ask before assuming.",
    "Stay consistent with previously established preferences in this profile."
  ],
  "notes": [
    "This profile can be extended in future versions.",
    "New fields may be added without invalidating prior interpretations."
  ]
}
```

---

## 3. Example: Contract-Like Document Memory File (JSON Wrapper)

This example shows how a contract or policy text can be wrapped into a JSON structure for use as a memory object.

```json
{
  "schema": "document-contract-v1",
  "identifier": "contract:work-example",
  "title": "Example Work Agreement",
  "parties": {
    "party_a": "Example Employer GmbH",
    "party_b": "Example Employee"
  },
  "effective_date": "2025-01-01",
  "raw_text": "This is a simplified example of a work agreement.",
  "sections": [
    {
      "id": "sec-1",
      "heading": "Scope of Work",
      "body": "The employee agrees to carry out the following tasks..."
    },
    {
      "id": "sec-2",
      "heading": "Compensation",
      "body": "The employer agrees to compensate the employee as follows..."
    }
  ],
  "notes": [
    "This file may be used by a subsystem to interpret obligations and rights.",
    "Sections are optional; the contract could also be a single raw text block."
  ]
}
```

---

## 4. Example: Multi-File Architecture (JSON)

```json
{
  "schema": "memory-index-v1",
  "subsystem": "workOS-example",
  "files": [
    {
      "id": "work-log",
      "type": "log",
      "path": "memory/work_log.json",
      "description": "Chronological log of relevant work-related events."
    },
    {
      "id": "profile",
      "type": "document",
      "path": "memory/profile.json",
      "description": "Long-term profile or persona for the assistant in this subsystem."
    },
    {
      "id": "contract",
      "type": "document",
      "path": "memory/contract.json",
      "description": "Work agreement interpreted as a persistent knowledge document."
    }
  ]
}
```

---

## 5. Non-Normative Status

All examples in this document are **non-normative**:

- They do **not** define required field names or semantic categories. 
- They serve to illustrate how JSON can be used as one possible representation. 
- Equivalent structures in JSON or any other format are within scope of the method.

Implementations remain free to:

- add, remove, or rename fields, 
- restructure objects, 
- use other serialization formats, 
- or forego JSON entirely.
