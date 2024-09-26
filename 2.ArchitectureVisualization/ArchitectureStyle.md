<img src="https://www.pngkit.com/png/full/53-536659_software-architecture-and-design-back-end-web-development.png" align="right" height="64px" />

# Architecture Style

## Project scope

ClearView aims to revolutionize the hiring process by promoting diversity and reducing bias through AI-powered candidate evaluation and anonymization. The system's [core](https://github.com/octaviaah/ClearView/blob/main/1.Requirements/CoreRequirements.md) functionality revolves around enhancing existing recruitment processes and empowering decision makers with additional data points to make more informed, inclusive decisions.

Choosing an appropriate architectural style is essential for ensuring that the system's structure aligns with the business specific needs.

## Identified architectural characteristics

In the requirements analysis phase, the team identified Cost-efficiency, Elasticity, and Agility as pivotal architectural characteristics for the ClearView system. 

#### Cost-efficiency
Many organizations, especially startups or smaller businesses, have limited budgets for IT infrastructure. The system should be able to handle fluctuations in workload without significant cost increases.

Utilizing cloud services like AWS, Azure, or GCP can provide pay-as-you-go pricing models, allowing for flexibility in resource allocation. Employing serverless functions can eliminate the need for managing servers, reducing operational costs. Implementing efficient data storage solutions can minimize storage costs.

#### Elasticity
The number of users and the workload on the system may vary significantly over time. The system should be able to automatically adjust its capacity to meet changing demands.

Configuring cloud services to automatically scale up or down based on workload, add or remove instances of the application to accommodate increased or decreased load, increase or decrease the resources allocated to individual instances will help to adapt to evolving demands as the system grows over time.

#### Agility
The technology landscape and business requirements can evolve quickly. The system should be able to adapt to new features, technologies, or changes in regulations.

Breaking down the system into smaller, independent services that can be developed, deployed, and scaled independently across domain boundaries can help drive and promote agility within a system.

#### Other considerations
* #### AI Responsibility 
  AI systems can have significant impacts on people's lives. It's essential to ensure they are used ethically and responsibly. AI models can perpetuate or amplify biases present in the data they are trained on.

  Implementing techniques to identify and mitigate biases in the AI models such as data augmentation, fairness metrics, and explainable AI are critical as well as being transparent about the AI's decision-making process and hold the system accountable for its actions.
  
  We can also ensure that human experts are involved in overseeing and making decisions based on the AI's output.

* #### Observability
  Observability helps identify and diagnose issues with the system. It provides insights into the system's performance and allows for optimization. Observability can help ensure compliance with regulations and industry standards.

  Implementing comprehensive logging to capture system events and behavior together with collecting and analyzing metrics related to system performance, resource usage, and error rates can help make the system more predictable and explainable while also helping identify performance bottlenecks and focus relevant teams on critical issues or anomalies.

## Architecture styles evaluation

Event-driven architecture focuses on the flow of events within a system or between different systems, often in the form of messages or notifications. Various components of a system communicate and react to events asynchronously, rather than through direct, synchronous method calls. Events can represent various occurrences, changes in state, or triggers within a system.

Event-driven architecture is commonly used in various applications, including:
- Real-time data processing
- Microservices-based systems
- IoT (Internet of Things) applications
- Systems that require high levels of concurrency and responsiveness

After conducting an assessment utilizing the [Architecture Styles Worksheet](https://github.com/octaviaah/ClearView/blob/main/2.ArchitectureVisualization/ArchitectureStylesWorksheet.png), the team has arrived at the decision that the most fitting architectural solution for the ClearView system is the adoption of an event-driven architecture. This conclusion is based on the alignment of the event-driven paradigm with the identified [project requirements](https://github.com/octaviaah/ClearView/blob/main/1.Requirements/ClientInitialRequirements.md) and essential [architectural characteristics](https://github.com/octaviaah/ClearView/blob/main/1.Requirements/CrossFunctionalRequirements.md).

The team aims to provide a balanced architecture for the ClearView system that can sustain present and future workloads with reasonable costs. We are aware that in various AI systems such as ClearView where the requirements are bound to a very specific and specialized domain the focus tends to shift towards building modular monoliths, however, considering the user base and the potential growing market for a greenfield system like ClearView we want to provide the ability to pivot certain domain functions to more elastic workloads.

In reality most systems grow towards a hybrid architecture and we hope we can highlight some of the areas where such tradeoffs have been considered and made for our system. As such we try to keep most of the basic ClearView functionality modular, while allowing certain modules to leverage the power of an event driven approach and also aiming to keep the AI model within a clear service boundary due to security and privacy concerns.

## Rationale and benefits

The rationale for choosing an event-driven architecture for the ClearView system is based on several key factors identified during the assessment and evaluation process.

#### Real-time Responsiveness
Event-driven architectures excel at providing real-time responsiveness. In the context of ClearView, where processing files and interview experiences are critical, the event-driven model aligns with the need for instantaneously processing resume data and detecting patterns of interaction between candidates and potential employers.

#### Adaptability to Changes
Event-driven architectures are adaptable and facilitate the addition of new features and integrations without major disruptions. Regarding interfacing with existing HR systems and future ones that leverage evolving technology this adaptability is crucial for the long-term success of the system.

#### Seamless Integration
Event-driven systems can easily integrate with external services, making communication with other systems like the HR Systems seamless. This capability is essential for ClearView to efficiently integrate within existing recruiting pipelines and processes.

#### Loose Coupling
Event-driven architectures typically promote loose coupling between components. This can enhance system flexibility, making it easier to modify or update individual components without affecting the entire system. This aligns with the need for maintainability and extensibility in our startup, greenfield business context.

#### Efficient Use of Resources
Event-driven architectures can optimize resource utilization by triggering actions only when relevant events occur. This efficiency is crucial for a system like ClearView, where the focus is on detecting patterns and measuring the fairness of the overall recruitment process.

#### Facilitating Parallel Processing
The event-driven model allows for parallel processing of events, enabling the system to handle multiple concurrent events simultaneously. This can contribute to improved overall system performance and responsiveness.

#### Enhanced Fault Tolerance
Event-driven architectures can enhance fault tolerance by allowing the system to gracefully handle faults or disruptions. This is critical for ensuring continuous and fair evaluation of candidate matches.

By considering these factors, the team has determined that an event-driven architecture aligns well with the specific requirements and goals of the ClearView system, making it a suitable choice for the project.

## Project constraints

#### Learning Curve
Introducing an event-driven architecture may require the development team to acquire new skills and practices. Training and adapting to the new paradigm may be a constraint, especially if the team is not already familiar with event-driven development. Providing training and resources for the team to acquire the necessary skills and bringing in experts or mentors with experience in event-driven development are some of the actions considered to mitigate this constraint.

#### Operational Practices
Managing a distributed event-driven system demands robust operational practices. Ensuring that operational teams are well-versed in handling event-driven architectures is crucial for system stability and performance.
We will implement robust operational practices, monitoring, and automation tools to streamline system management and also invest in training or hiring personnel with expertise in system operations.

## Risks and risk mitigation

#### Data Consistency
Risk: Ensuring data consistency across distributed components can be challenging, and improper handling could lead to data discrepancies.
Mitigation: Implement mechanisms for data validation and consistency checks. Use transactions or compensating transactions where appropriate to maintain data integrity.

#### Complex Event Routing Logic
Risk: The complex event routing logic may be difficult to manage and debug, potentially causing errors or delays.
Mitigation: Thoroughly document and test event routing logic. Implement logging and monitoring to quickly identify and address any issues. Consider using tools that provide visualization of event flows for better debugging.

#### Security Concerns:
Risk: Event-driven architectures may introduce security concerns, such as unauthorized event consumption or tampering.
Mitigation: Implement robust authentication and authorization mechanisms. Use secure communication protocols, and encrypt sensitive data. Regularly conduct security audits and assessments.

#### Operational Monitoring Challenges:
Risk: Monitoring a distributed event-driven system can be challenging, leading to difficulties in identifying performance or operational issues.
Mitigation: Invest in comprehensive monitoring tools and practices. Implement centralized logging and monitoring solutions to track system behavior. Conduct regular performance testing to identify and address potential issues proactively.

## Architecture visualization
The [C4 diagram](https://github.com/octaviaah/ClearView/blob/main/2.ArchitectureVisualization/C4Diagram.md) visually illustrates a high level overview of the system and the infrastructure is high-lighted 

## Architecture style worksheet:
![ArchitectureStyle](https://github.com/octaviaah/ClearView/blob/main/2.ArchitectureVisualization/ArchitectureStylesWorksheet.png)

## Relevant Architecture Decision Records
[ADR002-EventDrivenArchitecture](https://github.com/octaviaah/ClearView/blob/main/3.ADR/ADR002-EventDrivenArchitecture.md)

[ADR003-FunctionsAcrossDomainBoundaries](https://github.com/octaviaah/ClearView/blob/main/3.ADR/ADR003-FunctionsAcrossDomainBoundaries.md)

[ADR004-QuarantinedLLM](https://github.com/octaviaah/ClearView/blob/main/3.ADR/ADR004-QuarantinedLLM.md)