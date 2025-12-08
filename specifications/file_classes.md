# File Classes Specification (v1.0)
**Part of MetaMemoryArchitecture** 
**Author:** Johannes Glaser 
**Contact:** johannes.glaser@metamemoryworks.de 
**Year:** 2025

## 0. Purpose

This document defines the two valid classes of memory files used within the MetaMemoryArchitecture method. 
A system implementing **either class alone**, or **both in combination**, constitutes a valid implementation of the method.

The classes are intentionally abstract, allowing the architecture to remain format-agnostic, system-agnostic, and future-proof.

---

# 1. Overview of Memory File Classes

MetaMemoryArchitecture recognizes two independent categories:

1. **Structured Log Memory Files** 
2. **Document-Based Memory Files**

These classes serve different functional purposes but are equally valid forms of persistent memory.

There is **no dependency** between them. 
They are connected by **logical OR**, not AND.

---

# 2. Structured Log Memory Files

Structured log files capture **sequential or chronological** information.

They may — but do not have to — include:

- metadata (e.g., version, schema, last entry, status) 
- identifiable or sequential entry IDs 
- append-only structures 
- EOF markers or other consistency signals 
- optional validation fields 
- normalization patterns (e.g., time series formats)

Any functionally similar sequential structure qualifies.

## 2.1 Purpose

Log memory files are used when:

- order matters, 
- entries accumulate over time, 
- reproducibility or analytics require stable increments, 
- or the subsystem (e.g., nutritionOS, trainingOS) benefits from deterministic extension.

## 2.2 Minimal Requirement

A log memory file must:

- contain data that can be *extended over time*, 
- in a way that preserves meaningful continuity for the system.

No specific schema, metadata, or ID format is required.

---

# 3. Document-Based Memory Files

Document-based memory files capture **structured or semi-structured** information used as persistent knowledge.

They may include:

- hierarchical or nested data 
- semantic fields (traits, rules, parameters, goals) 
- relational or contextual elements 
- narrative, descriptive, or declarative content 
- embeddings of styles, tendencies, constraints 
- free-form or lightly structured text 
- contracts, profiles, scenes, notes, policies 
- any purpose-appropriate representation

They do *not* require:

- IDs 
- metadata 
- normalization 
- consistency markers 
- deterministic update patterns 

Document-based memory files **may** exhibit emergent interpretive effects when used by an LLM, but this is optional and not required for compliance.

## 3.1 Purpose

Document memory files are used when:

- meaning does not depend on sequence, 
- the file serves as a template, identity, or long-term reference, 
- the content guides interpretation or behavior, 
- the subsystem (e.g., personaOS, workOS, stageOS) requires persistent semantic structures.

## 3.2 Minimal Requirement

A document-based memory file must:

- provide a **purpose-appropriate** data layout that an LLM can interpret consistently.

No other requirements apply.

---

# 4. Relationship Between File Classes

The two classes are:

- independent, 
- complementary, 
- and equally valid.

A system that uses:

- **only structured log files**, 
- **only document-based files**, or 
- **any combination of both**

is implementing the MetaMemoryArchitecture method.

Emergent interactions between files or subsystems **may** occur but are not required.

---

# 5. Format Independence

Both memory file classes apply equally to:

- JSON 
- TXT 
- Markdown 
- YAML 
- TOML 
- XML 
- OCR-derived text 
- proprietary formats 
- semi-structured text 
- free-form text 
- other and future formats

The method imposes **no constraints** on file format, parser, encoding, or tooling.

---

# 6. Summary

This specification defines the only two structural categories required for the MetaMemoryArchitecture method:

- **Structured Log Memory Files** 
- **Document-Based Memory Files**

No other memory classes are required or implied. 
Any persistent external file that satisfies the minimal conditions of either category 
qualifies as a memory object under the method.

