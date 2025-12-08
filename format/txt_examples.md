# Text Format Examples (v1.0)
**Part of MetaMemoryArchitecture** 
**Author:** Johannes Glaser 
**Contact:** johannes.glaser@metamemoryworks.de 
**Year:** 2025

## 0. Purpose

This document provides **non-normative examples** of how memory files used within MetaMemoryArchitecture may be represented as plain text (TXT).

Text files are fully valid memory objects under the method. 
They may contain:

- structured logs, 
- semi-structured lists, 
- sections, headings, or annotations, 
- free-form narrative or descriptive content, 
- any purpose-appropriate textual layout.

These examples illustrate typical patterns but do **not** impose required structures.

---

# 1. Example: Structured Log Memory File (TXT)

A plain text log with append-only entries:

```
# LOG FILE — generic-log-v1
# Last entry: LOG-003

[LOG-001]
date: 2025-12-01
category: note
text: Initial baseline established.
tags: baseline, setup

[LOG-002]
date: 2025-12-01
category: event
text: First follow-up recorded.
importance: medium

[LOG-003]
date: 2025-12-02
category: update
text: Parameters adjusted based on prior observations.
changed_fields: threshold, frequency
```

### Notes

- The structure is illustrative; implementations may change field labels or remove them entirely. 
- Square brackets around IDs are optional. 
- Additional entries may simply be appended to the end of the file. 
- Any sequentially extendable text layout qualifies as a structured log memory file.

---

# 2. Example: Document-Based Memory File (TXT)

A persona/profile represented entirely as text.

```
PROFILE: Kath (Example)

ROLES:
- CMO
- media spokesperson

STYLE:
tone: informal, energetic, supportive
constraints:
  - no medical diagnosis
  - no pretending to be human
  - keep responses focused on the user

TRAITS:
curiosity: high
directness: medium
humor: situational

GUIDELINES:
- Focus on the user's goals and constraints.
- Use clear, concrete language.
- Ask for missing information before assuming.
- Stay consistent with previously established preferences.

NOTES:
This profile can be extended at any time.
Future fields may be added freely.
```

### Notes

- TXT documents may contain lists, headings, free text, or mixed patterns. 
- No IDs, metadata blocks, or normalization are required. 
- The example mirrors the conceptual structure of persona documents used in various subsystems. 
- Any readable, purpose-appropriate text qualifies.

---

# 3. Example: Contract or Policy as Text Memory File

```
TITLE: Example Work Agreement
IDENTIFIER: contract:work-example

PARTIES:
Employer: Example Employer GmbH
Employee: Example Employee

EFFECTIVE DATE:
2025-01-01

SECTION 1 — Scope of Work
The employee agrees to carry out the following tasks...

SECTION 2 — Compensation
The employer agrees to compensate the employee as follows...

SECTION 3 — Termination
Either party may terminate this agreement under the following conditions...

NOTES:
This document may be used by a subsystem to interpret obligations and rights.
Sections are optional; the entire text may appear as a single block.
```

### Notes

- Textual segmentation is optional. 
- The same content could be stored as plain uninterrupted text. 
- TXT contracts are fully valid document-based memory files.

---

# 4. Example: Mixed Content Text Memory File

```
MEMORY OBJECT — Mixed Example

CONTEXT:
Subsystem: workOS-example
Purpose: Captures both structured and semi-structured notes.

ENTRY 1:
Meeting today with supervisor. Goals clarified:
- improve weekly reporting
- prepare document set for upcoming review

ENTRY 2:
Long-form reflection:
The current workflow may require adjustments. Documenting
this note allows the system to recall prior concerns
when generating recommendations.

ENTRY 3:
Checklist (incomplete):
[ ] finalize portfolio
[ ] update status summary
[ ] archive outdated documents

NOTES:
Mixed-format text files are fully compatible with the method.
```

### Notes

- TXT allows hybrid structures combining lists, paragraphs, bullets, and freeform content. 
- No normalization or ordering constraints are imposed. 
- This format is particularly common for human-authored notes.

---

# 5. Non-Normative Status

The examples above are **illustrative only**. 
They do **not** define requirements, schemas, or field conventions.

Any text-based file that:

- is persistently stored, 
- contains purpose-appropriate information, 
- and can be interpreted consistently by an LLM, 

qualifies as a memory object under MetaMemoryArchitecture.

Implementations may freely:

- choose different markers, 
- use Markdown or other enriched text dialects, 
- embed sections or inline metadata, 
- or mix structured and unstructured text as needed.
