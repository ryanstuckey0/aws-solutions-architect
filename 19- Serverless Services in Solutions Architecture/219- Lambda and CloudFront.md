# 219- Lambda and CloudFront
- Many modern apps execute some form of logic at the edge locations from which it distributes content to end users
- Idea here is we want to run functions closest to user to minimize latency
- CloudFront provides two types- CloudFront Functions and Lambda@Edge
- Use cases
	- website security and privary
	- dynamic web apps
	- search engine optimization
	- route across origins and data centers
	- bot miitgation
	- user tracking and analytics

## CloudFront Functions
- Typical CloudFront request:
  ![200](attachments/Pasted%20image%2020241009070801.png)
  - Lightweight functions written in JavaScript
  - Useful for high scale, latency sensitive operations
  - Start up in only a few ms, millions of requests/second
  - Used to change viewer request and response from above picture
  - Native feature of CloudFront- all code managed within CloudFront

## Lambda@Edge
- Functions written in NodeJS or Python
- Scales to thousands of requests/second
- Used to change viewer request/response and origin request/response
- Functions are authored in one region, then CloudFront will replicate to all its locations
- Differences:![](attachments/Pasted%20image%2020241009071154.png)

## Use Cases
- CloudFront Functions
	- Cache key normalization
	- Header manipulation
	- URL rewrites/redirects
	- Request auth (i.e., create tokens)
- Lambda@Edge
	- Access to 3rd party libraries
	- Network access to access external services
	- File system access (in /tmp)
	- Access body of HTTP requests