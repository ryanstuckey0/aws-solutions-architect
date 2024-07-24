# 169- Cache Invalidations
- if you update the back-end origin, CloudFront won't know this and will wait until TTL expires before pulling new content
- You can force an entire or partial cache refresh with a CloudFront Invalidation
- Can include all files or exclude files using different paths
- 