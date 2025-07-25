## 1. Metadata & Declaration

| Field       | Value                                                                                                                                                  |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ID          | urn:prompt:transformer:doc2eventsourcing:1.0.0                                                                                                         |
| Version     | 1.0.0                                                                                                                                                  |
| Domain      | transformer                                                                                                                                            |
| Task        | doc2eventsourcing                                                                                                                                      |
| Description | Transform technical documentation into a comprehensive event-sourced architecture blueprint with event streams, aggregates, and projection patterns.  |
| Author      | [System]                                                                                                                                               |

## 2. Transformation Specification

### 2.1. Formal Objective

To process technical documentation describing system behaviors, business processes, or data workflows into a formal event-sourced architecture blueprint that captures all state changes as immutable events, defines aggregate boundaries, and specifies event stream processing patterns optimized for auditability, scalability, and temporal reasoning.

### 2.2. Input Schema (Source)

* **Type:** Technical Documentation (Markdown, Natural Language), System Requirements, Process Descriptions
* **Constraints:**
  * Must contain identifiable business processes, state transitions, or data workflows
  * Must include entities that undergo state changes over time
  * Should specify business rules, validation logic, or process constraints
  * May include existing CRUD operations or traditional architecture descriptions
* **Example:**

  > "The order management system allows customers to place orders, modify quantities before fulfillment, cancel orders, and track delivery status. Inventory is decremented when orders are confirmed. Payment processing occurs asynchronously with order confirmation."

### 2.3. Output Schema (Target)

* **Type:** Event-Sourced Architecture Blueprint (JSON-LD, YAML, Markdown)
* **Constraints:**
  * Must define all domain events as immutable facts
  * Must specify aggregate roots and their boundaries
  * Must include event stream topology and processing patterns
  * Must preserve all business logic as event-driven workflows
  * Must include projection strategies for read models
* **Example:**

```yaml
event_sourced_architecture:
  aggregates:
    - name: Order
      events: [OrderPlaced, OrderModified, OrderCancelled, OrderConfirmed]
      commands: [PlaceOrder, ModifyOrder, CancelOrder, ConfirmOrder]
    - name: Inventory
      events: [InventoryDecremented, InventoryReplenished]
      commands: [DecrementInventory, ReplenishInventory]
  
  event_streams:
    - name: order-events
      events: [OrderPlaced, OrderModified, OrderCancelled, OrderConfirmed]
      partitioning: by_customer_id
    
  projections:
    - name: OrderView
      source_streams: [order-events]
      materialized_view: current_order_status
```

### 2.4. Preconditions

* Input must contain identifiable business processes or state-changing operations
* Entities and their lifecycle states must be extractable from the documentation
* Business rules and constraints must be clearly defined or inferable

### 2.5. Postconditions (Guarantees)

* All state changes must be captured as domain events
* Event streams must be designed for optimal partitioning and scalability
* Aggregate boundaries must follow Domain-Driven Design principles
* Read models must be derivable from event streams through projections
* Architecture must support event replay and temporal queries

## 3. Operational Protocol (Agentic Instructions)

### 3.1. Cognitive Strategy

Domain Analysis + Event Extraction + Aggregate Design + Stream Topology + Projection Planning

### 3.2. Execution Steps

#### Transformation Pipeline Requirements:

* **Phase 1 – Domain Analysis:**
  Parse documentation to identify business processes, entities, and state transitions.

* **Phase 2 – Event Identification:**
  Extract all state-changing operations and model them as domain events.

* **Phase 3 – Aggregate Design:**
  Define aggregate boundaries based on consistency requirements and business invariants.

* **Phase 4 – Stream Topology:**
  Design event streams with appropriate partitioning and ordering guarantees.

* **Phase 5 – Projection Strategy:**
  Define read models and their derivation from event streams.

* **Phase 6 – Architecture Validation:**
  Ensure eventual consistency, scalability, and auditability requirements are met.

### Additional Step Logic

* **Step 1: Process Decomposition**
  * **Action:** Identify all business processes and their constituent operations.
  * **Rationale:** Establish comprehensive understanding of domain workflows.

* **Step 2: State Transition Analysis**
  * **Action:** Map all entity state changes and their triggering conditions.
  * **Rationale:** Ensure complete event coverage for auditability.

* **Step 3: Event Storm Modeling**
  * **Action:** Apply event storming techniques to identify domain events, commands, and aggregates.
  * **Rationale:** Leverage proven domain modeling practices for event-sourced systems.

* **Step 4: Consistency Boundary Definition**
  * **Action:** Define aggregate boundaries based on transactional consistency requirements.
  * **Rationale:** Ensure proper encapsulation of business invariants.

* **Step 5: Stream Architecture Design**
  * **Action:** Design event streams with partitioning strategies and ordering guarantees.
  * **Rationale:** Optimize for scalability and processing efficiency.

* **Step 6: Projection Planning**
  * **Action:** Define read models and their materialization strategies.
  * **Rationale:** Ensure efficient querying and reporting capabilities.

* **Validation & Refinement (Self-Correction Loop):**
  * **Action:** Validate event completeness, aggregate boundaries, and consistency guarantees.
  * **If any check fails:** Iterate with revised event definitions and aggregate boundaries.

## 4. Schema & Encoding Bindings

### 4.1. External References

* Event Sourcing Pattern: [https://microservices.io/patterns/data/event-sourcing.html](https://microservices.io/patterns/data/event-sourcing.html)
* Domain-Driven Design: [https://domainlanguage.com/ddd/](https://domainlanguage.com/ddd/)
* CQRS Pattern: [https://martinfowler.com/bliki/CQRS.html](https://martinfowler.com/bliki/CQRS.html)
* Apache Kafka: [https://kafka.apache.org/](https://kafka.apache.org/)

### 4.2. Target Formalism

* **Architecture:** Event-Sourced with CQRS
* **Serialization:** JSON, Avro, Protocol Buffers
* **Stream Processing:** Apache Kafka, Apache Pulsar, AWS Kinesis
* **Event Store:** EventStore, Apache Kafka, PostgreSQL with event sourcing extensions

## 5. Event-Sourced Architecture Template

### 5.1. Core Components

1. **Domain Events**
   - Immutable facts representing business state changes
   - Timestamp, version, and causation metadata
   - Semantic naming following past-tense conventions

2. **Aggregates**
   - Consistency boundaries for business invariants
   - Event application logic for state reconstruction
   - Command validation and event generation

3. **Event Streams**
   - Append-only logs of domain events
   - Partitioning strategies for scalability
   - Ordering guarantees within partitions

4. **Projections**
   - Read models materialized from event streams
   - Eventually consistent views optimized for queries
   - Incremental updates through event processing

5. **Sagas/Process Managers**
   - Long-running business processes
   - Cross-aggregate coordination
   - Compensation and error handling

### 5.2. Architecture Patterns

* **Event Store Pattern:** Centralized event persistence
* **CQRS Pattern:** Separate read and write models
* **Saga Pattern:** Distributed transaction management
* **Event Sourcing Pattern:** State derivation from events

## 6. Illustrative Example (Unit Test)

### 6.1. Input Instance

> "The e-commerce platform manages product inventory, processes customer orders, and handles payment transactions. When a customer places an order, the system checks inventory availability, reserves items, processes payment, and updates order status. If payment fails, reserved items are released back to inventory. Customers can view order history and track shipment status."

### 6.2. Expected Output Instance

```yaml
event_sourced_architecture:
  domain: e-commerce
  
  aggregates:
    - name: Product
      id: product_id
      events:
        - ProductCreated
        - ProductUpdated
        - InventoryAdjusted
        - ItemsReserved
        - ItemsReleased
      commands:
        - CreateProduct
        - UpdateProduct
        - AdjustInventory
        - ReserveItems
        - ReleaseItems
      invariants:
        - available_quantity >= 0
        - reserved_quantity <= total_quantity
    
    - name: Order
      id: order_id
      events:
        - OrderPlaced
        - OrderConfirmed
        - OrderCancelled
        - OrderShipped
        - OrderDelivered
      commands:
        - PlaceOrder
        - ConfirmOrder
        - CancelOrder
        - ShipOrder
        - DeliverOrder
      invariants:
        - order_total > 0
        - order_items.length > 0
    
    - name: Payment
      id: payment_id
      events:
        - PaymentInitiated
        - PaymentCompleted
        - PaymentFailed
        - PaymentRefunded
      commands:
        - InitiatePayment
        - CompletePayment
        - FailPayment
        - RefundPayment
      invariants:
        - payment_amount > 0
        - payment_status in [initiated, completed, failed, refunded]
  
  event_streams:
    - name: product-events
      events: [ProductCreated, ProductUpdated, InventoryAdjusted, ItemsReserved, ItemsReleased]
      partitioning: by_product_id
      retention: 365_days
      ordering: strict_within_partition
    
    - name: order-events
      events: [OrderPlaced, OrderConfirmed, OrderCancelled, OrderShipped, OrderDelivered]
      partitioning: by_customer_id
      retention: 7_years
      ordering: strict_within_partition
    
    - name: payment-events
      events: [PaymentInitiated, PaymentCompleted, PaymentFailed, PaymentRefunded]
      partitioning: by_order_id
      retention: 10_years
      ordering: strict_within_partition
  
  sagas:
    - name: OrderFulfillmentSaga
      triggers: [OrderPlaced]
      events_consumed: [OrderPlaced, ItemsReserved, ItemsReleased, PaymentCompleted, PaymentFailed]
      events_produced: [OrderConfirmed, OrderCancelled]
      compensation_events: [ItemsReleased, PaymentRefunded]
      timeout: 30_minutes
  
  projections:
    - name: ProductInventoryView
      source_streams: [product-events]
      materialized_view: current_product_inventory
      key: product_id
      fields: [product_id, name, total_quantity, available_quantity, reserved_quantity]
      update_strategy: incremental
    
    - name: OrderHistoryView
      source_streams: [order-events, payment-events]
      materialized_view: customer_order_history
      key: customer_id
      fields: [order_id, customer_id, order_date, items, total_amount, status, payment_status]
      update_strategy: incremental
    
    - name: OrderTrackingView
      source_streams: [order-events]
      materialized_view: order_tracking_status
      key: order_id
      fields: [order_id, status, tracking_number, estimated_delivery, actual_delivery]
      update_strategy: incremental
  
  event_schemas:
    - name: OrderPlaced
      version: 1
      schema:
        order_id: string
        customer_id: string
        items: array<OrderItem>
        total_amount: decimal
        order_date: timestamp
        shipping_address: Address
    
    - name: ItemsReserved
      version: 1
      schema:
        product_id: string
        quantity: integer
        order_id: string
        reserved_at: timestamp
    
    - name: PaymentCompleted
      version: 1
      schema:
        payment_id: string
        order_id: string
        amount: decimal
        payment_method: string
        transaction_id: string
        completed_at: timestamp
  
  technology_stack:
    event_store: Apache Kafka
    projection_store: PostgreSQL
    stream_processing: Apache Kafka Streams
    saga_orchestration: Custom Saga Manager
    serialization: Apache Avro
    
  consistency_guarantees:
    - within_aggregate: strong_consistency
    - across_aggregates: eventual_consistency
    - event_ordering: partition_level_ordering
    - delivery_semantics: at_least_once
  
  operational_concerns:
    - event_replay: full_system_rebuild_capability
    - schema_evolution: backward_compatible_avro
    - monitoring: event_lag_metrics
    - backup_strategy: kafka_topic_replication
    - disaster_recovery: cross_region_replication
```

### 6.3. Validation Criteria

The output must demonstrate:
- Complete event coverage for all state changes
- Proper aggregate boundary definition with business invariants
- Event stream design optimized for scalability and ordering
- Projection strategies covering all read model requirements
- Saga patterns for cross-aggregate coordination
- Operational considerations for production deployment
