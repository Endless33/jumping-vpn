# VRP Architecture Overview

Veil Routing Protocol (VRP) is a new privacy protocol designed to break the predictability of network behavior. Unlike traditional VPNs that rely on stable tunnels and fixed routes, VRP introduces dynamic mutation, blind-node logic, and client-authority control.

## Core Principles

- Motion equals privacy — static routes are vulnerable; dynamic behavior creates unpredictability.
- Blind-node model — no node knows the full path; each node sees only its immediate neighbor.
- Client-authority — the client defines the route logic and mutation behavior.
- Mutation flow — routes mutate over time, preventing long-term traceability.

## Components

- VRP Client — initiates connection, controls mutation, and manages handshake logic.
- VRP Node — relays traffic blindly, without knowledge of origin or destination.
- VRP Authority — optional coordination layer for route logic and mutation rules.

## Behavior Model

- Routes are never stable.
- Each packet may follow a different path.
- Nodes do not retain session state.
- Mutation is continuous and client-driven.

## Status

This document is part of an evolving protocol.  
VRP is currently in architectural definition phase.

---

Jumping VPN is the first implementation of VRP, designed to demonstrate the protocol's behavior and philosophy.
