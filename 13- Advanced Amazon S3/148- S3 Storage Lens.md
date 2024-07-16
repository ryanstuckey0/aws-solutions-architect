# 148- S3 Storage Lens
- Service that lets you analyze and optimize storage across AWS org
- Aggregate data at different levels- org, account, region, bucket, prefix
- Can use default dashboard or create your own dashboard
- Can also export data to reports in S3

## Default Dashboard
- Contains both free and advanced metrics
- Shows multi-region and multi-account data
- Can't be deleted, by can be disabled

## Available Metrics
- Summary metrics
	- General insights about S3 Storage
		- StorageBytes- size
		- ObjectCount
	- Use case- ID fastest growing buckets and prefixes
- Cost-optimization
	- Manage/optimize storage costs
	- Tells you things like how much storage non-current versions are taking, how much incomplete uploads are taking
	- Use case- see how much data is being stored that isn't actually active data
- Data-protection
	- Check which buckets have versioning enabled
	- Use case- ID which buckets don't have good data protection
- Access-management
	- Use case- see object ownership settings
- Event metrics
	- Use case- ID which buckets have event notifications configured
- Performance metrics
	- Use case- See how many buckets have S3 transfer acceleration enabled
- Activity metrics
	- See how storage is requested
- Status Codes
	- See which HTTP status codes are being returned most

## Free vs. Paid
- Some metrics are not free
- Free metrics includes around 28 metrics
	- Data stays available for 14 days
- Paid metrics
	- Advanced metrics
	- CloudWatch publishing
	- Metrics by prefix (prefix aggregation)
	- Data available for 15 months