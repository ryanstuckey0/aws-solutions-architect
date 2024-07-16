# 140- S3 Lifecycle Rules (with S3 Analytics)
 - Objects can be transitioned between storage classes
## Lifecycle Rules
- Transition Actions- configure objects to transition to another storage class
- Expiration actions- configure objects to expire/delte after some time
	- Useful to delete log files after some time
	- Delete old versions of files
	- Or delete incomplete multi-part uploads
- Rules can be specified for entire bucket, or only certain prefixes of keys
- Rules can also apply to objects with specific tags
- Scenario: ![](attachments/Pasted%20image%2020240714125623.png)
- Another scenario: ![](attachments/Pasted%20image%2020240714125733.png)

## Amazon S3 Analytics- Storage Class Analysis
- Helps determine when to transition objects to best storage class
- Makes recommendations for standard and standard IA
- Takes 24-48 hours after analytics are enabled, then updates daily