# MetaMemoryArchitecture

MetaMemoryArchitecture defines a formal, file-based method for persistent
memory in large language model (LLM) systems.

It specifies how external documents — often structured in machine-oriented
formats such as JSON, but designed to remain human-readable and editable —
can function as durable, interpretable state that remains available across
sessions, runtimes, and model changes.

The method is independent of any specific LLM, provider, or execution
environment and forms the architectural foundation of the
MetaMemoryWorks ecosystem.

This repository documents the abstract method, its core principles, and
the associated specifications required to implement persistent memory
systems using MetaMemoryArchitecture.

---

## Purpose of the Method

Modern LLMs do not possess inherent long-term memory.
State is tied to individual interactions, tool calls, or execution
contexts and is typically lost once a session ends.

MetaMemoryArchitecture addresses this limitation by defining a method
for representing memory externally in a way that remains stable,
interpretable, and reusable over time.

By storing state in explicit files, the method enables persistence
beyond individual model invocations, allows system state to be
reconstructed deterministically, and decouples memory from any specific
model, provider, or runtime environment.

The same method supports both simple and complex setups, ranging from
single-file memory objects to multi-file and multi-subsystem
architectures. Because the structure of the memory is explicit, LLMs can
interpret it consistently rather than relying on implicit or transient
context.

As a result, MetaMemoryArchitecture can be used as a foundational memory
layer for personal assistants, OS-like subsystems, long-running
analytical workflows, synthetic personas, and other systems that require
durable, interpretable state.

---

## Scope of This Repository

This repository focuses on documenting the MetaMemoryArchitecture method
at an abstract and architectural level.

It describes the principles, constraints, and structural conventions
that define the method. Concrete applications of the architecture — including working systems,
examples, and domain-specific structures — are documented in separate
MetaMemoryWorks module repositories (such as scanOS, noteOS, or
trainingOS).

This separation is intentional. The purpose of this repository is to
serve as a stable reference for the method itself, independent of any
particular implementation or use case.

---

## Core Principles of the Memory Architecture

The MetaMemoryArchitecture method is built around a small set of
foundational principles that define how persistent memory is represented,
interpreted, and evolved over time.

### 1. External files as primary memory

All persistent memory is stored in external, user-controlled files.
These files constitute the system’s ground-truth state and exist
independently of any LLM’s internal or transient context.

The language model does not “own” the memory. It reads, interprets, and
operates on state that is explicitly represented outside the model itself.

### 2. Two valid classes of memory files

The method supports two independent and equally valid classes of
persistent memory files. Either class can be used on its own, or both can
be combined within the same system.

#### A) Structured log memory files

Structured log files are designed for chronological or incremental data,
such as training records, nutrition logs, measurements, or activity
histories.

Depending on the use case, such files may include elements like metadata,
entry identifiers, append-only constraints, consistency markers, or
validation segments. None of these elements are mandatory. Any
functionally equivalent structure that preserves interpretable state over
time is considered a valid instance of the method.

#### B) Document-based memory files

Document-based memory files store structured or semi-structured data
objects, such as engines, personas, profiles, scenes, parameters, contracts, or
notes.

These files may contain hierarchical structures, semantic fields, or
embedded contextual relationships. They do not require identifiers,
logging semantics, or normalization rules. Their only requirement is that
they provide a purpose-appropriate layout that allows an LLM to interpret
their content consistently.

Some document-based memory files may give rise to emergent interpretive
effects when used in combination, but such effects are incidental rather
than required.

### 3. Interpretive ability

MetaMemoryArchitecture does not prescribe or constrain the internal
mechanisms of language models. Instead, it defines external structures
that enable models to interpret memory consistently, reconstruct working
state from files, and align multiple memory objects or subsystems in a
coherent manner.

Determinism is provided by the procedure and the structure of the memory,
not by the model itself.

### 4. Single-file and multi-file architectures

The method supports a range of architectural layouts, including
single-file systems in which one document represents the full memory,
multi-file systems composed of several memory objects, and
multi-subsystem setups in which multiple domain-specific modules coexist.

These modes are alternatives, not requirements. Routing layers,
templates, namespaces, or update engines may be used when helpful, but
they are never mandatory components of the method.

### 5. Format-agnostic and system-agnostic design

Memory files may exist in a wide range of formats, including structured
formats such as JSON or YAML, semi-structured text formats, or
OCR-derived representations.

The architecture is independent of model type, vendor, runtime
environment, execution context, or integration strategy. Memory remains
portable and interpretable across systems and over time.

---

## High-Level Procedure

MetaMemoryArchitecture defines a conceptual procedure that describes how
persistent memory is read, interpreted, and evolved over time. The steps
outlined below describe the method at an abstract level rather than a
specific implementation or execution engine.

**Read.**  
Memory files are made available to the language model as part of its
working context. Depending on size and structure, files may be read in
full or in segments. Structural incompleteness or inconsistencies can be
detected at this stage, but the method does not mandate a particular
reading strategy.

**Validate.**  
Validation depends on the class of memory file. Structured log files may
be checked for elements such as metadata, identifiers, or consistency
markers, while document-based memory files typically rely on their
semantic structure alone. Validation is procedural rather than enforced
by a fixed schema.

**Reconstruct.**  
Based on the available memory files, the LLM reconstructs working state
or contextual meaning. This reconstruction is interpretive: the model
derives its effective state from the structure and content of the files,
not from hidden internal memory.

**Extend.**  
When memory is updated, the procedure distinguishes between file classes.
Log-based memory is typically extended through new entries, while
document-based memory files are not modified in place. Instead, they may
serve as templates for generating updated versions or new related
documents.

**Persist.**  
The resulting memory is written back as a new stable external state.
Once persisted, it becomes part of the durable context available to
future sessions, restarts, or model changes.

These steps describe the logical flow of the method. They intentionally
do not prescribe tooling, execution order, or implementation details.

---

## Components of the Architecture

MetaMemoryArchitecture is composed of a small number of conceptual
components that together define how persistent memory is represented
and used.

At its core are memory objects, which may take the form of structured
logs or document-based files and serve as durable representations of
state. These objects are shaped by structuring patterns such as schemas,
templates, or informal conventions that make their content interpretable
to an LLM.

Depending on the use case, memory may be normalized or left intentionally
unconstrained. Normalization is optional and applied only when it
improves clarity or consistency, not as a requirement of the method.

Processing rules govern how different kinds of memory are interpreted.
Log-based memory follows deterministic update and interpretation rules,
while document-based memory relies on structural and semantic coherence.

Memory objects can be grouped into subsystems that represent coherent
domains or workflows, such as training, work, or planning. When multiple
memory layers or subsystems interact, higher-level or emergent behavior
may arise as a side effect, but such behavior is neither assumed nor
required.

---

## What This Architecture Enables

By externalizing memory into explicit, durable files,
MetaMemoryArchitecture makes it possible to build LLM-based systems that
retain coherence over time instead of resetting with each interaction.

In practice, this enables assistants that can accumulate knowledge,
maintain context across sessions, and participate in long-running
workflows without relying on hidden internal state. It also supports
reproducible AI-driven processes, where prior decisions and intermediate
results remain inspectable and recoverable.

Because the method is modular and system-agnostic, it can serve as a
foundation for a wide range of applications, including personal
assistants, structured analytical workflows, synthetic personas,
narrative or planning systems, and multi-module setups that resemble
OS-like environments.

The architecture is designed to remain stable across runtimes and model
changes, allowing memory to persist even as execution environments or
language models evolve.

MetaMemoryArchitecture functions as the underlying memory layer for
several MetaMemoryWorks systems, including trainingOS, nutritionOS,
stageOS, personaOS, and related modules. Additional subsystems based on
the same method can be added without changing the core architecture.

---

## License

MetaMemoryArchitecture is provided under a restricted license.

The license permits free private and personal use and defines separate
terms for commercial or organizational use. It also specifies conditions
for derivative works, format or media adaptations, and excluded use
cases.

The full license text is available in the `/license/` directory of this
repository.

For licensing inquiries, please contact:
- licensing@metamemoryworks.com
- lizenz@metamemoryworks.de

---

## Disclaimer

This repository documents an architectural method for persistent memory
in LLM-based systems. It does not provide professional legal, medical, or
psychological advice.

---

## Contact

**Author:** Johannes Glaser  
**General contact:** contact@metamemoryworks.com / kontakt@metamemoryworks.de
