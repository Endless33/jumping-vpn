# VRP Handshake Flow

The handshake flow defines how a VRP client establishes a connection with a node without revealing identity, route intent, or long-term session state.

## Goals

- Establish a temporary session.
- Exchange minimal routing metadata.
- Avoid persistent identifiers.
- Prevent fingerprinting.

## Flow Steps

1. Client selects node from available pool.
2. Client sends handshake packet with:
   - ephemeral session ID,
   - next-hop hint (optional),
   - mutation parameters (optional).
3. Node validates packet:
   - checks structure,
   - verifies basic integrity,
   - does not store session state.
4. Node responds with:
   - acknowledgment,
   - optional relay confirmation.

## Privacy Features

- No long-term session keys.
- No persistent identifiers.
- No client fingerprinting.
- No route disclosure.

## Status

Handshake logic is minimal by design.  
It supports dynamic mutation and blind-node behavior without compromising privacy.
