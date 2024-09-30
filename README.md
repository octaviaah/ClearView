# ClearView

## Summary

This repository presents an architectural proposal done by the Dreamers League team for the O'Reilly Fall 2024 Architectural Katas contest. This proposal describes our approach in implementing the ClearView, a piece of software that is intended to be integrated with HR systems, to simplify the hiring process and assure a more inclusive viewpoint. We have made a thorough analysis of the requirements, came up with arguments to support the architectural characteristics we found, concentrated on designing diagrams(sequence, C4) and identified the user flows exposed through ClearView. All these elements complete our vision on how we want ClearView to be designed and implemented.

## Table of contents

0. ### [ClearView Story](./1.Requirements/ClearViewStory.md)
1. ### Overview of the system

   1.1. [Client Initial Requirements](./1.Requirements/ClientInitialRequirements.md)

   1.2. [Core Requirements](./1.Requirements/CoreRequirements.md)

   1.3. Requirement analysis

   1. [User journey - Employer](./1.Requirements/UserJourneys/Employer.md)

   2. [User journey - Job Candidate](./1.Requirements/UserJourneys/JobCandidate.md)

   3. [User journey - Administrator](./1.Requirements/UserJourneys/Admin.md)

   1.4. [Cross-functional Requirements](./1.Requirements/CrossFunctionalRequirements.md)

   1.5. [Capabilities](./1.Requirements/Capabilities.md)

2. ### Architectural Visualization

   2.1. [Architecture Style](./2.ArchitectureVisualization/ArchitectureStyle.md)

   2.2. [C4 Diagram](./2.ArchitectureVisualization/C4Diagram.md)
   
   2.3. [Deployment](./2.ArchitectureVisualization/Deployment.md)

4. ### ADRs

   3.1. [Event Driven Architecture](./3.ADRs/ADR001-EventDrivenArchitecture.md)

   3.2. [Functions Across Domain Boundaries](./3.ADRs/ADR002-FunctionsAcrossDomainBoundaries.md)

   3.3. [AI Model Selection](./3.ADRs/ADR003-AIModelSelection.md)

   3.4. [Quarantined LLM](./3.ADRs/ADR004-QuarantinedLLM.md)

   3.5. [Bias Detection](./3.ADRs/ADR005-BiasDetection.md)

   3.6. [Integrating a Message Broker](./3.ADRs/ADR006-IntegratingAMessageBroker.md)

   3.7. [Handling Blob Storage](/3.ADRs/ADR007-HandlingBlobStorage.md)

   3.8. [Integration with Other HR Systems](/3.ADRs/ADR008-IntegrationWithOtherHrSystems.md)

## Contributors

For this project, an aspiring team of architects has been organized, using this opportunity to forecast our skills into new and innovative solutions that focus on transparency, user experience, functionality, while also emphasizing performance.

**Team members**:

- Lucian Braescu
- Miruna Urcan
- Octavia Hriscu
- Ovidiu Moldovan

You can contact us at: dreamersleague@evozon.com
