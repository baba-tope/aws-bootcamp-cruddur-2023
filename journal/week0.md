# User Personas
1. Product Owner - continuity and context
2. Web Development Group - current state
3. Investors - cost and timing
4. CTO - technical requirements and future state


# Good Architecture

## Gathering Requirements, Risks, Assumptions, and Constraints (RRACs)

### Requirements
- verifiable
- monitorable
- traceable
- feasible**

### Risks
- Single Point of Failure (SPoF)
- User Commitment
- Late Delivery

### Assumptions
These are factors held as true for the planning & implementation phases
- Sufficient network bandwidth
- Stakeholders will be available to make decisions
- Budget is approved

### Constraints
- Time
- Budget
- Vendor Selection

## Create Designs

### Conceptual Design
- Created by business stakeholders and architects
- organizes and defines concepts and rules
- a.k.a. "Napkin Design" or "Whiteboard" because it is a sketch of basic working parameters

### Logical Design
- Defines how the system should be implemented
- Environment without actual names or sizes
- It is a blueprint. Example: undeployed CloudFormation Template (CFT)

### Physical Design
- Representation of the actual thing
- Includes graular details like IP addresses, Instance types


### Develop a Common Dictionary
- Ask "dumb" questions
- Play "Be-the-packet" - acting as an end-user throughout the workflows
- Document everything (you can't remember everything. Visual copies help!)

*** TOGAF - Most popular framework for Enterprise Architecture (EA) ***
The Open Group Architectural Forum developed the TOGAF Standard for Enterprise Architecture which encompasses all of business activities and capabilities, information, and technology that make up the entire infrastructure and governance of the enterprise, or to one or more specific areas of interest within the enterprise. An enterprise may include partners, suppliers, and customers as well as internal business units. In all cases, the architecture crosses multiple systems, and multiple functional groups within the enterprise. [Read More](https://pubs.opengroup.org/togaf-standard/index.html)

AWS Well-Architected Tool aligns with TOGAF 


## The 4 C Model
The following are the 4 C's of Visualizing Software Architecture: Context, Containers, Components, and Code. [Learn More](https://c4model.com)

### Context

### Containers

### Components

### Code


# Week 0 — Billing and Architecture

You can use the `aws cli` or the AWS Billing and Cost Management console to create a Budget and set up billing alarms.

## AWS Organizations, IAM, and IAM Identity Center

Login to AWS Management console as the root user (email address) then navigate to the `AWS Organizations` console to enable the service and create an organization.


