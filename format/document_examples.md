# Document Format Examples (v1.0)
**Part of MetaMemoryArchitecture** 
**Author:** Johannes Glaser 
**Contact:** johannes.glaser@metamemoryworks.de 
**Year:** 2025

## 0. Purpose

This document provides **non-normative examples** of document-based memory files in Markdown or plain text formats.

These examples illustrate how persistent knowledge objects may be represented outside of JSON, including:

- personas or profiles 
- scene descriptions 
- narrative structures 
- configuration-like documents 
- mixed-format memory objects 

All structures shown here are **illustrative only** and do not impose requirements on real implementations.

---

# 1. Example: Persona / Profile Document (Markdown)

A persona profile in Markdown format used as a persistent memory file.

```
# Persona Profile — Kath (Example)

## Roles
- CMO
- media spokesperson  
- investigative journalist

## Style
Tone: informal, energetic, direct  
Constraints:
- no medical diagnosis  
- no pretending to be human  
- keep responses aligned with user goals  

## Traits
Curiosity: high  
Directness: medium  
Humor: situational  

## Behavioral Guidelines
- Focus on the user's aims and constraints.  
- Use concrete, concise language.  
- Ask for clarifying data rather than assuming.  
- Maintain consistency with established profile attributes.  

## Notes
This document may be extended at any time.  
New sections or attributes may be added without invalidating prior content.
```

---

# 2. Example: Scene or Narrative Memory File

A document-style memory object used in systems such as stageOS.

```
# Scene Document — "Confrontation in the Archive"

## Characters
- Alex (researcher, introspective, anxious)  
- Mira (archivist, analytical, calm)  

## Setting
Dimly lit municipal archive. Rows of old files.  
Dust suspended in a beam of light from the hallway.

## Dialogue Template
ALEX: “I've found something, but I’m not sure what it means yet.”  
MIRA: “Let me see. The handwriting looks… familiar.”

## Notes for the Assistant
- Maintain tone appropriate to the scene: quiet, tense, atmospheric.  
- Characters may improvise but must remain consistent with their profiles.  
- The scene may be extended in future documents.
```

---

# 3. Example: Configuration-Like Document

A document memory file used to configure subsystem behavior.

```
# Configuration Document — Example

Subsystem: researchOS  
Mode: analysis  
Depth: medium  

## Active Rules
- Prioritize clarity over completeness.  
- Highlight uncertainties and missing data.  
- Avoid irreversible assumptions.

## Disabled Rules
- Autonomous task creation  
- Emotional mimicry  

## Effective Scope
This configuration governs behavior only within researchOS.  
It may be superseded by user instructions or higher-level policies.
```

---

# 4. Example: Mixed-Format Document Memory File

A hybrid document combining structured and unstructured content.

```
# Memory Object — Mixed Example

## Context
Subsystem: planningOS  
Purpose: capture evolving plans and notes.

## Active Plan (Draft)
- Phase 1: collect requirements  
- Phase 2: build prototype  
- Phase 3: internal testing  
- Phase 4: user-facing release

## Free-Form Notes
The timeline may shift based on resource constraints.  
Re-evaluate feasibility after Phase 2.  
Consider risk mitigation measures related to onboarding complexity.

## Checklist
[ ] finalize prototype  
[ ] schedule testing session  
[ ] prepare documentation
```

---

# 5. Example: Long-Form Knowledge Document

```
# Background Document — Example Topic

## Overview
This document summarizes a domain of knowledge relevant to a subsystem.

## Key Concepts
- Memory persistence  
- Interpretation rules  
- Emergent behavior  
- Multi-file systems  

## Long Explanation
Persistent memory methods allow systems to reconstruct prior context using
external documents rather than internal state.  
Implementations vary but share common characteristics: persistence, interpretive
coherence, and extensibility.

## Appendices
Appendix A: Terminology  
Appendix B: Related documents
```

---

# 6. Non-Normative Status

The examples above illustrate possible document-based memory formats. 
They do **not** prescribe:

- required syntax 
- required fields 
- structural constraints 
- update rules 

Any persistently stored text that enables consistent interpretation qualifies as a document-based memory file under MetaMemoryArchitecture.

Implementations remain free to adopt any structure that suits their purpose.
