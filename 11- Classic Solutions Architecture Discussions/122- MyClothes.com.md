# 122- MyClothes.com
- People buy clothes online
- Shopping cart
- Hundreds of users at a time
- Want to scale horizontally while also keeping our app as stateless as possible
- Users should not lose shopping cart when scaling
- Save details (e.g., address, etc.) in database

## Stateful Web App
- route users -> Route 53 -> ELB -> ASG -> EC2 instances (multi AZ)
- Users are having problems where their cart is not persisting
- Need to introduce session affinity (stickiness) on ELB
- If EC2 instance goes down **shopping cart is still lost** 

## User Cookies
- Instead of on EC2 instances, store cart in cookies on user machine
- Cart contents are no longer dependent on EC2 instance
- Achieve stateless status
- HTTP requests are bigger now though with cookies being sent
- Also, cookies can open vulnerabilities, which means EC2 instances need to validate cookie contents
- Cookies are also 4kb max

## Server Session
- Instead of sending whole shopping cart, send session ID
- Session info will be stored in ElastiCache
- All EC2 instances will pull data from ElastiCache
- Could also use DynamoDB
- Store user data in Amazon RDS

## Scaling user reads
- Users are reading to database to pull product info more often than they are writing
- Solution is to scale read replicas
- Could also user lazy loading- look first in cache, if not there pull from DB and then put into cache
- Reduces traffic on RDS, but need figure out cache maintenance

## Disaster Strikes
- Switch RDS and ElastiCache (Redis) to be multi-AZ

## Security Groups
- Allow all HTTP/HTTPS traffic on all IP
- Allow only traffic to EC2 instances from ELB instance