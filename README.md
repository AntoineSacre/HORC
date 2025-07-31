# Harmonized Ontology for Regulatory Compliance (HORC)

HORC is a cross-domain ontology for representing and assessing regulatory and standardisation rules from **ISO international standards** and **EU binding legal acts** in a structured, machine-readable format.

---

## What is HORC?

The Harmonized Ontology for Regulatory Compliance (HORC) is designed to:
- Support **automatic compliance assessment** of software systems.
- Enable **Ontology-Based Information Extraction (OBIE)** from legal and standard documents.
- Integrate compliance reasoning directly into software development.
- Align regulatory concepts across multiple legal sources.

HORC harmonises two formally defined regulatory ontologies:
- One based on ISO international standards using ISO/IEC Directives Part 2.
- One based on EU binding legal acts using the Joint Practical Guide.

The harmonisation follows the ISO 860 methodology for terminology alignment, resolving both structural and semantic mismatches. The result is a unified OWL ontology compatible with both document types.

---

## Ontology Overview

HORC includes:
- Core classes: `Normative_Document`, `Article`, `Provision`, `Rule`, `Scope`, `Limits_of_applicability`, `Objectively_Verifiable_Criteria`, etc.
- Key properties: `hasContent`, `hasNumbering`, `conveys`, `part_of_document`, `originates_from`, etc.
- Alignment logic that connects ISO and EU document structures into a common model.
- Support for traceability and compliance reasoning.

The ontology is OWL-compliant and built using [Protégé](https://protege.stanford.edu/).

---

## Example

Sample instantiations are included for:
- **ISO/IEC 27001** — e.g., Clause 1 (Scope), Clause 4.1 (Context), applicability conditions.
- **EU Medical Device Regulation** (to be added, if applicable).

These can be found in the `/examples` folder.

---

## Installation and Usage

### Requirements
- [Protégé](https://protege.stanford.edu/) (recommended for editing/viewing)
- Any RDF/OWL-compatible reasoner or semantic tool (e.g. TopBraid, OWL API, RDF4J)

### Usage
1. Clone or download the repository.
2. Open `harmonized_ontology.rdf` in Protégé.
3. Browse the ontology class hierarchy and individuals.
4. Use SPARQL or reasoning tools to test compliance scenarios.

Example SPARQL query to list all rules:
```sparql
SELECT ?rule ?content
WHERE {
  ?rule a horc:Rule ;
        horc:hasContent ?content .
}
