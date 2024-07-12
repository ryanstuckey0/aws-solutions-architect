- Used to route traffic to multiple resources
- Can be associated with health checks- so only healthy resources are returned
- Up to 8 records returned
- **Not a substitute for ELB**, more like a client-side load balancer
- Similar to simple routing policy, but a simple policy **does not allow health checks**

## Setting up in console
- Create multiple records, set health checks