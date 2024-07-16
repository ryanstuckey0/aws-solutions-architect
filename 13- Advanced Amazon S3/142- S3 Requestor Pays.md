# 142- S3 Requestor Pays
- Generally, bucket owners will pay themselves for all storage and access costs associated with bucket
- You can setup a requestor pays bucket, meaning the requestor will pay the access costs (owner still pays for storage)
- Useful for sharing large amounts of data with other accounts
- When enabled, requestor must be non-anonymous (i.e., authenticated in AWS)