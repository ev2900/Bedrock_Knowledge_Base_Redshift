# Bedrock Knowledge Base with Redshift
<img width="275" alt="map-user" src="https://img.shields.io/badge/cloudformation template deployments-1-blue"> <img width="85" alt="map-user" src="https://img.shields.io/badge/views-008-green"> <img width="125" alt="map-user" src="https://img.shields.io/badge/unique visits-003-green">

Amazon Bedrock Knowledge Bases incorporate into your existing data stores and provide LLM query generation and natural language question, answer. Knowledge bases are offered for both structures and unstructured data.

Knowledge bases for structured data work with Amazon Redshift.

The following architecture depicts the key components. Including the additional metadata that can be added to enrich a knowledge base.

<img width="700" alt="quick_setup" src="https://github.com/ev2900/Bedrock_Knowledge_Base_Redshift/blob/main/README/kb_architecture.png">

The outputs a knowledge base offer include generatequery, retrieve and retrieve and generate

* *generatequery* will convert a natural language question into a SQL query that can be run on Redshift
* *retrieve* will convert a natural language question into a SQL query, run the query on Redshift and return a table of the results
* *retrieve and generate* will convert a natural language question into a SQL query, run the query on Redshift and return the results to an LLM to generate an answer to your question using the data returned from Redshift

## Example

You can test Bedrock Knowledge base integration with Redshift. Begin by deploying the CloudFormation stack below. This will create the required AWS resources.

> [!WARNING]
> The CloudFormation stack creates IAM role(s) that have ADMIN permissions. This is not appropriate for production deployments. Scope these roles down before using this CloudFormation in production.

[![Launch CloudFormation Stack](https://sharkech-public.s3.amazonaws.com/misc-public/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=redshift-kb&templateURL=https://sharkech-public.s3.amazonaws.com/misc-public/bedrock_knowledge_base_redshift.yml)

### Sync the Knowledge Base

Syncing the knowledge base allows bedrock to connects to Redshift, reads table and column metadata, embeds + indexes it into the knowledge base’s vector store so it can be used during generation and retrieval.

To sync the knowledge base navigate to the bedrock page on the AWS console, then knowledge bases.

Select the pre-deployed **redshift-knowledge-base** and click *Sync*

<img width="700" alt="quick_setup" src="https://github.com/ev2900/Bedrock_Knowledge_Base_Redshift/blob/main/README/sync.png">

### Test via. the AWS Console

You can test the knowledge base via. the built in AWS console interface. Click *Test Knowledge Base*

<img width="700" alt="quick_setup" src="https://github.com/ev2900/Bedrock_Knowledge_Base_Redshift/blob/main/README/test_1.png">

You can now use this interface to test the knowledge base

<img width="700" alt="quick_setup" src="https://github.com/ev2900/Bedrock_Knowledge_Base_Redshift/blob/main/README/test_2.png">

## Planned Improvements
1. Bulk SQL insert statements to load the table data. The CloudFormation stack currently uses 1 insert per row, which is less efficient
