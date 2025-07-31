# Harmonized Ontology for Regulatory Compliance (HORC)

HORC is a cross-domain ontology for representing **ISO international standards** and **EU binding acts** in a structured, machine-readable format, and allow for assessing regulatory compliance.

---

## What is HORC?

HORC harmonises two regulatory ontologies:
- One based on ISO International Standards using the [ISO/IEC Directives Part 2](https://boss.cen.eu/media/yypjl3mn/iso_iec_directives_part2.pdf): "Principles and rules for the structure and drafting of ISO and IEC documents ». 
- One based on EU binding legal acts using the [Joint Practical Guide]([url]eur-lex.europa.eu/content/techleg/KB0213228ENN.pdf) by the European Parliament, the Council and the Commission.

The harmonisation process has been carried out based on the [ISO 860 methodology on terminology harmonisation](https://www.iso.org/fr/standard/40130.html) with a choice for applying the least restrictive approach to preserve the expressiveness of both ontologies. This means the overlapping concepts were aligned and he unique elements from each ontologies were carry over to retain their full expressiveness.

The harmonized ontology is aim to represent regulatory and standardisation rules in a structured, high-level and machine-readable form. 
It support compatibility across both **ISO international technical standards** and **European binding legal acts**. 

The model built following the HORC are intended to support tasks as:
- Identifying all applicable rules from multiple sources for a given scenario or system.
- Tracking the origin and legal status of each rules to support compliance checks
- Linking Rules and concepts like Scope, Article or Definition from multiple sources.
- Mapping concepts from multiple sources and avoid duplication or contradiction in compliance checks.

---

## Ontology Overview

<img width="1143" height="567" alt="harmonized ontology" src="https://github.com/user-attachments/assets/33201701-8a0b-4fd9-b10e-bf4151996b0b" />

HORC includes:
- Core classes: `Normative_Document`, `Definition`, `Scope`, `Limits_of_applicability`, `Article`, `Provision`, `Rule`, `Objectively_Verifiable_Criteria`
- Alignment logic that connects ISO and EU document structures into a common model.
- Support for traceability.

The ontology is OWL-compliant and built using [Protégé](https://protege.stanford.edu/).

---

## Classes

- `Normative Document`: A document or act that sets out rules to be followed by its intended audience. Includes both ISO international standards and EU binding legal acts (e.g. EU regulations and directives). Content may be followed voluntarily or under legal obligation.
- `Article`: A structural unit of content. Articles are the smallest self-contained units, numbered continuously throughout the document. Called "clauses" in ISO standards. Can be subdivided into paragraphs or points.
- `Preamble`: All content between the title and enacting terms (e.g. introduction, citations, recitals).
- `Enacting Terms`: Normative part of the document, structured with articles. Includes normative references, scope, definitions, and provisions.
- `Annex`: Material too voluminous or technical to be included in the body of the enacting terms.
- `Normative References`: Documents cited in the text that form part of the document’s requirements.
- `Scope`: Defines the boundaries and applicability of the document. Describes subject, covered situations, audience, and limits.
- `Limits of applicability`: In ISO, statements like “This document is (not) applicable to …”
- `Definition`: Provides formal definitions for key terms.
- `Provision`: Articles with enforceable content and context for application (scope, conditions). Define what must/should/may be done.
- `Rule`: A type of provision prescribing obligations or prohibitions (e.g. "shall", "must"). Expressed as requirements (ISO) or rights/obligations (EU). May include conditions of applicability.
- `Objectively Verifiable Criteria`: In ISO, expectations expressed in a way that fulfilment can be confirmed with objective evidence.
- `Statement`: A non-binding expression, e.g. permission, possibility, capability.
- `Permission`: Indicates consent or freedom to act. Uses the verb "may".
- `Possibility`: Indicates an expected or possible outcome. Uses the verb "can".
- `Capability`: Indicates ability or suitability. Also uses "can".
- `Instruction`: Sentences written in the imperative mood.
- `Recommendation`: Suggests an appropriate action using “should” or “should not”.
- `External Constraint`: Obligations on the user not stated as provisions. Uses “must” (but not “must not”).
- `Procedural Provision`: Defines how rules should be implemented, applied, or enforced.

## Object Properties

- `part_of_document`: Links legal content to its regulatory document.
- `part_of_enacting_term`: Links normative content to enacting terms.
- `part_of`: Links articles to their containing entities.
- `part_of_annex`: Links provisions to the annexes expressing them.
- `indicates`: Links scope to its limits of applicability.
- `conveys`: Links rules to the objectively verifiable criteria they express.
- `originates_from`: Links limits of applicability to the article they originate from.

## Data Properties

- `title`: Title of the Normative Document.
- `hasContent`: Literal textual content of articles.
- `hasNumbering`: Supports traceability to article numbering.
- `hasLimits`: Content of the limits of applicability.
- `hasCriteria`: Criteria content within Objectively Verifiable Criteria.

---

## Example

Sample instantiations are included for:
- **ISO/IEC 27001**: Clause 1 (Scope), Clause 4.1 (Context), applicability conditions.
- **EU Medical Device Regulation**: ...

These can be found in the `/examples` folder.

---

## Installation and Usage

### Requirements
- [Protégé](https://protege.stanford.edu/) (recommended for editing/viewing)

### Usage
1. Clone or download the repository.
2. Open `harmonized_ontology.rdf` in Protégé.
3. Browse the ontology class hierarchy and individuals.
