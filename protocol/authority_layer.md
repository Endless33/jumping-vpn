# VRP Authority Layer (Optional)

The VRP Authority Layer is an optional coordination component.  
It does not control routing, does not assign nodes, and does not act as a central authority.  
Instead, it provides optional metadata that clients may use to improve performance or diversity.

## Purpose

The authority layer exists to:
- distribute optional node metadata,
- provide recommended mutation parameters,
- assist with network-wide coordination,
- improve node diversity and availability.

It does not participate in routing decisions.

## What the Authority Does

- Publishes a list of available nodes.
- Provides optional performance metrics.
- Suggests mutation intervals (optional).
- Helps clients avoid overloaded nodes.

## What the Authority Does NOT Do

- Does not assign routes.
- Does not track users.
- Does not maintain sessions.
- Does not know client identity.
- Does not know mutation logic.
- Does not know full network topology.

## Privacy Properties

- Clients remain fully autonomous.
- No central point of control.
- No persistent identifiers.
- No route disclosure.

## Optional Nature

The authority layer is not required for VRP to function.  
Clients may:
- ignore it completely,
- use it partially,
- or rely on decentralized discovery instead.

## Status

The authority layer is an optional extension and may evolve independently of the core protocol.
