# 121- WhatsTheTime.com
- Stateless app- allows people to know what time it is
- No database, start small, accept downtime
- Scale vertically, horizontally, remove downtime

## Starting from the Beginning
- Public EC2 instance, tells user what time it is
- Use elastic IP

## Scaling- Vertical
- More users start using app- traffic increases
- Start out on T2 micro instance, but need to scale vertically to M5 instance
- Same public IP, since it has elastic IP
- Users not happy during downtime while upgrading to M5 though

## Scaling Again- Horizontal
- Tons of users all accessing single elastic IP
- Add several more instances, but each have their own elastic IP
- But now, users also need to remember each IP address, and we need to manage infrastructure

## Dealing with IPs
- Switch to DNS on route 553, A record
- Use TTL = 1 hour
- Need to deal with instances being remove, going down, etc.
- TTL is long, so if EC2 instance goes away, then IP address doesn't update

## Adding load balancer
- Switch EC2 instances to private, same AZ
- Place ELB + health checks in front
- DNS can no longer use A record since load balancer IP is constantly changing
- Switch to alias record

## Auto Scaling Group
- Still need to manually add and remove instances as traffic scales up and down
- Add ASG to manage instances for us based on demand

## Availability
- Earthquake in AZ, entire AZ goes down, which means entire app goes down
- Switch ELB to be multi-AZ- 3 AZ total
- ASG also switched to span across several AZ

## Capacity Reservation
- Start wanting to save money by reserving capacity
- We know 2 instances must be running at all times, so reserve instances
- Save money

## 5 pillars of well architected application
- cost, performance, reliability, security, operational excellence