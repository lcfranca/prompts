# Transformation Contract: transformer-doc2roadmap

## 1. Metadata & Declaration

| Field       | Value                                                                                                                                                  |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ID          | urn\:prompt\:transformer\:doc2roadmap:1.0.0                                                                                                           |
| Version     | 1.0.0                                                                                                                                                  |
| Domain      | transformer                                                                                                                                            |
| Task        | doc2roadmap                                                                                                                                            |
| Description | Transform software documentation into a design-first, build-sequenced development roadmap with architectural patterns, file structure, and modular implementation steps. |
| Author      | \[Lucas]                                                                                                                                               |

## 2. Transformation Specification

### 2.1. Formal Objective

To process software documentation into a comprehensive development roadmap that provides:
- Initial filesystem blueprint using modern architectural patterns (DDD, Clean Architecture, Hexagonal)
- Sequential, modular, compilable development steps with explicit dependencies
- High specificity implementation guidance optimized for developer execution

### 2.2. Input Schema (Source)

* **Type:** Software Documentation (Natural Language, Markdown, Technical Specifications)
* **Constraints:**
  * Must contain functional requirements, system behavior, and technical constraints
  * Must include domain context, user interactions, and business rules
  * Should specify technology stack, external dependencies, and integration points
  * Must be sufficiently detailed to infer architectural decisions
* **Example:**
  > "Build a task management system where users can create projects, assign tasks to team members, track progress, and generate reports. The system should support real-time notifications and integrate with external calendar services."

### 2.3. Output Schema (Target)

* **Type:** Development Roadmap (Structured Markdown with YAML/JSON components)
* **Constraints:**
  * Must include complete filesystem structure with architectural justification
  * Must provide sequential development steps with isolated, testable units
  * Must specify exact file paths, function signatures, and data models
  * Must include dependency mapping and compilation order
  * Must be immediately actionable by development teams
* **Example:**
```markdown
## 🏗 Filesystem Blueprint
```
/src
  /domain
    /entities
    /repositories
    /services
  /infrastructure
    /database
    /external
  /application
    /commands
    /queries
    /handlers
```

## 📋 Development Steps
### Step 1: Domain Entities
**Files:** `/src/domain/entities/Task.ts`, `/src/domain/entities/Project.ts`
**Dependencies:** None
**Test Files:** `/tests/domain/entities/Task.test.ts`
```

### 2.4. Preconditions

* Input documentation must contain sufficient detail to infer system boundaries
* Technology stack must be specified or derivable from context
* Business rules and constraints must be clearly articulated
* External integrations and dependencies must be documented

### 2.5. Postconditions (Guarantees)

* The roadmap must be architecturally sound and follow established patterns
* Each development step must be independently compilable and testable
* File structure must support maintainability and extensibility
* Implementation guidance must be specific enough to minimize ambiguity

## 3. Operational Protocol (Agentic Instructions)

### 3.1. Cognitive Strategy

Architecture-First Analysis + Domain-Driven Decomposition + Sequential Build Planning

### 3.2. Execution Steps

#### Transformation Pipeline Requirements:

* **Phase 1 – Domain Analysis:**
  Extract core domain concepts, entities, and business rules from documentation.

* **Phase 2 – Architectural Planning:**
  Design filesystem structure using DDD, Clean Architecture, or Hexagonal patterns.

* **Phase 3 – Dependency Mapping:**
  Identify build order, module dependencies, and integration points.

* **Phase 4 – Step Decomposition:**
  Break implementation into modular, testable units with clear boundaries.

* **Phase 5 – Roadmap Assembly:**
  Compile structured roadmap with filesystem blueprint and sequential steps.

* **Phase 6 – Validation & Refinement:**
  Ensure architectural coherence and implementation feasibility.

### Additional Step Logic

* **Step 1: Domain Modeling**
  * **Action:** Extract entities, value objects, aggregates, and domain services
  * **Rationale:** Establish core domain vocabulary and bounded contexts

* **Step 2: Architecture Selection**
  * **Action:** Choose appropriate architectural pattern based on complexity and requirements
  * **Rationale:** Ensure long-term maintainability and testability

* **Step 3: Filesystem Design**
  * **Action:** Create directory structure reflecting architectural decisions
  * **Rationale:** Provide clear separation of concerns and module boundaries

* **Step 4: Build Sequence Planning**
  * **Action:** Order development steps by dependency and risk
  * **Rationale:** Enable incremental development and early validation

* **Step 5: Implementation Specification**
  * **Action:** Define exact file contents, interfaces, and test requirements
  * **Rationale:** Minimize implementation ambiguity and accelerate development

* **Validation & Refinement (Self-Correction Loop):**
  * **Action:** Validate architectural coherence and step feasibility
  * **If any check fails:** Iterate with revised components

## 4. Schema & Encoding Bindings

### 4.1. External References

* Domain-Driven Design: [https://martinfowler.com/bliki/DomainDrivenDesign.html](https://martinfowler.com/bliki/DomainDrivenDesign.html)
* Clean Architecture: [https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
* Hexagonal Architecture: [https://alistair.cockburn.us/hexagonal-architecture/](https://alistair.cockburn.us/hexagonal-architecture/)

### 4.2. Target Formalism

* **Language:** Structured Markdown with YAML/JSON components
* **Syntax/Schema:** CommonMark, YAML 1.2, JSON Schema v7

### 4.3. Roadmap Structure Template

```markdown
# 🚀 Development Roadmap: [Project Name]

## 🏗 Filesystem Blueprint
### Architecture Pattern: [DDD/Clean/Hexagonal]
### Technology Stack: [Languages/Frameworks]

```
[Directory Tree Structure]
```

## 📋 Sequential Development Steps

### Step N: [Step Name]
**Estimated Time:** [Duration]
**Dependencies:** [Previous Steps]
**Files to Create/Modify:**
- `/path/to/file.ext` - [Description]

**Implementation Requirements:**
- [Specific requirement 1]
- [Specific requirement 2]

**Function Signatures:**
```typescript
[Code signatures]
```

**Test Requirements:**
- Unit tests: `/tests/path/to/file.test.ext`
- Integration tests: [If applicable]

**Acceptance Criteria:**
- [Testable criterion 1]
- [Testable criterion 2]

---
```

## 5. Illustrative Example (Unit Test)

### 5.1. Input Instance

> "Create a library management system where librarians can add books, users can borrow and return books, and the system tracks due dates with automatic fine calculation. The system should send email notifications for overdue books."

### 5.2. Expected Output Instance

```markdown
# 🚀 Development Roadmap: Library Management System

## 🏗 Filesystem Blueprint
### Architecture Pattern: Domain-Driven Design with Clean Architecture
### Technology Stack: TypeScript, Node.js, Express, PostgreSQL

```
/src
  /domain
    /entities
      Book.ts
      User.ts
      Loan.ts
      Fine.ts
    /repositories
      BookRepository.ts
      UserRepository.ts
      LoanRepository.ts
    /services
      LoanService.ts
      FineCalculationService.ts
      NotificationService.ts
  /infrastructure
    /database
      PostgreSQLBookRepository.ts
      PostgreSQLUserRepository.ts
      PostgreSQLLoanRepository.ts
    /external
      EmailService.ts
  /application
    /commands
      BorrowBookCommand.ts
      ReturnBookCommand.ts
      AddBookCommand.ts
    /queries
      GetOverdueLoansQuery.ts
      GetUserLoansQuery.ts
    /handlers
      BorrowBookHandler.ts
      ReturnBookHandler.ts
  /presentation
    /controllers
      BookController.ts
      UserController.ts
      LoanController.ts
    /routes
      bookRoutes.ts
      userRoutes.ts
      loanRoutes.ts
```

## 📋 Sequential Development Steps

### Step 1: Domain Entities
**Estimated Time:** 2 days
**Dependencies:** None
**Files to Create/Modify:**
- `/src/domain/entities/Book.ts` - Core book entity with ISBN, title, author
- `/src/domain/entities/User.ts` - User entity with borrowing privileges
- `/src/domain/entities/Loan.ts` - Loan aggregate managing book borrowing
- `/src/domain/entities/Fine.ts` - Fine calculation and tracking

**Implementation Requirements:**
- All entities must be immutable with factory methods
- Loan entity must enforce business rules (max books per user, due dates)
- Fine entity must calculate overdue amounts based on configurable rates

**Function Signatures:**
```typescript
class Book {
  constructor(private readonly isbn: string, private readonly title: string, private readonly author: string) {}
  static create(isbn: string, title: string, author: string): Book
  isAvailable(): boolean
}

class Loan {
  static create(book: Book, user: User, dueDate: Date): Loan
  calculateFine(currentDate: Date): Fine
  isOverdue(currentDate: Date): boolean
}
```

**Test Requirements:**
- Unit tests: `/tests/domain/entities/Book.test.ts`, `/tests/domain/entities/Loan.test.ts`
- Test loan creation, fine calculation, and overdue detection

**Acceptance Criteria:**
- All entities validate input data and throw appropriate errors
- Loan entity correctly calculates overdue status and fines
- Book entity tracks availability status

---

### Step 2: Repository Interfaces
**Estimated Time:** 1 day
**Dependencies:** Step 1
**Files to Create/Modify:**
- `/src/domain/repositories/BookRepository.ts` - Interface for book persistence
- `/src/domain/repositories/UserRepository.ts` - Interface for user persistence
- `/src/domain/repositories/LoanRepository.ts` - Interface for loan persistence

**Implementation Requirements:**
- All repositories must use async/await patterns
- Repositories must define methods for CRUD operations
- Search methods must support filtering and pagination

**Function Signatures:**
```typescript
interface BookRepository {
  findByIsbn(isbn: string): Promise<Book | null>
  findAvailableBooks(): Promise<Book[]>
  save(book: Book): Promise<void>
}

interface LoanRepository {
  findOverdueLoans(): Promise<Loan[]>
  findByUser(userId: string): Promise<Loan[]>
  save(loan: Loan): Promise<void>
}
```

**Test Requirements:**
- Unit tests: Mock implementations for testing repository contracts
- Integration tests: Test repository implementations against real database

**Acceptance Criteria:**
- Repository interfaces define complete data access contracts
- All methods include proper error handling signatures
- Async operations are properly typed

---
```

### 5.3. Validation Criteria

The output must satisfy:
- **Architectural Coherence:** File structure reflects chosen architectural pattern
- **Implementation Specificity:** Each step provides concrete, actionable guidance
- **Testability:** Every component includes corresponding test specifications
- **Dependency Clarity:** Build order respects module dependencies
- **Completeness:** Roadmap covers all documented system requirements
