# 📘 README.md — MetaMemoryArchitecture
**Version: v1.0** 
**Copyright (c) 2025 — Johannes Glaser** 
**Contact: johannes.glaser@metamemoryworks.de**

## 🧠 Overview

**MetaMemoryArchitecture** is a file-based, persistent memory method for large language models (LLMs) and agentive AI systems. 
It defines:

- a **procedure** (the abstract, reproducible method), and 
- a **product** (the concrete structures, formats, and engine logic that enable the method).

The architecture enables LLMs to interpret external documents as stable memory instances, allowing consistent behavior across sessions, tools, runtimes, and models.

This repository documents the procedure, the system design, the associated formats, and the full prior art required to establish authorship and method protection.

A separate license file governs usage.

## 🎯 Purpose of the Method

Modern LLMs lack inherent long-term memory. 
MetaMemoryArchitecture provides:

1. **Persistence** — memory survives beyond any single model invocation. 
2. **Reproducibility** — state can be reconstructed deterministically from files. 
3. **Cross-system stability** — the memory layer works across models, APIs, runtimes, and environments. 
4. **Modularity** — the architecture supports single-file and multi-file memory systems. 
5. **Interpretive consistency** — the structure of the files enables an LLM to interpret them coherently.

The method is suitable for personal assistants, OS-like subsystems, multi-agent setups, synthetic personas, and a wide range of structured knowledge applications.

## 🧱 Core Principles of the Memory Architecture

### 1. External files as primary memory

Memory is stored in external, user-controlled files. 
These files act as ground-truth state, independent of the LLM’s internal context.

### 2. Two valid classes of memory files

The procedure supports two independent and equally valid classes of persistent memory files:

#### A) Structured Log Memory Files
Designed for chronological data (e.g., nutrition, training, sleep, measurements). 
They *may*, but do not have to, include:

- metadata (version, schema, last entry, status) 
- identifiable or sequential entry IDs 
- append-only constraints 
- EOF consistency markers 
- validation segments 

Any functionally equivalent variant is part of the method; none of these elements are mandatory.

#### B) Document-based Memory Files
Files storing structured or semi-structured data objects (e.g., personas, profiles, scenes, parameters, contracts, notes). 
These files:

- may contain hierarchical or nested structures, 
- may contain semantic fields (traits, goals, styles, rules), 
- may include relational elements or embedded contexts, 
- may — but do not have to — produce emergent interpretive effects when used by an LLM, 
- do *not* require IDs, logs, metadata, or normalization.

The only requirement is that they provide a **purpose-appropriate data layout** that an LLM can interpret consistently.

Either class alone, or both in combination, constitutes a valid implementation of the method.

### 3. Interpretive ability

The method does not prescribe or constrain LLM internals. 
Instead, it defines file structures that **enable** an LLM to:

- interpret content consistently, 
- reconstruct states from memory files, 
- and align multiple memory files or subsystems coherently.

Determinism lies in the procedure, not in the model.

### 4. Single-file and Multi-file architectures (OR, not AND)

The architecture supports:

- **single-file systems** (a single document is the full memory), 
- **multi-file systems** (a subsystem uses multiple memory objects), 
- **multi-subsystem systems** (several OS-modules coexist), 
- optional cross-file or cross-system emergence.

Any of these modes qualifies as use of the method.

Routing layers, templates, namespaces, or update engines **may** be used but are never required.

### 5. Format-agnostic and system-agnostic design

Memory files may exist in any format, including:

- JSON 
- TXT 
- Markdown 
- YAML 
- TOML 
- proprietary formats 
- OCR-derived text 
- future formats 

The architecture is independent of:

- model type 
- vendor 
- API or runtime 
- local or cloud execution 
- toolchain or integration method

## ⚙️ High-Level Procedure Description

### Step 1 — Read
Memory files are read in full or in chunks; incomplete structures may be detectable.

### Step 2 — Validate
Depending on file class: 
- logs may validate metadata, IDs, or EOF markers; 
- documents may rely on semantic structure alone.

### Step 3 — Reconstruct
The LLM reads or interprets the file to reconstruct state or contextual meaning.

### Step 4 — Extend (if applicable)
Logs append new entries; document-based memory files are not edited directly but may serve as templates for generating updated or modified versions, or for producing new related objects.

### Step 5 — Persist
The updated memory becomes a new stable external state.

These steps describe the **method**, not a specific implementation.

## 🧩 Components of the Architecture

- **Memory Objects** — logs or documents representing persistent knowledge. 
- **Structuring Patterns** — templates, schemas, or informal structural conventions. 
- **Normalization Approaches** — optional; used when beneficial, not required. 
- **Processing Rules** — deterministic for logs; structurally interpretive for documents. 
- **Subsystems** — coherent groups of memory files (e.g., trainingOS, workOS). 
- **Emergent Behavior** — optional side-effect of interacting memory layers.

## 🗂 Repository Structure

```
/specification/
    method_spec.md
    file_classes.md
    engine_principles.md

/format/
    json_examples.md
    txt_examples.md
    document_examples.md

/prior_art/
    development_history.md

/license/
    (Restricted License will be placed here)

/examples/
    sample_log_files/
    sample_document_files/

README.md
```

## 🚀 What This Architecture Enables

- persistent personal assistants 
- reproducible AI workflows 
- synthetic personas and narrative engines 
- OS-like multi-module ecosystems 
- LLM-driven automation tools 
- agent systems with stable state 
- cross-runtime and cross-model continuity

The method is the foundational memory layer used in systems such as:

- **trainingOS** 
- **nutritionOS** 
- **stageOS** 
- **personaOS** 
- **workOS** 
- and future MetaMemoryWorks subsystems.

## 🔒 License Notice (placeholder)

A dedicated **MetaMemoryArchitecture Restricted License** will be provided in `/license/`. 
It covers:

- permitted personal use, 
- commercial licensing requirements, 
- derivative-work rules, 
- format- and media-shift applicability, 
- prohibited categories (e.g., harmful or military use).

## 🛡 Disclaimer

This method provides structural rules for persistent memory systems. 
It does not provide or replace professional legal, medical, or psychological advice.

## 📬 Contact

For licensing requests, collaboration, or commercial partnerships:

**Email:** johannes.glaser@metamemoryworks.de 
**Author:** Johannes Glaser
