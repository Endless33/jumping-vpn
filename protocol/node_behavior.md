# VRP Mutation Flow

The mutation flow is the core mechanism that makes VRP unpredictable and resistant to long‑term correlation. Unlike traditional VPN tunnels, VRP does not rely on a stable route. Instead, the path mutates continuously based on client‑driven logic.

## Core Idea

A static route is a vulnerability.  
A moving route is protection.

VRP ensures that no route remains valid long enough to be profiled, mapped, or correlated.

## How Mutation Works

- The client defines mutation intervals.
- Each interval triggers a route change.
- Nodes are selected dynamically from the available pool.
- No node knows the previous or next hop.
- Each packet may follow a different path.

## Mutation Types

- Time‑based mutation — route changes every N milliseconds.
- Packet‑based mutation — route changes after X packets.
- Event‑based mutation — triggered by network conditions or heuristics.

## Why Mutation Matters

- Prevents long‑term traffic correlation.
- Breaks any attempt to map the route.
- Eliminates stable identifiers.
- Makes VRP resistant to surveillance and profiling.

## Status

The mutation flow is under active definition and will evolve as the protocol matures.**
