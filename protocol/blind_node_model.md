# VRP Blind-Node Model

The blind-node model is a core part of VRP’s privacy design. Nodes in the VRP network are intentionally limited in what they can see and know about the traffic they relay.

## Core Idea

No single node should ever have enough information to:
- identify the user,
- reconstruct the full route,
- or reliably correlate traffic over time.

## Node Perspective

Each VRP node:
- sees only the previous hop and the next hop,
- does not know the origin or final destination,
- does not have global knowledge of the network,
- does not store long-term session state.

## Privacy Effects

- Limited knowledge — a compromised node cannot expose the whole route.
- No full graph — no node has a global view of paths.
- Hard to correlate — mutation and blind-node logic work together to break patterns.

## Role in VRP

The blind-node model, combined with dynamic mutation, ensures that even if some nodes are observed or controlled, the overall privacy of the user remains extremely hard to break.
