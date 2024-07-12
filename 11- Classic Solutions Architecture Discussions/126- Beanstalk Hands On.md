- Choose web server or worker env
- Specify app name
- Specify application env
- Choose platform- programming language, version, etc.
- Application code- choose sample application, existing version, or new code
- Presets- several choices like single instance, high availability, custom config
	- Also allows you to use on-demand or spot instances

## Security Groups
- Go to IAM -> new Role -> AWS Service -> EC2 -> Permissions
	- Permissions- filter on beanstalk, add web tier, worker tier, and multicontainer Docker
	- Name role, fill out in beanstalk console

## Resource formation
- Beanstalk creates events, which creates stacks in Cloud Formation
- In template tag, can see JSON document that provisions resources
- Can view health checks
- domain name gives access to beanstalk env (sample app, or code), which points to underlying EC2 instances
- Can then update app version and scale as needed
- Delete app from beanstalk console, which will delete all associated resources
- 