# 97- ElasticCache Overview
- ElastiChache is used to get managed Redis or Memcached
- Helps reduce load off DB
- Helps make application stateless
- AWS takes care of OS, optimizations, monitoring, etc.
- Using ElastiCache will involve heavy applications code changes

## Solution Architecture Examples
### DB Cache
- Application queries ElastiCache instead of getting it from DB
- Needs to read from DB if not available in DB
- Then, write to cache so same query is available next time
- Need to have cache invalidation to make sure data in there is current
![[Pasted image 20240704223147.png]]

### User Session Store
- user will log into anyone of supported applications
- application will then write session info to cache
- other applications can retrieve this session info when user switches apps

## ElastiCache- Redis vs Memcached

### Redis
- Multi-AZ
- Auto failover
- Scaled via read replicas- high availability
- Data durability using AOF persistence
- Backup and restore features
- Supports sets and sorted sets

### Memcached
- Multi-node for partitioning of data
- no replication = no high availability
- non persistent
- no backup and restore
- multi-threaded focus

### Summary
Redis = high availability, important data we'd rather not lose
Memcached = high performance, data can be lost
![[Pasted image 20240704223748.png]]