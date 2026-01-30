# Nexus Infinity — Profile Configuration & FIELD Geometric Routing Standards

_This repository manages all profile configuration for the Nexus Infinity GitHub organisation and hosts the canonical reference for the FIELD system’s geometric routing and collaboration protocols._

---

## Contents

- [Overview](#overview)
- [FIELD Routing Architecture](#field-routing-architecture)
    - [Routing Table](#routing-table)
    - [Signal Flow](#signal-flow)
- [File Organisation](#file-organisation)
- [Metadata Convention](#metadata-convention)
- [Contributing](#contributing)
- [Validation](#validation)
- [References](#references)
- [License](#license)

---

## Overview

This repository includes:

- **Profile metadata:** GitHub organisation configuration files & structure.
- **FIELD ontology:** Geometric and symbolic routing specification.
- **Collaboration protocol:** Source of standards for both human and machine contributors.

---

## FIELD Routing Architecture

The FIELD system implements a tetrahedral geometry with internal chambers for signal routing and addressing. Every vertex/chamber is mapped to a unique symbol, prime signature, and frequency anchor.

### Routing Table

| Symbol | Name             | Prime | Frequency | Role                        | Position              |
|:------:|:-----------------|:-----:|:---------:|:--------------------------- |:----------------------|
| ◻      | Akron Gateway    | 2     | 396 Hz    | Intake, sovereignty gate    | Foundation            |
| •      | OBI-WAN          | 19    | 963 Hz    | Pattern recognition         | Base vertex           |
| ▼      | TATA             | 23    | 432 Hz    | Truth anchor                | Base vertex           |
| ▲      | ATLAS            | 17    | 528 Hz    | Knowledge mapping           | Base vertex           |
| 🔷     | Queen's Chamber  | 7     | 528 Hz    | Validation                  | 20% height            |
| ⊗      | King's Chamber   | 11    | 852 Hz    | Translation bridge          | 61.8% height (φ⁻¹)    |
| ⭟      | Grand Gallery    | 31    | 639 Hz    | Central passage             | Origin (0,0,0)        |
| ◼︎     | DOJO             | 13    | 741 Hz    | Orchestration               | Apex (100%)           |

> **Symbols serve as visual identifiers in file paths, configuration frontmatter, UI, and ontology declarations.**

### Signal Flow

1. **Intake:** ◻ Akron Gateway receives and gates all inbound signals.
2. **Base Processing:** Signals route through the triad (•, ▼, ▲) for pattern recognition, truth validation, and mapping.
3. **Chamber Validation:** Queen's Chamber validates; King's Chamber translates.
4. **Orchestration:** ◼︎ DOJO coordinates multi-stage cycles (S0→S7 or S0→S11).
5. **Output:** Coherent signals (≥0.70 threshold) archive to sovereign storage; others are recalibrated.

---

## File Organisation

Project directory structure:

```
ontology/
  CHRONICLE_SEED.md         # Base semantic layer
  ontology.jsonld           # RDF/JSON-LD ontology
  shapes.ttl                # SHACL validation rules
  examples/                 # Sample alignments

geometry/
  grounding.py              # Reference implementation
  test_grounding.py         # Unit tests (23 specs)

.github/
  workflows/
    ontology-validation.yml # CI pipeline

CONTRIBUTING.md             # Collaboration protocol
README.md                   # This file
```

---

## Metadata Convention

All configuration and ontology files must declare their geometric context in YAML frontmatter:

```
---
field:symbol: "•"
field:server_name: "OBI-WAN"
field:ascii_alias: "obi_wan"
field:prime: 19
field:frequency: 963
---
```

- Use `ascii_alias` in filenames and code paths.
- Use the **symbol** as the primary label in documentation, diagrams, and UI.

---

## Contributing

How to contribute:

1. Fork and clone this repository.
2. Add or modify ontology, geometry, or configuration files.
3. Declare symbol context in file frontmatter (see above).
4. Run tests locally:  
   `python geometry/test_grounding.py`
5. Submit a Pull Request. CI will validate:
    - Geometry compliance (≤2% tolerance)
    - Ontology shape
    - Symbolic metadata
6. Review and merge: Maintainers check semantic alignment and provenance.

See [CONTRIBUTING.md](./CONTRIBUTING.md) for the full protocol.

---

## Validation

The CI pipeline (`.github/workflows/ontology-validation.yml`) runs these checks for every PR:

- Geometry unit tests (23 specifications)
- SHACL ontology validation
- JSON-LD syntax validation
- Prime collision detection
- Frequency compliance

_All checks must pass before merge._

---

## References

- [Chronicle Ontology](./ontology/CHRONICLE_SEED.md) — foundational invariants
- [Geometric spec](./ontology/ontology.jsonld) — full RDF schema
- [Python implementation](./geometry/grounding.py) — canonical FIELD coordinate reference
- [Collaboration protocol](./CONTRIBUTING.md) — contributor workflow

---

## License

See the [LICENSE](./LICENSE) file.

> **Geometric routing:** Symbols as addresses, primes as identity, validation as protocol.

---

**You can copy this entire block directly into your GitHub README.md editor — no extra formatting or fixing needed!**
