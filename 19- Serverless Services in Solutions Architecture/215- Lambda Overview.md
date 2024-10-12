# 215- Lambda Overview
- Traditional servers (like EC2) are limited by the amount of RAM and CPU that we provision them with
- Scaling means adding/removing servers
- AWS Lambda- virtual functions, no servers to manage
	- Limited by time; runs in short executions up to 15 minutes
	- Run on demand, then terminate after complete
	- Scaling is automated
- Benefits
	- Pricing- pay per request, runtime
	- Free tier- 1M Lambda request, 400k GBs of compute time
	- Works w/ many programming languages
	- Integrate w/ CloudWatch to monitor
	- Can get up to 10GB of RAM per function- CPU and networking scale w/ RAM
	- Supported languages- Node.js, Python, Java, C#, Ruby, or customer Runtime API
	- Lambda Container Images- container must implement the Lambda Runtime API
		- On exam, it is preferred to run containers on ECS/Fargate

## Lambda Integration w/ AWS Services
-  API Gateway- REST API that invokes lambda functinos
- Kinesis- lambda functions to transform data on the fly
- DynamoDB- trigger lambda function when something happens in DB
- S3- run lambda function when an object is added to S3
- CloudFront- Lambda at edge- more info later
- CloudWatch Events, EventBridge- react to things happening across AWS services
- CloudWatch logs- stream logs to desired location
- SNS/SQS- processing notifications / messages in queues
- Cognito- react to user logging into AWS services

## Example- Serverless Thumbnail Creation
- Given an S3 bucket, we want to create thumbnails from files uploaded to it
- We can create a Lambda function that creates thumbnails whenever images are uploaded
- Lambda function can then push thumbnail to S3 or DynamoDB

## Example- Serverless CRON Job
- We create a rule in CloudWatch event that triggers on some schedule, and runs a Lambda function

## Lambda Pricing
- Pay per requests
	- First 1M request are free
	- After that, $0.20 per 1 million requests
- Pay per duration (increments of 1 ms), based on RAM used
	- First 400k GB-seconds of RAM is free (i.e., free to use 1 GB of RAM for 400k seconds)
	- After that, pay $1 for 600k GB-seconds