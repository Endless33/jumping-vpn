# VRP Multi‑Path Routing

VRP (Veil Routing Protocol) is designed to treat multi‑path behavior as a core privacy primitive, not as an optimization or load‑balancing feature. This document describes the high‑level model of VRP multi‑path routing without exposing internal scoring or decision logic.

---

## 1. Goals

VRP multi‑path routing is designed to:

- Reduce correlation between entry and exit flows.
- Fragment knowledge about any single flow across multiple routes.
- Complicate traffic analysis based on timing and volume.
- Provide graceful degradation when some routes become unreliable or hostile.

Multi‑path is a tool for anti‑analysis, not for throughput tuning.

---

## 2. Core concepts

### 2.1 Flow

A VRP *flow* is a logical stream of packets at the VRP routing layer (not a TCP connection, not an application session).

Each flow is identified by a FlowId and may be attached to one or more routes.

### 2.2 Route

A *route* is an ordered chain of blind nodes (VrpRoute), constructed and rotated by the client‑side mutation engine.

Routes are:

- short‑lived,
- replaceable,
- independent from each other.

### 2.3 Multi‑path binding

A flow may be bound to multiple routes simultaneously.  
For example:

- Flow F1 → Routes: R1, R2, R3  

The routing layer then decides how each packet of F1 is mapped onto these routes.

---

## 3. Multi‑path behaviors

VRP supports different high‑level behaviors, which can be implemented as strategies:

### 3.1 Duplication

The same packet is sent across multiple routes:

- increases redundancy,
- complicates correlation,
- increases cost for an observer.

### 3.2 Splitting

The flow is split across routes:

- some packets via R1,
- some via R2,
- some via R3.

Splitting pattern is not exposed in the public reference.

### 3.3 Dynamic merging and rebalancing

Routes attached to a flow may:

- appear,
- disappear,
- change weight,
- be retired.

From the observer’s point of view, the path structure is non‑static and hard to model.

---

## 4. Strategy abstraction

At the implementation level, VRP models multi‑path routing as a strategy.

In Rust, this is expressed as:

- a MultiPathStrategy trait,
- a RoutingContext that owns active routes and flow → route bindings,
- strategy implementations that decide how to map packets to routes.

The public reference exposes only the interface, not the internal decision rules.

---

## 5. Design principles

VRP multi‑path routing follows these principles:

- Client‑centric: the client controls which routes are active for a flow.
- Blind nodes: no single node sees the entire multi‑path structure.
- Short‑lived routes: paths are expected to change over time.
- Fragmented visibility: neither any single node nor a simple observer has a complete view.

Multi‑path behavior interacts closely with the mutation engine and the threat model.

---

## 6. Out‑of‑scope details

This document intentionally does not define:

- exact splitting algorithms,
- scoring functions for routes,
- timing jitter rules,
- advanced anti‑correlation heuristics.

Those details are part of the private implementation and are not required to understand the public architecture.
