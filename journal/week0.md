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
1. From the Gitpod terminal, set the AWS credentials:

```sh
export AWS_ACCESS_KEY_ID=""
export AWS_SECRET_ACCESS_KEY=""
export AWS_DEFAULT_REGION=us-east-1
```

2. To make the Gitpod workspaces to be persistent at launch, pass them as environment variables:

```sh
gp env AWS_ACCESS_KEY_ID=""
gp env AWS_SECRET_ACCESS_KEY=""
gp env AWS_DEFAULT_REGION=us-east-1
```

3. Update the `.gitpod.yml` to include the following task:

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

4. Commit the change and close the workspace.

> Ensure the GitHub repo reflects the changes made to the `.gitpod.yml` file before workspace termination.













## AWS Organizations, IAM, and IAM Identity Center

Login to AWS Management console as the root user (email address) then navigate to the `AWS Organizations` console to enable the service and create an organization.


