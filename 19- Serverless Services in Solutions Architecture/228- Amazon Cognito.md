# 228- Amazon Cognito
- Gives a user an identity to access application
- Usually these are external users who do not sign into AWS
- Cognito User Pool
	- Provides sign in functionality for app users
	- Tight integration w/ API Gateway, ALB
- Cognito Identity Pool (Federated Identity)
	-  Provide temporary AWS credentials to users so they can access AWS resources directly
	- Integrates w/ Cognito User Pools as an identity provider
	- Cognito vs IAM- Cognito is better for hundreds of users, mobile users, or authentication via SAML

## Cognito User Pools (CUP)
- Serverless database of users for apps
- Simple login- username, email
	- Has password resets, email/phone # verification, MFA, integration w/ other accounts (FB, Google, etc.)
- CUP integrates w/ API Gateway and ALB
- Auth flow
	- w/ API Gateway: ![400](attachments/Pasted%20image%2020241012163558.png)
	- w/ ALB: ![400](attachments/Pasted%20image%2020241012163701.png)

## Cognito Identity Pools (Federated Identities)
- Provides identities for users so they can obtain temporary AWS credentials
- User source can be Cognito user pools, 3rd party logins, etc.
- Users can then access AWS service directly in console or through API gateway
- The IAM policies are defined in Cognito and then apply to these temporary credentials
- There are some default IAM roles for users
- Example architecture: ![](attachments/Pasted%20image%2020241012164055.png)

- Use Case- Row Level Security in DynamoDB
	- can define leading key for DynamoDB based on their Cognito identity