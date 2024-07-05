# 91- Amazon Aurora
- Aurora is proprietary AWS (not open source)
- Compatible with postgres and MySQL
- Very cloud optimized- 5x performance over MySQL on RDS, and 3x performance over Postgres on RDS
- Automatically grows, starting at 10GB and in increments of 10GB, up to 128 TB
- up to 15 replicas, and replication is very fast (<10ms of lag)
- Failover is instantaneous and it is highly available by design
- About 20% more than other RDS 

## High Availability and Read Scaling
- Auto-stores 6 copies of data across 3 AZ
	- 4/6 copies needed for reads
	- 3/6 copies needed for writes
	- Self healing with P2P replication
	- Storage is striped across 100s of volumes
Example- data is stored across multiple AZ: [image](Pasted image 20240704204313.png)

- One Aurora instance handles writes, failover from master happens in less than 30 seconds
- Can have master + up to 15 read replicas
	- Any one of read replicas can become master
	- Replicas support cross-region replicas

## Aurora DB cluster
- Master instance is the only one that can write to storage
- AWS provides a **writer endpoint**, that will auto move to correct master instance even through failovers
- Read replicas can also be setup with autoscaling
- **Reader endpoint**- one endpoint that load balances between all replicas; happens per connection, not per statement / query
[image](Pasted image 20240704204617.png)

## Features of Aurora
- Auto failover
- backup and recovery
- easy autoscaling
- Zero downtime patching
- Restore data at any point in time. **backtrack**; doesn't rely on backups, uses other methods