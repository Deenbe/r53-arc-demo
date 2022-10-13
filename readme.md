# Route53 Application Recovery Controller Demo
This is still very much a work in progress, please contact jonesaws@amazon.com with questions and/or feedback.

## Prerequisites
Public Route53 domain

## CloudFormation Components
## ./3tier_single_az_self_contained_web.yaml
Application template, deployed into both Sydney and Singapore regions

## ./Route53-arc.yaml
Shared Route53 components, deployed into us-east-1

## ./ArcCellResources.yaml
Deployed once per cell into us-east-2
