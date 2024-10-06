# 207- ECS Cleanup
- Deleting service will trigger all created dependencies to also be deleted; can see this in CloudFormation
- Same applies when deleting cluster
- Task definitions don't cost money; can still delete it by deregistering it