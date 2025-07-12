# Prompt Index — Specification & Naming Guide

This document outlines the canonical structure, naming conventions, and taxonomic framework for AI prompt files in the `/prompts/` repository. Each prompt file defines a deterministic input-to-output transformation, categorized by its functional domain and thematic specialization.

---

## Prompt Naming Convention

Prompt files follow a standardized, machine-parsable naming structure:

`prompt-[domain]-[subdomain].md`

| Segment       | Constraint             | Description                                      |
|---------------|-----------------------|--------------------------------------------------|
| `prompt`      | Fixed Prefix          | Identifies the file as a prompt artifact.        |
| `[domain]`    | Enumerated Set        | Primary functional transformation class (see §2). |
| `[subdomain]` | Derived Label         | Thematic specialization within the domain.       |

**Constraints:**
- Use **lowercase**, **kebab-case** for all identifiers (e.g., `prompt-transformer-narrative2logic.md`).
- Ensure identifiers are **technology-agnostic** and **semantically clear**.
- Subdomains must reflect **functional intent**, not implementation details.

**Example**: `prompt-transformer-narrative2logic.md` converts descriptive prose into logical expressions.

---

## Functional Domain Taxonomy

Prompts are organized into five core domains, each defined by its transformation objective. Each domain specifies required input formats, expected outputs, and valid subdomains. Below, each domain is detailed with input/output profiles, constraints, and examples.

### 1. `transformer`
Transforms input data into a new structural representation, preserving semantic content for a different analytical or operational purpose.

- **Input Profile**:
  - **Source**: Existing artifacts (e.g., narrative prose, technical documents, user stories, schemas).
  - **Format**: Unstructured text, Markdown, or semi-structured data (e.g., lists, key-value pairs).
  - **Example Input**:
    ```markdown
    A customer submits a support ticket describing an issue with payment processing.
    ```
- **Output Profile**:
  - **Artifact**: Structured representation (e.g., formal specification, ontological map, semantic graph).
  - **Example Output**:
    ```markdown
    **Support Ticket Specification**  
    - **Entity**: Customer  
    - **Action**: Submits ticket  
    - **Issue**: Payment processing failure  
    - **Priority**: High
    ```
- **Valid Subdomains**:

  | Subdomain            | Input                        | Output                       |
  |----------------------|------------------------------|------------------------------|
  | `doc2spec`           | Technical Documentation       | Formal Specification         |
  | `concept2ontology`   | Conceptual Schema            | Ontological Encoding         |
  | `narrative2logic`    | Descriptive Prose            | Logical Expression           |
  | `text2graph`         | Unstructured Text            | Semantic Graph               |
  | `object2event`       | Object-Oriented Model        | Event-Oriented Model         |
  | `plan2protocol`      | Strategic Plan               | Operational Protocol         |

- **Example Filename**: `prompt-transformer-narrative2logic.md`

### 2. `generator`
Synthesizes new structured artifacts from minimal, high-level declarative inputs.

- **Input Profile**:
  - **Source**: Symbolic fragments, intent statements, or constraint sets.
  - **Format**: Natural language or formalized fragments.
  - **Example Input**:
    ```markdown
    Design a system supporting asynchronous communication with eventual consistency.
    ```
- **Output Profile**:
  - **Artifact**: Complete structured document (e.g., architecture blueprint, object model, query set).
  - **Example Output**:
    ```markdown
    **Architecture Blueprint**  
    - **Components**: Message Queue, Event Handler, Data Store  
    - **Consistency Model**: Eventual Consistency  
    - **Communication**: Asynchronous via Pub/Sub
    ```
- **Valid Subdomains**:
  | Subdomain        | Input                        | Output                       |
  |------------------|------------------------------|------------------------------|
  | `specification`  | Design Intent                | Formal Specification         |
  | `architecture`   | Requirements                 | Component Framework          |
  | `ontology`       | Domain Concepts              | Structured Ontology          |
  | `queryset`       | Semantic Goal                | Declarative Query Block      |
  | `policy`         | Constraints                  | Governance Rule Schema       |

- **Example Filename**: `prompt-generator-architecture.md`

### 3. `modeler`
Encodes abstract concepts or systems into formal, machine-interpretable models.

- **Input Profile**:
  - **Source**: High-level descriptions of domain knowledge, behaviors, or processes.
  - **Format**: Natural language, requirement lists, or conceptual diagrams.
  - **Example Input**:
    ```markdown
    Model a support ticket lifecycle from creation to resolution.
    ```
- **Output Profile**:
  - **Artifact**: Formal model (e.g., OWL ontology, UML/BPMN diagram, state-machine definition).
  - **Example Output**:
    ```markdown
    **Ticket Lifecycle Model**  
    - **States**: Created, Assigned, In Progress, Resolved  
    - **Transitions**: Create → Assign → Progress → Resolve
    ```
- **Valid Subdomains**:
  | Subdomain        | Input                        | Output                       |
  |------------------|------------------------------|------------------------------|
  | `ontology`       | Domain Knowledge             | Knowledge Map                |
  | `epistemology`   | Concepts                     | Conceptual Framework         |
  | `behavior`       | Requirements                 | Agent/System Behavior Model  |
  | `process`        | Steps                        | Workflow Abstraction         |
  | `dialogic`       | Use Case                     | Conversational Flow Model    |

- **Example Filename**: `prompt-modeler-process.md`

### 4. `reasoner`
Generates inferential chains or analytical judgments from facts, axioms, or observations.

- **Input Profile**:
  - **Source**: Structured facts, rules, hypotheses, or contextual data.
  - **Format**: Predicate logic, key-value pairs, or statement lists.
  - **Example Input**:
    ```markdown
    Facts: {Event A at T1, Event B at T2, T2 > T1}  
    Question: Did A cause B?
    ```
- **Output Profile**:
  - **Artifact**: Logical deduction, causal chain, diagnostic conclusion, or probability assessment.
  - **Example Output**:
    ```markdown
    **Causal Analysis**  
    - **Conclusion**: Insufficient evidence to confirm A caused B.  
    - **Reasoning**: Temporal precedence established, but no causal link provided.
    ```
- **Valid Subdomains**:
  | Subdomain        | Input                        | Output                       |
  |------------------|------------------------------|------------------------------|
  | `axiomatic`      | Axioms                       | Logical Deduction            |
  | `causal`         | Events/Facts                 | Cause-Effect Chain           |
  | `temporal`       | Time-based Facts             | Constraint Evaluation        |
  | `diagnostic`     | Symptoms                     | Fault Inference              |

- **Example Filename**: `prompt-reasoner-diagnostic.md`

### 5. `translator`
Transcodes information between technical representation formats while preserving semantics.

- **Input Profile**:
  - **Source**: Well-formed artifact (e.g., source code, ontology, database schema).
  - **Format**: Code, formal logic, OWL/Turtle, RDF/XML, or structured data.
  - **Example Input**:
    ```python
    class User:
        def __init__(self, name, email):
            self.name = name
            self.email = email
    ```
- **Output Profile**:
  - **Artifact**: Equivalent artifact in a target format (e.g., specification, JSON-LD, natural language).
  - **Example Output**:
    ```markdown
    **Technical Specification**  
    - **Entity**: User  
    - **Attributes**:  
      - Name: String  
      - Email: String
    ```
- **Valid Subdomains**:
  | Subdomain            | Input                        | Output                       |
  |----------------------|------------------------------|------------------------------|
  | `ontology2schema`    | Ontology (OWL)               | Structured Schema (JSON-LD)  |
  | `logic2text`         | Formal Logic                 | Natural Language Explanation |
  | `code2spec`          | Source Code                  | Technical Specification      |
  | `language2symbol`    | Text                         | Symbolic Structure           |

- **Example Filename**: `prompt-translator-code2spec.md`


## Contribution Guidelines

- **Prompt File Creation**:
  - Adhere to the naming convention and file structure above.
  - Validate subdomain alignment with the domain’s transformation objective.

- **Proposing New Domains**: 
  - A new functional domain may be proposed if it defines a transformation category that is functionally orthogonal to all existing domains while maintaining deterministic input-to-output logic.
  - Provide a detailed description, including input/output profiles and example subdomains.

- **Validation**:
  - Ensure prompts are technology-agnostic and reusable across contexts.
  - Test prompts with sample inputs to verify output consistency.
