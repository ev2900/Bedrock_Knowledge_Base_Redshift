# Bedrock Knowledge Base with Redshift
<img width="275" alt="map-user" src="https://img.shields.io/badge/cloudformation template deployments-00-blue"> <img width="85" alt="map-user" src="https://img.shields.io/badge/views-000-green"> <img width="125" alt="map-user" src="https://img.shields.io/badge/unique visits-000-green">



## Example

You can test Bedrock Knowledge base intergration with Redshift. Begin by deploying the CloudFormation stack below. This will create the required AWS resources.

> [!WARNING]
> The CloudFormation stack creates IAM role(s) that have ADMIN permissions. This is not appropriate for production deployments. Scope these roles down before using this CloudFormation in production.

[![Launch CloudFormation Stack](https://sharkech-public.s3.amazonaws.com/misc-public/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=redshift-kb&templateURL=https://sharkech-public.s3.amazonaws.com/misc-public/bedrock_knowledge_base_redshift.yml)

### Sync the Knowledge Base

### Test via. the AWS Console

## Planned Improvements
1. Bulk SQL insert statement to load the table data. The CloudFormation stack currently uses 1 insert per row, which is less efficient 
