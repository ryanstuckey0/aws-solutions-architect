# 143- S3 Event Notifications
- Various actions in buckets will trigger events- object created, object remove, replicaed, etc.
- Can filter on object names
- Can create as many events as desired
- Events are typically delivered to destination immediately, but sometimes might take a couple minutes
	- Could send to SNS, SQS, or lambda function

## IAM Permissions
- Need to create SNS, SQS, and Lambda policies attached to each so that S3 can access those services  ![](attachments/Pasted%20image%2020240714131922.png)

## S3 Event Notifications with EventBridge
- All events go from S3 to EventBridge, no matter what
- Can setup rules to send events/trigger things in over 18 AWS services as desinations
- Also can use advanced filtering options via JSON rules
- Can also send to multiple destinations
- EventBridge also supports things like archive, replay events, and reliable delivery

