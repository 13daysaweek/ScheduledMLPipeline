# Overview
This repo contains an Azure DevOps pipeline that illustrates how to call an Azure ML pipeline on a schedule.  The schedule for the Azure DevOps pipeline is defined as a cron expression in the pipeline.  PowerShell is used to first acquire an Azure AD bearer token.  Once the token is acquired, a call to an Azure ML endpoint is made, using the bearer token for authentication.

## Setup
The pipeline depends on an Azure DevOps variable group named `Scheduled ML Pipeline Variables`.  This variable group needs to define the following variables:

| Name              | Description                              |
|-------------------|------------------------------------------|
| client_id         | The client id of the service principal which is authorized to call the Azure ML pipeline |
| client_secret     | The client secret of the service principal which is authorized to call the Azure ML pipeline |
| tenant_id         | The Azure AD tenant id for the service principal which is authorized to call the Azure ML pipeline |
| pipeline_endpoint | The URI of the Azure ML pipeline to call |

Optionally, you may create these variables in a Key Vault and link the Key Vault to a variable group named `Scheduled ML Pipeline Variables`.
