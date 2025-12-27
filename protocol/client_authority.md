# VRP Client Authority Model

In VRP, the client is not a passive participant. It is the architect of its own privacy. This model breaks from traditional VPNs and anonymity networks, where the server or network dictates the route.

## Core Idea

The client defines:
- how the route mutates,
- which nodes are used,
- when and how mutation occurs.

This gives the user full control over their privacy behavior.

## Why It Matters

- No central authority — no server decides the route.
- Custom mutation logic — users can define mutation intervals and triggers.
- Adaptive privacy — the client can respond to network conditions, threats, or heuristics.

## Comparison

| Model               | Who controls routing? | Mutation? | Node awareness |
|--------------------|------------------------|-----------|----------------|
| Traditional VPN    | Server                 | None      | Full           |
| Tor                | Directory Authority    | Static    | Partial        |
| VRP                | Client                 | Dynamic   | Blind          |

## Status

Client authority is a foundational principle of VRP.  
It enables dynamic, adaptive, and user‑defined privacy behavior.
