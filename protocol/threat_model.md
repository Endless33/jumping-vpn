# VRP Threat Model

The VRP threat model defines the types of adversaries the protocol is designed to resist.  
It focuses on preventing long‑term correlation, route reconstruction, and metadata exposure.

## Adversary Types

### 1. Passive Network Observer
An entity that monitors traffic without modifying it.

Capabilities:
- Can observe packets entering and leaving a node
- Can measure timing and volume
- Cannot decrypt payloads

VRP protection:
- Continuous mutation breaks long‑term correlation
- Blind-node model prevents route reconstruction

### 2. Compromised Node
A node under adversary control.

Capabilities:
- Sees previous and next hop only
- Sees encrypted payload
- Cannot see full route

VRP protection:
- No node has global knowledge
- Mutation ensures compromised nodes lose relevance quickly

### 3. Global Traffic Analyst
A powerful adversary capable of observing large parts of the internet.

Capabilities:
- Can correlate timing across multiple points
- Can attempt route mapping

VRP protection:
- Per‑packet mutation disrupts correlation
- No stable identifiers
- No long‑term sessions

### 4. Malicious Service Provider
A provider attempting to profile users.

Capabilities:
- Can observe entry traffic
- Cannot see internal mutation or node behavior

VRP protection:
- Client authority prevents provider‑controlled routing
- Blind-node model hides internal structure

## Out‑of‑Scope Threats

VRP does not protect against:
- Compromised client devices
- Malware on the user’s machine
- Physical access attacks
- Social engineering

## Summary

VRP is designed to resist:
- correlation attacks  
- route reconstruction  
- compromised nodes  
- metadata analysis  
- centralized control  

It achieves this through mutation, client authority, and blind-node logic.
