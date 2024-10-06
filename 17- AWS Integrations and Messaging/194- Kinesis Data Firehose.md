# 194- Kinesis Data Firehose
- Can take data from a wide variety of producers- apps, SDK, Kinesis Agent, Kinesis Data Streams, AWS IoT, CloudWatch
- Can also transform data before reading via Lambda Functions
- Reads records up to 1MB in size
- Handles writing data in batches to destinations
	- Destinations include **AWS S3, AWS Redshift (copied through S3), Amazon OpenSearch**
	- Can also send data to 3rd parties (e.g., Splunk, mongoDB), or custom destinations via HTTP endpoint
	- Can  also additionally send all data (or just failed data) into S3 bucket

## Summary
- Fully managed service- no administration, auto scaling, serverless
- Send data to AWS S3, AWS Redshift, or AWS OpenSearch; or 3rd parties/custom app
- Pay for data flowing through Firehose
- Almost real time- can set buffer between 0-900 seconds
	- And specify buffer size, starting at 1MB
- Can write customer data transformations using Lambda

## Kinesis Data Streams vs Kinesis Fire Hose
- KDS used to ingest data at scale, more customizable for producer/consumer, manage scaling, store data, replay data, store for 1 to 365 days
- Firehose- Auto scaling, fully managed, stream data into S3, RedShift, or OpenSearch, no storage, no replay, near real time