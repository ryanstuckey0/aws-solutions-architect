# 82- Connection Draining
- CLB- called connection draining
- ALB/NLB- deregistration delay
- Gives time to complete in-flight requests while de-registering instance or it is becoming unhealthy
- Also stops sending new requests to instance (avoids draining instance)
- Can customize duration (1-3600 seconds, default = 300)
	- Can be disabled by setting to 0 seconds
- Set to low value if requests are short