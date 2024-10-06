# 197- Data Ordering for Kinesis vs SQS FIFO
- For Kinesis Data Streams, we can hash inputs into shards based on some key, ensuring data can be read in order from each shard
- For SQS FIFO, if we do not have a group ID, we can only ave one consumer to ensure data is never processed out of order
	- We can increase efficiency by adding a group ID to each message, and then assign consumers to each group
	- 