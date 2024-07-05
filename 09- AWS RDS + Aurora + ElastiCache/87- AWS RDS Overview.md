# 87- AWS RDS Overview
- RDS is AWS's Relational Database Service
- Uses SQL
- Available DB
	- Postgres
	- MySQL
	- MariaDB
	- Oracle
	- MS SQL Server
	- IBM DB2
	- Aurora (AWS's own RDB)
- Why use RDS over deploying DB on EC2?
	- AWS auto provisions DB, OS, patching
	- Automatically makes continuous backups, and restore from timestamp
	- Monitor dashboards
	- Read replicas for improved performance
	- Multi-AZ setup for DR
	- Scaling
	- Storage backed up EBS (gp2 or io1)
	- Can't SSH into instances

## Storage Auto Scaling
- Allows you to dynamically increase storage on DB instance
- Scales automatically when it detects you're running out of free space
- Need to set a maximum storage threshold
- Auto scale storage if:
	- Free storage is less than 10% of allocated storage
	- Low-storage lasts at least 5 minutes
	- 6 hours have passed since last modification
- Supports all DB engines