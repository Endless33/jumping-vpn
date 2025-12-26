# VRP Packet Format

VRP packets are designed to minimize metadata exposure and prevent long‑term correlation.  
Nodes see only what they need to forward traffic — nothing more.

## Packet Structure

A VRP packet consists of the following components:

- Header — minimal routing metadata
- Payload — encrypted user data
- Integrity tag — ensures packet validity

## Header Fields

- Ephemeral Session ID
  - Temporary identifier
  - Changes frequently
  - Not linkable across sessions

- Next-Hop Hint (optional)
  - Helps node forward the packet
  - Does not reveal full route

- Mutation Flags
  - Indicates if packet triggers mutation
  - Used only by the client

## Payload

- Fully encrypted
- Node cannot inspect or modify
- Contains no identifiable metadata

## Integrity Tag

- Ensures packet was not tampered with
- Node can validate but cannot decrypt

## Privacy Properties

- No persistent identifiers
- No long-term session state
- No route disclosure
- No fingerprintable metadata

## Status

Packet format is stable and forms a core part of the VRP specification.
