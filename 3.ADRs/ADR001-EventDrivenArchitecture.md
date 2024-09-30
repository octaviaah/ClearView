# Choose an architectural style

## Context
This ADR addresses the decision of selecting an architectural style for the ClearView system. The goal is to determine the most appropriate approach for designing and building the system's components and interactions.

## Options
* Microservices Architecture: Break down the system into small, independent services that communicate via APIs.
* Service-Oriented Architecture (SOA): Use a coarse-grained approach with loosely coupled services that exchange messages.
* Event-Driven Architecture: Focus on events as the primary mechanism for communication and processing.
* Monolithic Architecture: Build the entire system as a single, tightly coupled unit.

## Decision
Based on the ClearView requirements, we have decided to choose the Event-Driven Architecture style.

## Status
Proposed

## Consequences:
* Increased complexity: Designing and managing an event-driven system can be more complex than a monolithic architecture.
* Potential for message loss: If events are not processed or acknowledged correctly, they might be lost.
* Increased overhead: Event processing and message queuing can introduce additional overhead.
* Improved scalability and flexibility: The event-driven approach can lead to more scalable and adaptable systems.

## Useful links 
- [C4 diagram](https://github.com/octaviaah/ClearView/blob/main/2.ArchitectureVisualization/C4Diagram.md)
