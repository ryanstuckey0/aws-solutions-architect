# 157- S3 Access Logs
- Can set up access logging to be logged into another S3 bucket
	- Will log request made to S3 from accounts, whether authorized or denied
- Target logging bucket must be in same AWS region

## Logging Loop
- It is possible to set logging bucket to be the monitored bucket
- This will cause bucket to grow exponentially
