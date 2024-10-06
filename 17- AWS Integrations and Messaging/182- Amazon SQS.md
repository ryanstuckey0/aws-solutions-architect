# 181- Amazon SQS
- Producer(s) will produce messages to the SQS queue
- Consumer(s) will pull messages from queue; each queue will process one unique message
- Amazon SQS (Standard Queue) is the oldest offering- fully mangaged services
- Attributes and limitations
	- Allows unlimited throughput, no limit on messages in queue
	- Messages will stay in queue for 4 days, max of 14 days
	- Very low latency (<10 ms)
	- Message size is limited to 256KB
- Messages can be duplicated (at least once delivery)
- Messages can be out of order (best effort ordering)

## Producing Messages
- Producer sends message up to 256KB
- Uses Amazon's SDK (SendMessage API)
- Message is persisted in SQS until consumer deletes it

## Consuming Messages
- Consumers can run in AWS (EC2 instances, AWS lambda) or in on-prem apps
- Consumer polls SQS for messages- an receive up to 10 at a time
- Consumer then processes the message and deletes message after consuming
	- Deleting message assures no other consumers consume the same message

### Multiple Consumers
- Consumers can poll and process images in parallel
- If message is not processed fast enough by one consumer, it is possible another consumer will read the same message
- If there are too many messages, we can scale consumers horizontally
- SQS w/ Auto Scaling Groups
	- Can set up AutoScaling group to scale based on queue length (Cloud Watch metric)

## SQS Security
- Encryption
	- In flight encryption using HTTPS
	- At rest encryption via KMS keys
	- Clients can also manually implement encryption on their end
- Access controls
	- IAM policies can be used to regulate access to the SQS API
	- Also has SQS Access Policies (similar to S3 bucket policies)
		- Useful for allowing cross-account access
		- Or allowing other services to access queue
