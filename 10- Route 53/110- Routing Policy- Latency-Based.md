# 110- Routing Policy- Latency-Based
- Redirect to resource w/ lowest latency
- Combine w/ health checks for failover capability
![](attachments/Pasted%20image%2020240706133937.png)

## Creating latency-based records in console
- Need to specify region for policy (AWS doesn't determine region based on IP address we put in)
- Create another record with same name, and of type latency, with a different region