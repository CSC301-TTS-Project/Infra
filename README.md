# Infrastructure
This repository contains the migration cloudformation template. It contains pipeline and deployment related resources.
It expects the aws account to already contain an AWS Secrets Manager Secret instance with the following values:

* MAPBOX_PUBLIC_KEY
* HERE_PUBLIC_KEY
* RDS_HOST
* RDS_PASSWORD
* RDS PORT
* RDS_USERNAME
* RDS_TRAFFIC_FINDER_DB
* DDB_ROUTE_TABLE_NAME
* DDB_SEGMENT_TABLE_NAME
* DDB_TEST_ROUTE_TABLE_NAME
* DDB_TEST_SEGMENT_TABLE_NAME
* GITHUB_SECRET

The intended usage is for someone to create their own EB/RDS instances within their own VPC, import them into this stack and do any further network configurations, change the final deployment stage in the backend pipeline to point to the EB instance, then create the stack.

