# Route53 Application Recovery Controller Demo
This is still very much a work in progress, please contact jonesaws@amazon.com with questions and/or feedback.

## Prerequisites
Public Route53 Hosted Zone (this is not included in the scope of this demo and must be setup seperately).

## CloudFormation Templates
## Application

`./templates/Application.yaml`

Application template, deployed into both a primary and secondary region.  The template deploys the following basic application architecture:

![Application Architecture](./images/r53_Arc_demo.png)

## Route53 Application Recovery Controller Common Components

`./templates/ArcShared.yaml`

**Must be deployed into us-east-1**

This template deploys shared components including:

- S3 Bucket
- Cloudwatch Synthetics Canary
- Route53
  - Healthchecks
  - Weighted RecordSet
- Route53 Arc
  - Cluster
  - Control Panel
  - Safety Rule
  - Routing Controls
  - Recovery Group
  - Cells
  - Global ResourceSet
  - Global Readiness Check

## Route53 Application Recovery Controller Cell Components

`./templates/ArcCellResources.yaml`

**Must be deployed into us-east-1**

Deployed once per cell into us-east-1 and creates cell specific components including:

- Route53 Arc
  - Resource Sets
  - Readiness Checks
