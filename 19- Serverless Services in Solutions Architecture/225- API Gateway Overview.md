# 225- API Gateway Overview
- How can we build a serviceless API?
- Can create REST APIs in API Gateway that proxies request through AWS services
- Provides useful feature like auth, etc.
- Features-
	- AWS Lambda + API gateway means no infra to manage
	- Support for WebSocket Protocol
	- Suports API versioning
	- Can handle multiple environments
	- Auto configure and handle security
	- Create API keys
	- Handle throttling for users
	- Import APIs via Swagger
	- Validate requests/responses
	- Generate SDK and API specs
	- Cache API responses

## High Level Integrations
- Lambda Functions
- HTTP
	- Can access an internal HTTP API on prem, Application Load Balancer
	- Can do this to take advantage of features like throttling, API keys, caching, etc.
- Other AWS Services
	- Expose any AWS service

## Example: API Gateway with Kinesis Data Streams
- Want to have people send data through KDS
- Don't want to give them access to AWS account
- Can send requests through API gateway that sends data to Kinesis Data Streams -> Firehose -> S3

## Endpoint Types
- Three ways
- Edge optimized
	- accessible from anywhere in world
	- routed through Edge locations
	- API gateway itself still only lives in one location
- Regional
	- Used for clients in same region
	- Could manually combine with CloudFront, giving you more control over the Edge optimized verion
- Private
	- Can only be access from your VPC using an interface VPC endpoint (ENI)
- Use resource policy

## API Gateway Security
- Can authenticate users via:
	- IAM Roles (useful for internal users/applications)
	- Cognito (for external users)
	- Custom authorizers (Lambda function)
- Can enable HTTPS through integration with AWS Certificate Manager
	- If using edge optimized API Gateway, then cert must be in us-east-1
	- If using regional, then cert must be same region as API Gateway
	- Must also setup a CNAME or A-alias record in Route 53
