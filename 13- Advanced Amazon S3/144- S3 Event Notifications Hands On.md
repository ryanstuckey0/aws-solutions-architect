# 144- S3 Event Notifications Hands On
- Under bucket properties, scroll down to event notifications
- Can create event notification, or enable Amazon EventBridge
- Creating event notification
	- Provide name, prefix and suffix (if desired)
	- Choose event types (what will trigger the event? put, post, etc.)
	- Choose where to publish event- Lambda function, SNS topic, SQS queue
		- Need to authorize resource to allow S3 to publish events into that destination
			- If you don't authorize, AWS will let you know before you save the event
			- After enabling, a test message is sent to SQS to make sure it can receive messages
