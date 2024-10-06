# 206- ECS- Solutions Architectures
## Example 1- Process S3 Objects
- ECS Tasks can be invoked by EventBridge![](attachments/Pasted%20image%2020241006093803.png)
- Serverless architecture to process objects from S3 buckets

## Example 2- Run Scheduled Processes
- Could configure schedule in EventBridge to run ECS task every 1 hour ![](attachments/Pasted%20image%2020241006093923.png)
- Useful for batch processing w/ serverless architecture

## Example 3- SQS Queue Example
- Can create tasks that poll for messages, use autoscaling when queue builds up![](attachments/Pasted%20image%2020241006094034.png)

## Example 4- Intercept Stopped Tasks via EventBridge
- Can use EventBridge to figure out when tasks change to stopped state, trigger a notification via SNS, and email admin
