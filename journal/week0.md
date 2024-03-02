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

## IAM
Navigate to the [IAM User groups Console](https://us-east-1.console.aws.amazon.com/iam/home?region=us-east-2#/groups)
1. Create a group named `Privileged_Service_Accounts`
2. Attach the `PowerUserAccess` and `Billing` policies to the group*
3. Create a user named `Gitpod` and add it to the group
4. Click on [Users](https://us-east-1.console.aws.amazon.com/iam/home?region=us-east-2#/users), click on the newly created user
5. Click on `Security Credentials` then `Create Access Key` for programmatic access.
6. Choose `Command Line Interface (CLI)`, confirm and download the CSV with the credentials.

> It is best to use least privilege when assigning permissions 


## Billing
You can use the `aws cli` or the AWS Billing and Cost Management console to create a Budget and set up billing alarms. 
Activate the Gitpod Workspace from the repo, install the AWS CLI, then set the budget and billing alarms programmatically. 

### Install AWS CLI
Gitpod would be launched to use AWS CLI to send Bash commands to AWS. Follow the [AWS CLI Install instructions](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) to install via the terminal.
```sh
cd /workspace
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
cd $THEIA_WORKSPACE_ROOT
```


### Set Environment Variables
From the Gitpod terminal, set the AWS credentials:
```sh
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export AWS_DEFAULT_REGION=us-east-1
```

To make the Gitpod workspaces to be persistent at launch, pass them as environment variables:
```sh
gp env AWS_ACCESS_KEY_ID=""
gp env AWS_SECRET_ACCESS_KEY=""
gp env AWS_DEFAULT_REGION=us-east-1
```

Update the `.gitpod.yml` to include the following task:

```
tasks:
  - name: aws-cli
    env:
      AWS_CLI_AUTO_PROMPT: on-partial
    init: |
      cd /workspace
      curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
      unzip awscliv2.zip
      sudo ./aws/install
      cd $THEIA_WORKSPACE_ROOT
```


> Ensure the GitHub repo reflects the changes make to the `.gitpod.yml` file.


## AWS Organizations, IAM, and IAM Identity Center

Login to AWS Management console as the root user (email address) then navigate to the `AWS Organizations` console to enable the service and create an organization.


