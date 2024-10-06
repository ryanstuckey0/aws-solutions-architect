# 199- Amazon MQ
-  SQS, SNS are AWS cloud native services
- Existing apps might be using other messaging protocols (MQTT, WSS, etc.)
- When migrating to cloud, might not want to rewrite app for SQS/SNS
- Can us Amazon MQ- managed message broker service for RabbitMQ or ActiveMQ
- Not as scalable as cloud native setups
- Runs on servers, so can run in multi-AZ w/ failover
- Has features from both SQS and SNS (queue and topic)

## Amazon MQ and High Availability
- Have active-passive setup for two MQ brokers
- Need to use and EFS instance mounted to both brokers so that passive instance knows where active instance left off
- 