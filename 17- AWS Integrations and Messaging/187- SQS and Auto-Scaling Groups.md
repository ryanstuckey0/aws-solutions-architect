# 187- SQS and Auto-Scaling Groups
- Say we have EC2 instances in an ASG, which watches CloudWatch metric Queue Length
- Can set alarm in CloudWatch that triggers auto scale of EC2 instances
- SQS queue can be used as a buffer to ensure database does not get overwhelmed when there are many request coming through
	- This is a common use case
- Can have two microservices- one to enqueue and one to dequeue/write to DB
	- Dequeue microservice will only delete messages from queue after the write to DB is confirmed