# 131- Static Web Hosting
- S3 can hot static websites and have them be accssibles
- Website URL will be either
	- http://bucket-name.s3-website-aws-region.amazonaws.com
	- http://bucket-name.s3-website.aws-region.amazonaws.com
- Must have policy attached that allows public access- else will get HTTP 403 Forbidden