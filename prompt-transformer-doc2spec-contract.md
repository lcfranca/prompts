# Transformation Contract: transformer-doc2spec

## 1. Metadata & Declaration

| Field       | Value                                                                                                                                                  |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ID          | urn\:prompt\:transformer\:doc2spec:1.0.0                                                                                                               |
| Version     | 1.0.0                                                                                                                                                  |
| Domain      | transformer                                                                                                                                            |
| Task        | doc2spec                                                                                                                                               |
| Description | Transform natural language documentation into a compact, lossless, machine-readable specification optimized for AI agent execution and interpretation. |
| Author      | \[Lucas]                                                                                                                                               |

## 2. Transformation Specification

### 2.1. Formal Objective

To process natural language documentation into a formal specification that is maximally dense, context-retentive, and suitable for direct interpretation by machine agents within limited token contexts.

### 2.2. Input Schema (Source)

* **Type:** Unstructured Text (Natural Language), Markdown
* **Constraints:**

  * Must contain full process/system/behavioral documentation, with embedded business logic and functional descriptions.
  * Must be context-complete (i.e., include all implicit assumptions or dependencies).
  * Avoid metaphor, emotion, or anthropocentric language unless clearly marked as contextual constraints.
* **Example:**

  > "Users can create, edit, and delete notes. Only the owner of a note may modify it. Admins have full read access to all notes."

### 2.3. Output Schema (Target)

* **Type:** Formal Specification (JSON-LD, OWL2-DL, TPTP logic, Markdown)
* **Constraints:**

  * Must encode all original semantics with zero information loss
  * Must follow entropy-optimized symbolic compression
  * No undefined terms, ambiguous constructs, or redundant expressions
* **Example:**

```json
{
  "entities": [
    {"type": "User", "permissions": ["create", "edit", "delete"]},
    {"type": "Note", "ownership_rule": "only owner can modify"},
    {"type": "Admin", "permissions": ["read_all"]}
  ]
}
```

### 2.4. Preconditions

* Input must be well-formed, with paragraphs representing independent units of meaning.
* Any domain-specific terms must be internally or externally definable.

### 2.5. Postconditions (Guarantees)

* The output must preserve all semantic content
* The result must be interpretable by symbolic reasoners or AI agents
* The output must be syntactically valid in its formal representation

## 3. Operational Protocol (Agentic Instructions)

### 3.1. Cognitive Strategy

Iterative Refinement + Compression-Oriented Decomposition + Formal Encoding

### 3.2. Execution Steps

#### Transformation Pipeline Requirements:

* **Phase 1 – Ingestion:**
  Normalize text input, resolve informal constructs.

* **Phase 2 – Semantic Grounding:**
  Map entities, actions, and constraints to a formal ontology or symbol space.

* **Phase 3 – Interpretation & Decomposition:**
  Split into discrete rule sets, ownership structures, access control logic, and process flows.

* **Phase 4 – Synthesis:**
  Compile specification components into compact, symbolic expressions.

* **Phase 5 – Validation:**
  Ensure the output satisfies all postconditions; no ambiguity or loss of fidelity.

* **Phase 6 – Correction Loop (if needed):**
  Regenerate invalid parts with correction metadata.

### Additional Step Logic

* **Step 1: Entity Extraction**

  * **Action:** Identify and label all domain-specific nouns and roles.
  * **Rationale:** Establish entity vocabulary for grounding logic.

* **Step 2: Action/Rule Decomposition**

  * **Action:** Extract permission rules, constraints, and relationships.
  * **Rationale:** Each should be encoded as logic/ontology predicates.

* **Step 3: Specification Assembly**

  * **Action:** Compile formal logic representation with minimal token overhead.
  * **Rationale:** Create a valid, dense, interpretable output.

* **Validation & Refinement (Self-Correction Loop):**

  * **Action:** Validate against schema/ontology and logical soundness.
  * **If any check fails:** Iterate with revised components.

## 4. Schema & Encoding Bindings

### 4.1. External References

* JSON Schema: [https://schema.org/SoftwareApplication](https://schema.org/SoftwareApplication)
* OWL2-DL: [http://www.w3.org/TR/owl2-overview/](http://www.w3.org/TR/owl2-overview/)

### 4.2. Target Formalism

* **Language:** OWL2-DL, JSON-LD, TPTP, Markdown
* **Syntax/Schema:** Manchester Syntax, JSON Schema v7, TPTP FO logic

## 5. Illustrative Example (Unit Test)

### 5.1. Input Instance

> "Each registered user can upload files. Files can be shared with specific users. Only the file owner can delete them."

### 5.2. Expected Output Instance

```json
{
  "entities": [
    {"type": "User", "permissions": ["upload"]},
    {"type": "File", "rules": [
      {"condition": "shared_with_specific_users"},
      {"ownership": "delete_by_owner_only"}
    ]}
  ]
}
```
