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

Further VPC network configuration may need to be done, and role permissions may need to be adjusted to allow the Elastic Beanstalk instance access to the RDS instance depending on the existing stack.
This stack uses Github V1 sources for pipelines, but our current dev pipeline uses v2. This is because v2 is not supported in cloudformation yet/there is no documentation for it.
See: https://docs.aws.amazon.com/codepipeline/latest/userguide/appendix-github-oauth.html

