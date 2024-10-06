# 209- Amazon EKS
- EKS = elastic kubernetes service
- open source container management system
- Similar goal to ECS
- Supports both EC2 and Fargate Launch modes
- use case- lift and shift from k8s on prem to k8s in AWS
- K8s is considered cloud-agnostic (i.e., cross cloud)
![](attachments/Pasted%20image%2020241006094708.png)

## Node Types
- Managed node groups
	- Creates and manages nodes (EC2 instances) for you
	- Nodes are part of ASG
	- Supports on -demand or spot EC2 instances
- Self managed notes
	- Managed by user
	- Can use prebuilt AMI
- Or can use Fargate and not have to worry about nodes

## Data Volumes
- Need to specify storage class on EKS cluster
- Uses Container Storage Interface (CSI) compliant driver
- Supports- EBS, EFS (**only one support by Fargate**), FSx for Lustre, FSx for NetApp ONTAP