# Overview
This repo contains an Azure DevOps pipeline that illustrates how to call an Azure ML pipeline on a schedule.  The schedule for the Azure DevOps pipeline is defined as a cron expression in the pipeline.  The pipeline starts the ML pipeline using the ML extension for `az cli`.  

## Setup
The pipeline depends on an Azure DevOps variable group named `Scheduled ML Pipeline Variables`.  This variable group needs to define the following variables:

| Name                | Description                              |
|---------------------|------------------------------------------|
| pipeline_id         | The unique identifier (guid) for the AML pipeline to be run |
| resource_group_name | The name of the resource group containing the AML workspace |
| workspace_name      | The name of the AML workspace containing the pipeline |

