# Transformation Contract: [Domain]-[Task]

## 1. Metadata & Declaration

| Field       | Value                                                                 |
|-------------|-----------------------------------------------------------------------|
| ID          | urn:prompt:[Domain]:[Task]:[Version]                                  |
| Version     | [e.g., 1.0.0]                                                         |
| Domain      | `[transformer                                                         |
| Task        | [A concise, kebab-cased identifier for the specific task]             |
| Description | [A formal description of the deterministic transformation from Source to Target, including the overall goal and context.] |
| Author      | [Author/Team Name]                                                    |

## 2. Transformation Specification

### 2.1. Formal Objective
To process a Source input according to this contract and produce a Target artifact that is syntactically valid, semantically consistent, and verifiably correct against the specified Postconditions.

### 2.2. Input Schema (Source)
- **Type:** [e.g., Unstructured Text, JSON, YAML, XML, Formal Expression]  
- **Constraints:**  
  [List all structural, semantic, or content-based constraints the input must satisfy.]  
  [e.g., "Input JSON must validate against the UserProfile schema."]  
  [e.g., "Narrative must describe a complete, non-ambiguous process."]  
- **Example:**  
  [Provide a clear, representative example of a valid input instance.]

### 2.3. Output Schema (Target)
- **Type:** [e.g., JSON, YAML, Markdown, Source Code, Formal Expression]  
- **Constraints:**  
  [List all constraints the output must satisfy.]  
  [e.g., "Must adhere to the specified Target Formalism."]  
  [e.g., "All generated identifiers must be unique."]  
- **Example:**  
  [Provide a clear example of the expected output for the input example above.]

### 2.4. Preconditions
[List all conditions that must be true before execution.]  
[e.g., "The AI agent must have access to the API definitions specified in Section 4."]  
[e.g., "The input data must be pre-validated and well-formed."]

### 2.5. Postconditions (Guarantees)
[List the non-negotiable guarantees the output must provide.]  
[e.g., "The output is syntactically valid according to the Target Formalism."]  
[e.g., "The output contains no undefined terms or unresolved references."]  
[e.g., "The transformation is information-preserving (for translator tasks) or logically sound (for reasoner tasks)."]

## 3. Operational Protocol (Agentic Instructions)

### 3.1. Cognitive Strategy
[e.g., Deductive Chain-of-Thought (CoT) with Self-Correction, Analogical Reasoning, Iterative Refinement, Divide and Conquer]

### 3.2. Execution Steps

#### Transformation Pipeline Requirements:
The agent must execute the transformation via the following pipeline phases:
- **Phase 1 – Ingestion:**  
  Parse and normalize the raw source input, resolving any encoding ambiguities or malformed symbols.

- **Phase 2 – Semantic Grounding:**  
  Anchor all entities, concepts, and relations in formal schemas as defined in Section 4.

- **Phase 3 – Interpretation & Decomposition:**  
  Break down the input into logical components based on task intent, data types, and domain-specific constraints.

- **Phase 4 – Synthesis:**  
  Reconstruct the elements into the Target artifact structure, ensuring fidelity to all schema rules and task goals.

- **Phase 5 – Validation:**  
  Assess the constructed output against all Postconditions and Output Schema requirements.

- **Phase 6 – Correction Loop (if needed):**  
  Regenerate components with explicit correction notes for any invalidated artifacts, until the output conforms fully.

### Additional Step Logic
- **Step 1: [First Logical Action]**  
  - **Action:** [Describe the action, e.g., "Decompose the input query into its constituent semantic parts (intent, entities, constraints)."]  
  - **Rationale:** [Explain why this step is necessary.]

- **Step 2: [Second Logical Action]**  
  - **Action:** [e.g., "For each entity, ground it against the schemas defined in Section 4."]  
  - **Rationale:** [e.g., "To ensure all terms are unambiguous and formally defined before use."]

- **Step N: [Final Construction/Synthesis Action]**  
  - **Action:** [e.g., "Synthesize the processed components into the final Target artifact, adhering strictly to the Output Schema."]  
  - **Rationale:** [e.g., "To construct the final, valid output."]

- **Validation & Refinement (Self-Correction Loop):**  
  - **Action:** Validate the generated Target artifact against all Postconditions.  
  - **If any check fails:** Re-evaluate the preceding steps, explicitly noting the failure reason, and regenerate the artifact.

## 4. Schema & Encoding Bindings

### 4.1. External References
[List any required external schemas, ontologies, API definitions, or knowledge bases. Use standard formats like @prefix for ontologies or direct links for JSON Schemas.]  
[e.g., @prefix ex: [http://example.com/ontology/v1#](http://example.com/ontology/v1#)]  
[e.g., JSON Schema: [http://api.example.com/schemas/user.json](http://api.example.com/schemas/user.json)]

### 4.2. Target Formalism
- **Language:** [e.g., JSON, XML, OWL 2 DL, Python, Natural Language (EN-US)]  
- **Syntax/Schema:** [e.g., JSON Schema v7, Manchester, PEP 8, APA Style]

## 5. Illustrative Example (Unit Test)

### 5.1. Input Instance
[Provide a complete, self-contained input that serves as a clear test case.]

### 5.2. Expected Output Instance
[Provide the exact, correct output that should be generated from the Input Instance above. This pair serves as a definitive functional requirement.]
