# 123- MyWordPress.com
- We are working on creating full scalable word press website
- Website needs to be able to access and display picture uploads
- User data and blog contents will be stored in MySQL DB

## First Steps
- Create Route 53 -> ELB -> EC2 instances -> Database
- Aurora MySQL, Multi-AZ, Read replicas

## Storing Images
- Can use EBS volumes
- User sends image through ELB -> EC2 instance -> EBS volume
- Problems arise when we start scaling
- Image might get sent to one instance but then user connects to another instance the next time

### Using EFS
- Use same architecture, switch EBS to EFS
- Create ENI into each AZ (elastic network interface)
- Storage is shared between all instances