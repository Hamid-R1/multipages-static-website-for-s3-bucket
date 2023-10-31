# multipages-static-website-for-s3-bucket
- multipages-static-website-for-s3-bucket-


### Prerequisite
- you must have `S3 bucket` with `Static website hosting' enabled & also `bucket policy` for public access.

### See how to clone this repo & copy `source codes` into `S3 bucket`
```
# clone repo for source code
git clone https://github.com/Hamid-R1/multipages-static-website-for-s3-bucket.git

# change directory
cd multipages-static-website-for-s3-bucket/

# check all contents
ls
contact.html  css/  fonts/  images/  index.html  js/  LICENSE  README.md  topics-detail.html  topics-listing.html


# copy all contents (except .git, LICENSE, README.md) from currect directory to S3 Bucket
aws s3 sync . s3://demo-static-multi-123/ --exclude ".git" --exclude "LICENSE" --exclude "README.md"
	#here '.git' folder is also uploaded, solution is delete all objects in S3 bucket & againg upload
	 via below command.

aws s3 cp . s3://demo-static-multi-123/ --recursive --exclude ".git" --exclude "LICENSE" --exclude "README.md"
	#here again '.git' folder is uploaded, so solution is before uploading, manually delete '.git' folder
	 then upload all objects, see below:

rm -rf .git/

aws s3 sync . s3://demo-static-multi-123/ --exclude "LICENSE" --exclude "README.md"
```

