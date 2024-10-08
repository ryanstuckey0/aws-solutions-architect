# 195- Kinesis Data Firehose Hands On
- Ingest from producers, (optionally) transform data via Lambda function, Load into desired destination
	- S3, Redshift, OpenSearch
	- Dynatrace, Splunk, Datadog
- Sources can include Kinesis Data Streams
- Can transform output using other preset options (in additino to Lambda)
- Choose destination- S3 bucket, Redshift, etc.
- Also enable/disable dynamic partitioning
- Can also add prefix for S3 data
- Can use buffer size to accumulate data before sending into target (5MiB default), can go up to 128 MiB
- Buffer interval- if buffer size doesn't fill up, how often should we flush it (60-900 seconds, default 300)
- Enable/disable compression (can select compression method) & encryption (KMS)
- Can also auto-create IAM role that can be assigned to write into S3
- When using a Kinesis data stream as a source, only new records will be sent through the Kinesis Fire Hose
- 