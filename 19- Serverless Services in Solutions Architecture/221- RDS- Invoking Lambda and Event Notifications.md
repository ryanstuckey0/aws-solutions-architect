# 221- RDS- Invoking Lambda and Event Notifications
## Invoking Lambda from RDS & Aurora
- Can invoke Lambda from within DB instance- supports both PostgreSQL and Aurora MySQL
- Can process data events from within database
- Set up from within database, not in AWS console
- Must allow outbound traffic from DB to Lambda function (via Public, gateway, VPC)
- DB instance must also have required permissions to invoke Lambda functions

## RDS Event Notifications
- These happen within AWS
- Tell info about DB instance itself (created, start, stopped, etc.)
- No info about data in database
- Event categories- DB instance, DB snapshot, DB parameter group, DB security group, RDS Proxy, Custom Engine Version
- Almost real time- up to 5 minute delay
- Notifications can be sent to SNS or EventBridge, then from there send them to SQS, Lambda function, etc.