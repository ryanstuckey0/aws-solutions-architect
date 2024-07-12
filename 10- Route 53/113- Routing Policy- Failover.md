# 113- Routing Policy- Failover
- Say we have a primary and DR EC2 instance
![](attachments/Pasted%20image%2020240706135910.png)

## Setting Up Failover Health Checks
- Create new record mapped to active instance
- Set policy to failover
- Set failover record type to primary or secondary (for DR instance)
	- And associate health check w/ it
- Add a second record, set failover policy, set to IP of DR instance, and then set record type to secondary
	- Optionally associate health check
- Can check monitoring tab to see when instances became unhealthy
- 