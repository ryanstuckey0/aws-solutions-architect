# 188- Amazon Simple Notification Service (SNS)
- What if you want to send one message to many receivers?
- Can use pub-sub (publich-subscribe) model to implement this
- Interested parties can subscribe to publiches on their own free well
- Event producer sends messages to one SNSN topic
- Up to 12.5 million subscribers can listen to one topic
- Subscribers will receive all messages sent to topic, although a new filter feature has been added
- SNS subcribers- email, SMS, HTTP endpoints, SQS, Lambda, Kinesis Data Firehose
- SNS can receive data from a lot of AWS services- CloudWatch, Lambda, etc.
## How to publish
- AWS has topic publish SDKs available
- Or Direct Publish (for mobile apps SDK), for push notifications

## Security
- Similar to SQS- includes inflight and at rest, as well as clients implementing their own encryption
- Can also regulate access via IAM policies or SNS Access Policies
- 