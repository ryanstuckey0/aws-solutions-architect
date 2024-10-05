# 175- Amazon FSx
- Launch 3rd party file systems on AWS as a fully managed service
- Examples- Lustre, Windows File Server, NetApp ONTAP, OpenZFS

## FSx for Windows File Server
- Fully managed Windows file system shared drove
- Supports SMB protocol and NFTS
- Supports MS Active Directory integration, ACLs, user quotas
- Can be mound on Linux EC2 instances
- Supports Microsofts Distributed File System (DFS) namespaces
	- Lets you group files across multiple file systems
- Highly scalable- 10s GB/s, millions of IOPS, 100s PB of data
- Storage options
	- SSD- low latency, fast access
	- HDD- better for static workloads (home directory)
- Can be accessed from on-prem infra (via VPN or AWS Direct Connect)
- Con be configured to be Multi-AZ
- Data is backed up daily to S3

## FSx for Lustre
- Lustre is a parallel distributed file system used for large scale computing
- Lustre = Linux + cluster
- Useful for machine learning, HPC
- Also offers SSD or HDD
- Full integration with S3- can read from and write to S3 as a native file system
- Can also be used with on-prem servers

### File System Deployment Options
- Scratch- temporary storage
	- Data is not replicated if server fails
	- High bursts (6x faster, 200 MBps / TB)
	- short-term processing, optimize costs
	- Used for processing temporary data, lower costs
- Persistent- replicated within same AZ\
	- Long-term storage
	- Replaces failed files within minutes
	- Used for long term processing, sensitive data

## FSx for NetApp ONTAP
- File system that is compatible with NFS, SMB, iSCSI protocols
- Used to move workloads running in ONTAP or NAS to AWS
- Works with- Linux, Windows, MacOS, VMware Coud on AWS...
- Storage auto-scales up and down
- Can also de-dup data
- Instantaneous cloning of a file system at a single point in time
	- Can be used to test new workloads

## FSx for OpenZFS
- Compatible only with NFS
- Works with wide variety of OS
- Up to 1M IOPS w/ <0.5ms latency
- Offers snapshots, compression, all at low cost
- Also offers instant cloning at point in time