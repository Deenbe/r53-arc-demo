# Route53 Application Recovery Controller Demo
This is still very much a work in progress, please contact jonesaws@amazon.com with questions and/or feedback.

## Prerequisites
Public Route53 domain

## CloudFormation Components
## ./templates/3tier_single_az_self_contained_web.yaml
Application template, deployed into both Sydney and Singapore regions.  The template deploys the following basic application architecture:

![Application Architecture](./images/r53_Arc_demo.png)

## ./templates/Route53-arc.yaml
Shared components, deployed into us-east-1, including:

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



## ./templates/ArcCellResources.yaml
Deployed once per cell into us-east-2
