# Harmonized Ontology for Regulatory Compliance (HORC)

HORC is a cross-domain ontology for representing **ISO international standards** and **EU binding acts** in a structured, machine-readable format, and allow for assessing regulatory compliance.

---

## What is HORC?

HORC harmonises two regulatory ontologies:
- One based on ISO International Standards using the [ISO/IEC Directives Part 2]([url](https://boss.cen.eu/media/yypjl3mn/iso_iec_directives_part2.pdf)): "Principles and rules for the structure and drafting of ISO and IEC documents ». 
- One based on EU binding legal acts using the [Joint Practical Guide]([url]eur-lex.europa.eu/content/techleg/KB0213228ENN.pdf) by the European Parliament, the Council and the Commission.

The harmonisation process has been carried out based on the [ISO 860 methodology on terminology harmonisation]([url](https://www.iso.org/fr/standard/40130.html)) with a choice for applying the least restrictive approach to preserve the expressiveness of both ontologies. This means the overlapping concepts were aligned and he unique elements from each ontologies were carry over to retain their full expressiveness.

The Harmonized Ontology for Regulatory Compliance (HORC) is designed to:
- Enable **Ontology-Based Information Extraction (OBIE)** from legal and standard documents.
- Align regulatory concepts across multiple legal sources.

The harmonized ontology is aim to represent regulatory and standardisation rules in a structured, high-level and machine-readable form. 
It support compatibility across both **ISO international technical standards** and **European binding legal acts**. 

The model built following the HORC are intended to support tasks as:
- Identifying all applicable rules from multiple sources for a given scenario or system.
- Tracking the origin and legal status of each rules to support compliance checks
- Linking Rules and concepts like Scope, Article or Definition from multiple sources.
- Mapping concepts from multiple sources and avoid duplication or contradiction in compliance checks.

---

## Ontology Overview

HORC includes:
- Core classes: `Normative_Document`, `Article`, `Provision`, `Rule`, `Scope`, `Limits_of_applicability`, `Objectively_Verifiable_Criteria`
- Key properties: `hasContent`, `hasNumbering`, `conveys`, `part_of_document`, `originates_from`
- Alignment logic that connects ISO and EU document structures into a common model.
- Support for traceability.

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
