# 94- AWS Aurora- Backup and Monitoring
## RDS Backups
- Auto backups
	- Daily- RDS will do full daily backup of DB during backup window
	- 5 minutes- Transaction logs are backed up every 5 minutes
	- So can restore to any point in time (from oldest backup, up to 5 minutes ago)
	- And save 1 to 35 days of backups
- Manual backups
	- Triggered by user
	- Can retain for as long as you like
- Trick: if you don't need your database for sometime, take a snapshot, delete the database, and then restore it later when you need it again
	- this is cheaper because you still pay for a stopped RDS DB

## Aurora Backups
- Automated backups
	- 1-35 days
	- Cannot be disabled
	- Exact point in time recovery
- Manual backups- same as RDS

## RDS and Aurora Restore Options
- Restoring from a backup or snapshot creates a new database
- Restoring a MySQL RDS database from S3
	- Create backup of on-prem database
	- Send it to S3
	- Restore the backup file onto new RDS instance running MySQL
- Restoring a MySQL Aurora cluster from S3
	- Create backup of on-prem database using Percona XtraBackup (**only option**)
	- Store backup file on S3
	- Restore onto new Aurora cluster running MySQL

## Aurora Database Cloning
- Create new Aurora DB cluster from existing one
- Faster than snapshot & restore
- Uses copy on write protocol
	- Initially, DB clone will be using same data volume as original DB cluster
	- As updates are made, additional storage is allocated, data is copied and separated
- Very fast and cost-effective