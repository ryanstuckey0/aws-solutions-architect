# 88- RDS Read Replicas vs Multi AZ
- Read replicas helps to scale the number of reads
- Create up to 15 replicas
- Can be within AZ, cross AZ, or cross region
- Replication is async, so reads will **eventually** be consistent
- Application must update connection string to utilize read replicas
- Replicas can be promoted to their own DB

## Use Cases
- Useful for other apps that want to run reports or analytics on data- they can read from read replica

## Networking Cost
- Normally, there is a cost when data moves across AZ
- For RDS read replicas, there is no charge for data that moves cross-AZ
	- As long as AZs are in same region
- Cross region replicas will incur data movement fees

## RDS Multi AZ
- Have primary instance in AZ #1, and standby in AZ #2
- Application talks to single DNS name, and DB will auto-failover to standby DB in the background
	- No need to include both instances on connection string
- Standby instance is not a read replica, just for standby
- Can multi-AZ read replicas be used as DR instances? yes

## RDS from single AZ to multi-AZ
- zero downtime operation
- just need to modify the database and enabled multi-AZ
- The following happens behind the scenes
	- Snapshot taken of main DB
	- Snapshot is then restored in standby DB
	- Synchronization is then enabled from primary to standby database