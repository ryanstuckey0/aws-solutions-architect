# 134- S3 Versioning Hands On
- Go to properties and enable version
- Can toggle show versions in objects tab
	- Version ID is unique string of numbers and letters
- how can we rollback using versions?
	- Click on version ID, delete object
- Deleting the last version does not delete it, but just adds a delete marker to the object
	- So need to click show versions to see a version ID on a object of type delete marker
	- To restore a file, we need to delete its delete marker