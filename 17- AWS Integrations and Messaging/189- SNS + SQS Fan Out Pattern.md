# 189- SNS + SQS Fan Out Pattern
- Let's say you want a message sent to multiple SQS queue- but this could cause problem if app crashes before message is sent to all SQS
- Instead, publish to SNS topic, which then sends to multiple SQS Queues
	- app -> SNS -> SQS Queues -> Consumers
- Need to allow SNS to write to SQS queue in the SQS queue access policy

## S3 Events into multiple queues
- For the same combination of event type (i.e., create, delete, etc.) and the prefis (i.e., images/), there can only be one S3 event rule
- Can send the event to SNS queue, then fan out to SQS queues, lambda functions, etc.

## Kinesis Data Firehose (KDF)
- KDF can receive data directly from SNS topic

## SNS FIFO
- can enable FIFO in SNS 
- has same features as SQS- ordering, dedup

## SNS Message Filtering
- JSON policy that can be used to filter messages sent to SNS topics
- Each subscription can define its own filter policy
- Can then have SQS queues to process all different types of messages  