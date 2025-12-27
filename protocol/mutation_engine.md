# VRP Mutation Engine

The mutation engine is the component responsible for deciding when and how the route changes.  
It operates entirely on the client side and is a core part of VRP’s unpredictability model.

## Core Principles

- Client-driven — only the client decides when mutation happens.
- Unpredictable — mutation intervals and triggers avoid stable patterns.
- Continuous — routes evolve over time, not only at session start.
- Independent — nodes do not influence mutation decisions.

## Mutation Triggers

The mutation engine may trigger route changes based on:

### 1. Time-based triggers
- Route changes every N milliseconds.
- Ensures continuous motion.

### 2. Packet-based triggers
- Route changes after X packets.
- Prevents long-term correlation.

### 3. Event-based triggers
- Network instability
- Latency spikes
- Suspicious patterns
- Client heuristics

### 4. Randomized triggers
- Adds entropy to avoid predictability.

## Mutation Actions

When mutation is triggered:

1. Client selects new nodes.
2. Client updates next-hop hints.
3. Client rotates ephemeral session identifiers.
4. Client sends packets through the new route immediately.

## Privacy Effects

- No stable route exists long enough to be mapped.
- Compromised nodes lose relevance quickly.
- Traffic correlation becomes extremely difficult.
- Observers cannot predict future paths.

## Status

The mutation engine is a flexible component and may evolve as VRP matures.
