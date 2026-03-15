# OpenBuildingDesign

An open standard for building information. Plain text files that describe building elements — what they are, what they must do, and how they connect — from first design decision through the life of the building.

No proprietary software. No license fee. Open in any text editor on any device.

-----

## The Problem

Every building element exists in at least three places at once — a specification document, a 3D model, and a drawing set. None of them know about each other. The knowledge connecting them lives in the head of whoever is managing the project. When that person leaves, the knowledge leaves with them.

This is not a workflow problem. Every system in AEC was designed to produce a document. None were designed to share a building element’s identity across its full lifecycle.

The result plays out the same way on every project. Information generated during design gets re-entered by procurement. Re-entered again by construction. By the time an owner takes the building, what was installed, what the warranties cover, and what needs maintenance is buried in a binder on a shelf. The information was created. It was never preserved in a form that survives a handoff.

The current standards stack — MasterFormat, NCS, AIA documents — was designed for paper. Requirements and performance criteria buried in prose paragraphs cannot be automatically checked, queried by software, or preserved across phase transitions. Almost all of it is proprietary. OBD is CC0. No owner. No fee. Anyone can read it, write it, and build tools on top of it without asking permission.

-----

## What It Looks Like

One file per element type. Plain text.

```
NAME
8 inch CMU exterior wall

PROPERTIES
thickness 8 inches
fire rating 2 hours

MATERIALS
CMU block
mortar type S

RELATIONSHIPS
PART OF building envelope
SATISFIES 2-hour fire rating requirement
SPECIFIED IN section 04 22 00

LOG
2026-03-15   created from construction documents
```

The same file the architect creates in design is the file the contractor reads during construction, the inspector signs off against, and the facility manager queries twenty years later. The data does not reset at phase transitions. It accumulates.

-----

## What OBD Provides

**Persistent records.** Every element type has a structured file that travels with it from design through operations. All information — requirements, materials, relationships, inspection records, warranty data — attaches to that file.

**Open format.** Plain text. Version controlled in git. Any program can read it. Any person can edit it. No software lock-in.

**Structured requirements.** Performance criteria as typed fields, not prose paragraphs. A fire rating is a value, not a sentence. Software can read it, check it, and act on it.

**Lifecycle continuity.** One record per element type from design through demolition. Nothing gets re-entered. Nothing gets lost in a handoff.

-----

## Status

Early development. Not v1.0.

What exists: file format, relationship vocabulary, initial project simulation underway.

What is not built yet: tools to read and check files automatically, element library beyond initial samples.

What is blocking v1.0: how elements are classified, how assemblies are defined.

All development is documented session by session in [Discussions](https://github.com/arroq/OpenBuildingDesign/discussions) — decisions made, things rejected, and open questions included. That is the right place to understand where things stand.

-----

## Contributing

Contribution workflow is being established. The best place to start is [Discussions](https://github.com/arroq/OpenBuildingDesign/discussions). Read the development reports, understand the open questions, and open an issue or join a discussion.

-----

## License

- Data and schema: CC0-1.0 (public domain)
- Tooling: MIT

-----

## Development

Developed with AI assistance (Claude, Anthropic). Human-directed. Every session is published in full in [Discussions](https://github.com/arroq/OpenBuildingDesign/discussions) including dead ends, rejected ideas, and unresolved questions. The development process is transparent by design.