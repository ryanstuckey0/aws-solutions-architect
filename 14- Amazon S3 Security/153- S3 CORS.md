# 153- S3 CORS
- CORS = Cross Origin Resource Sharing
- Origin = scheme/protocol + host/domain + port
	- so https://ww.example.com, implied port = 443
- Web browser based mechanism to allow requesting to locations other than the main one you're visiting
- When trying to make a request to another origin, it will be denied unless a CORS header is present
- Other origin (not main origin) has to specify if it allows requests from main origin
	- It can also allow only specific HTTP method (e.g., GET, PUT, DELETE)
![](attachments/Pasted%20image%2020240716214350.png)

## How does this apply to AWS S3?
- If client makes a cross-origin request on our S3 bucket, we need to enable correct CORS header
- Could use start * to allow all origins
- One example could be if a bucket is configured as a static website and that website references objects in another bucket
![](attachments/Pasted%20image%2020240716214527.png)
