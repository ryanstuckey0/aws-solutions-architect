## Requesting Spot Fleet
- Can use launch template or configure launch parameters manually
- Can link EC2 instances to load balancer
- Set target capacity- # of instances in fleet, vCPUs, or GB of RAM
- Can choose interruption behavior- terminate, hibernate, or shut down
- Select instance types, or specific attributes that meet reqs (# CPU, GB RAM, etc.)
	- can then preview the matching instance types
- Ending gives # of matching instances, rating on fleet strength, est'd cost / hour

## Requesting Spot Instance
- Go to EC2 -> scroll down -> select advanced -> request spot instance
	- price is capped by default at on-demand price, but can specific max price manually
- Can set other details like request type (persistent/one-time), interruption behavior, etc.

## Reserved Instances
- Can purchase reserved instance of specific type
- Can be standard or convertible instance
- Pay upfront or no upfront
- Reserved instances might be going away in favor of savings plan

## Savings plan
- Flexible pricing where you can specify an amount for a set amount of usage

## Dedicated Hosts
- Recommends using license manager now, which automatically allocates hosts for you based on your licenses

## Capacity Reservations
- Ensure capacity of a specific instance type is available when needed
- Can set an end time