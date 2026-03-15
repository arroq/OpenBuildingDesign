# OpenBuildingDesign

OpenBuildingDesign is a standard for AEC that maintains the same data from design through construction to operations, with all information attached to that data throughout the building's life. Human-readable files, version control friendly, and machine-parseable so anyone can build tools on top without proprietary software or licensing.

## The Problem

Buildings exist in disconnected representations across specification documents, 3D models, and drawing sets. When information changes in one system, manual updates are required across others. When projects transition from design to construction to operations, information is re-interpreted or re-entered rather than transferred as structured data. Facility owners receive document binders requiring manual searching rather than queryable databases.

Every phase transition loses data. Information generated during design exists somewhere—emails, model properties, spec text, meeting notes. By procurement, most of it gets re-entered by someone who wasn't in the room when it was generated. By construction, it happens again. By operations, critical information about installed products, warranties, and maintenance requirements is buried in PDFs on a shelf.

The industry cannot advance computationally while data remains locked in proprietary formats and prose paragraphs. AI cannot check code compliance against unstructured text. Automated fabrication cannot read specification intent from Word documents. Facility management systems cannot query warranties from PDF binders. The infrastructure layer must exist before the applications layer can be built.

## What OBD Provides

**Persistent element identity:** Same ID from design through operations. Wall gets placed, gets an ID. Spec requirements attach to that ID. Submittal goes against that ID. Inspector signs off against that ID. Owner queries that ID 20 years later for warranty information.

**Dual taxonomy:** Physical spatial elements (walls, beams, columns, equipment) and non-physical performance requirements (code mandates, constraints, metrics, calculations) operate in the same framework.

**Lifecycle properties:** Permanent vs temporary elements. Continuous vs triggered enforcement. Design vs construction vs operational phase differentiation.

**Data primacy:** Structured data is the source. Documents are generated from it. Requirements are typed fields, not prose paragraphs requiring human interpretation.

**Open governance:** CC0 licensing for data/schema, MIT for tooling. No proprietary dependencies. Anyone can build tools that read and write this format.

## AI and Automation Potential

Structured data enables what prose cannot:

**Training data:** Clean, tagged building element datasets for training construction-focused AI models. Current limitation: models train on text descriptions, not queryable element properties with verified relationships.

**Automated compliance checking:** Code requirements as typed fields mean AI can verify element properties against code mandates without parsing natural language. Fire rating requirement of 2 hours checks directly against wall assembly rating property.

**Fabrication automation:** Assembly definitions with parametric relationships generate shop drawings and CNC tooling paths. Current barrier: geometric intent buried in 2D drawings requiring human interpretation.

**Predictive maintenance:** Element lifecycle data with installation dates, product specifications, and warranty terms enables operational AI to predict failures and schedule maintenance before problems occur.

**Carbon accounting:** Material quantities tied to embodied carbon factors at element level means automated whole-building carbon calculation. Current process: manual quantity takeoff, manual carbon factor lookup, manual calculation.

This project removes the data infrastructure barrier preventing these applications. Not by building the applications—by providing the standardized data layer they all require.

## Text Format

Human-readable section-header based format. Version control friendly. 

## Current Status

**Alpha development** — not v1.0 ready

**Completed:**
-

**Not built:**
-

**Blocking v1.0:**
1. Spatial function taxonomy (requires IFC 4.3 investigation)
2. Open taxonomy selection (OmniClass Table 23 recommended)
3. Assembly composition approach (3 options, needs complex test case)

## Architecture

Minimal stable core inspired by open OS kernels.

**Kernel defines:**
- Element identity schema
- Classification taxonomy
- Typed requirement field structure
- Cross-layer linkages

**Kernel does NOT define:**
- Document appearance
- Visualization rendering
- Contract language
- Tool-specific implementations
- Fabrication system interfaces

Extension namespace mechanism allows regional/specialty forks without core modification.

## Four Data Layers

**Layer 1: Specification Schema**
- Open hierarchical classification (independent of MasterFormat)
- Requirements as typed data fields (not prose)
- Cross-reference to UFGS public domain content

**Layer 2: Drawing and Document Schema**
- Sheets generated from spatial model + element data
- Version control at data level (revision = diff between states)

**Layer 3: Spatial Element Model** *(kernel scope)*
- Typed spatial objects with persistent IDs
- Minimal geometry (coordination only, not fabrication)
- Spec section references define assembly
- Properties attach to persistent ID throughout lifecycle

**Layer 4: Asset Record**
- Same data object from design through operations
- Construction fields populated during build
- Queryable database replaces document closeout
- Warranty, maintenance, product data attached to element IDs

## Target Adoption

**Initial sectors:**
- Fabrication-intensive construction (steel, precast, curtain wall)
- Modular and systems-based building
- Institutional owners wanting open asset data at closeout
- Computational workflows where legacy formats inadequate

**Not targeting initially:**
- Contract layer replacement (MasterFormat stays for contracts, OBD handles data/asset management in parallel)
- Traditional design-bid-build contracts

## Roadmap

**v1.0 Success Metrics:**
- All CSI divisions represented
- All lifecycle phases represented
- Complex assemblies successfully defined
- Performance requirements from actual code sections
- External contributor creates valid element without assistance
- Parser handles all cases
- Visualizer scales to 100+ elements
- IFC export pathway documented

## Contributing

Contribution workflow documentation in development.

Element creation requires:
- Unique ID assignment (collision prevention mechanism pending)
- Required sections validation
- Reference validation (element IDs must exist)
- Lifecycle validation (phase/duration/enforcement combinations)

## Development Transparency

This project is being developed with AI assistance (Claude by Anthropic) as a core development tool. Architecture decisions, documentation, and code are human-directed with AI augmentation. All development notes, decision logs, and iteration history are maintained in project files for full transparency.

The use of AI in this project is intentional—demonstrating that structured data formats enable AI-assisted development while proprietary prose formats resist it. If this kernel can be built with AI assistance, so can the ecosystem tools that will use it.

## License

Dual licensing:
- **Data/Schema:** CC0-1.0 Universal (public domain dedication)
- **Tooling Code:** MIT License

See `LICENSE.md` for details.

## Why Now

Computational workflows already dominant in fabrication-intensive construction. Gap between prose specifications and machine requirements already painful. BIM adoption widespread but painful—everyone feels modeling overhead, geometry fragility, coordination burden.

Open source governance models proven at scale (Linux kernel, Wikipedia, OpenStreetMap). Public domain content available (UFGS—don't need to write 27,000 specification requirements from scratch, need to reorganize and structure existing content).

Technology trivial—text format, simple parser, basic validation. Complexity is governance, adoption strategy, ecosystem building.

Window of opportunity: Before next proprietary standard entrenches.
