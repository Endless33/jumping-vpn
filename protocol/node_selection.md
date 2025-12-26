# VRP Node Selection Logic

Node selection in VRP is designed to maximize unpredictability while maintaining performance and privacy.  
The client is fully responsible for choosing which nodes participate in the route.

## Core Principles

- Client authority — only the client decides the route.
- Unpredictability — selection must avoid patterns.
- Diversity — nodes should vary across geography, latency, and trust domains.
- Replaceability — any node can be swapped at any moment.

## Selection Factors

The client may consider:

- latency
- geographic distribution
- node availability
- mutation interval
- randomization entropy
- optional user preferences

These factors do not reveal identity or route intent.

## Selection Process

1. Client retrieves or maintains a list of available nodes.
2. Client applies filtering (optional).
3. Client applies randomization.
4. Client selects N nodes for the current route.
5. Client may replace nodes at any mutation event.

## Privacy Effects

- No central authority controls routing.
- No node knows why it was selected.
- No stable patterns emerge over time.
- Mutation ensures continuous unpredictability.

## Status

Node selection logic is flexible and may evolve as VRP matures.
