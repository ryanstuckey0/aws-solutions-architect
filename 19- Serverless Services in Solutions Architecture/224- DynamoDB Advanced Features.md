# 224- DynamoDB Advanced Features
## DynamoDB Accelerator (DAX)
- Fully managed, highly available in-memory cache for DynamoDB
- Helps solve read congestion by caching
- Latency is in the microseconds
- DAX Cluster is compatible with existing DynamoDB APIs- no need to change application
- Cache default TTL is 5 minutes
- Why use this instead of ElastiCache?
	- DAX is better for pulling the same raw data over and over
	- ElastiCache is better if we want to store processed/aggregated data

## DynamoDB Stream Processing
- Ordered stream of item-level modifications (create, update, delete)
- Use cases- react to changes in real time, usage analytics, cross-region replication, invoke AWS Lambda
- Two types
	- DynamoDB Streams
		- 24 hour retention
		- Limited # of consumers
		- Connect to AWS Lambda, or DynamoDB Stream Kinesis Stream adapter
	- Kinesis Data Streams (newer)
		- 1 year retention
		- Can have a lot of consumers
		- Connect to many AWS services- Lambda, Kinesis Data Analytics, Kinesis Data Firehose, etc.
- Potential architecture: ![](attachments/Pasted%20image%2020241012154701.png)

## Global Table
- Table replicated across multiple regions
- Two-way replication- can write to either table
- Allows DynamoDB to be used in multiple regions w/ low latency
- Must enable DynamoDB Streams as a pre-req (uses this underneath the hood to replicate)

## DynamoDB TTL
- Can set up to auto-delete items after an expiry timestamp
- Define TTL- items will expire according to TTL, then get deleted
- Use case- only keep current items, adhere to regulatory retention periods, track web sessions

## DynamoDB DR
- Has continuous backups with point in time recovery
- Enabled by default for last 35 days
- Recovery process creates a new table
- On demand backups are also available
	- Backups are retained long time unless manually deleted
	- Configured and managed in AWS Backup (can also backup to other regions)

## DynamoDB and S3
- Can export a table into S3 (must enabled PITR)
- Might want to export to S3 to run Amazon Athena
- Doing an export does not affect performance/read capacity
- Can be used to retain snapshot for audits
- Can export as a JSON or ION format
- Can also import from S3 into DynamoDB using CSV, JSON, ION
	- Does not consume write capacity