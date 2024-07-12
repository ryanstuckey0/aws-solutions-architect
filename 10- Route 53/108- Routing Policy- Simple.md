# 108- Routing Policy- Simple
- Defines how route 53 responds to DNS queries
- Not associated with traffic, just with DNS queries
- Route 53 supports policies- simple, weighted, failover, latency based, geolocation, multi-value answer, geoproximity

## Simple Routing Policy
- Route traffic to single resource
- Can specify multiple values in record- Route 53 returns all and client randomly picks one
- With Alias, only supports one AWS resource
- No health checks
- 