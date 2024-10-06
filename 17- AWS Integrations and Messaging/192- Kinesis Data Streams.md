# 192- Kinesis Data Streams
- Made of multiple shards
	- Each is provisioned ahead of time
	- Data is split across shards; defines stream capacity and consumption rates
- Producers send data into KDS
	- could be applications, SDK, Kinesis agent (on server)
	- produce records to send to streams- made of partition key, and data blob (up to 1MB)
	- Partition key determines which shard record goes to
	- Producers can send up to 1MB/sec or 1000 messages/sec/shard
- Consumers then read data from KDS
	- Could be apps (via SDK), Lambda, Kinesis firehose, Kinesis Data Analytics
	- Consumed records contain partition key, sequence #, and data blob
	- Can consume up to 2MB/sec/shard or 2MB/sec/shard/consumer (enhanced consumer mode)
- Configuration
	- Retention can be between 1-365 days
	- Cab also replay data
	- Once data is inserted into Kinesis, it is immutable
	- Data shares the same partition goes to the same shard
	- Producers- AWS SDK, Kinesis Producer Library (KPL), Kinesis Agent
	- Consumers- Kinesis Client Library (KCL), AWS SDK, AWS Lambda, Kinesis Data Firehose, Kinesis Data Analytics

## Capacity Modes
- Provisioned mode (traditional)
	- Choose number of shards, and then scale manually or via A{PI
	- Each shards can do 1MB/s or 1000 message/s input
		- And can output 2MB/s
	- Costs is per shard per hour
- On-demand mode (new)
	- Do not provision or manage cacacity
	- Receive default capacity (4MB/s or 4000 records per second)
	- Then scales automatically based on observer throughput in the last 30 days
	- Pay per stream, per hour and data in and out per GB
	- More expensive- so best if you don't know capacity yet

## Security
- Kinesis is deployed within region
- Use IAM policies
- Inflight using HTTPS, at rest using KMS
- Can also implement your own encryption
- VPC endpoints are available to access Kinesis within VPC