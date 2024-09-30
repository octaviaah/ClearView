# Implement a Quarantined LLM for increased privacy and security

## Context
This ADR addresses the decision of implementing a quarantined Large Language Model (LLM) within the ClearView system to enhance privacy and security. The goal is to isolate sensitive data and prevent unauthorized access or data leakage.

## Decision: 
Based on the ClearView requirements and the factors considered above, we have decided to implement a quarantined LLM using dedicated, local, quarantined LLM instance approach.

## Status
Proposed

## Options
* Dedicated LLM Instance: Deploy a separate LLM instance exclusively for processing sensitive data. This provides the highest level of isolation but may increase costs and complexity.
* Containerization: Encapsulate the LLM within a secure container, isolating it from other components of the system. This offers a balance between security and resource efficiency.
* Data Masking and Anonymization: Before processing sensitive data, mask or anonymize it to reduce its value to attackers. This can be combined with other options for additional security.

## Consequences
Advantages:
* Highest level of isolation: Provides the most robust security by completely segregating the LLM from other system components.
* Minimal risk of data leakage: Reduces the chances of sensitive data being exposed to unauthorized parties.
* Customizable configuration: Allows for fine-grained control over the LLM's environment and resources.

Disadvantages:
* Increased costs: Requires additional hardware or cloud resources to host the dedicated LLM instance.
* Operational complexity: Managing a separate LLM instance can be more complex than integrating it with existing infrastructure.
* Potential performance overhead: Depending on the workload and resource allocation, a dedicated LLM instance may introduce additional latency.

## Useful links
- [C4 diagram](https://github.com/octaviaah/ClearView/blob/main/2.ArchitectureVisualization/C4Diagram.md)
- [ADR003 - AI Model Selection and Training](https://github.com/octaviaah/ClearView/blob/main/3.ADRs/ADR003-AIModelSelection.md)
