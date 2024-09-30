# Integration with other HR Systems

## Context

ClearView needs to be integrated with existing HR Systems to exchange candidates' data, thus integrating with existing processes inside companies.

## Decision:

The decision is to integrate with other systems using a REST API mainly because most modern HR systems already provide REST APIs.

## Status

Proposed

## Options

- HTTP / REST APIs: widely supported, lightweight. An easier approach for our system that can be expanded in future.
- FTP/SFTP: file transfer may be common for legacy systems.
- Message Queues: event-driven integration may also be a solution, but adds complexity and may not be crucial for our first iteration of ClearView.

## Consequences

REST APIs offer **scalability** while offering a plus in **ease of development** and **maintenance**. They also offer **flexibility** in adapting the data format for different HR Systems' requirements.

## Useful links

- [C4 diagram](https://github.com/octaviaah/ClearView/blob/main/2.ArchitectureVisualization/C4Diagram.md#hr-integration-component-diagram)
