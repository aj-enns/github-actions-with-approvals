# github-actions-with-approvals

## GitHub Actions Workflow for Deploying Azure Function

This repository contains GitHub Actions workflows to deploy an Azure Function to different environments: Dev, System Test, UAT, and Production.

### Deployment to Dev

The deployment to the Dev environment is triggered automatically when changes are pushed to the main branch. The workflow file for this deployment is located at `.github/workflows/deploy-dev.yml`.

### Deployment to System Test

The deployment to the System Test environment is triggered manually using the `workflow_dispatch` event. The workflow file for this deployment is located at `.github/workflows/deploy-system-test.yml`.

### Deployment to UAT

The deployment to the UAT environment is triggered manually using the `workflow_dispatch` event. This deployment requires approval from a set of reviewers. The workflow file for this deployment is located at `.github/workflows/deploy-uat.yml`.

### Deployment to Production

The deployment to the Production environment is triggered manually using the `workflow_dispatch` event. This deployment requires approval from a different set of reviewers. The workflow file for this deployment is located at `.github/workflows/deploy-prod.yml`.

### Approvers

- UAT Approvers: A set of reviewers who must approve the deployment to the UAT environment.
- Production Approvers: A different set of reviewers who must approve the deployment to the Production environment.

### to Setup approvers
Navigate to your repository on GitHub.
Go to the "Settings" tab.
In the left sidebar, click on "Environments".
Create a new environment (e.g., uat or production) if it doesn't already exist.
Configure the environment:
Click on the environment name.
Under "Deployment protection rules", add the required reviewers.
For example, to set up the uat environment with reviewers:

Click "New environment" and name it uat.
Click on the uat environment.
Under "Deployment protection rules", click "Add rule".
Select "Required reviewers" and add reviewer1 and reviewer2.
