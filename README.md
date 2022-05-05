# aws_interactions

**!aws s3 sync . s3://bucket_level1/bucket_level2/testing/**

the above command copies current directory to the s3 bucket. And it keeps in sync with the s3 whenever we run this command. Advantage is no need to copy individual files.

copy file to s3 Bucket:
**!aws s3 cp 'data_processing.ipynb' s3://bucket_level1/bucket_level2/testing/**
syntax: 


good reference: https://bobbyhadz.com/blog/aws-s3-copy-local-folder-to-bucket

**Copying a file from S3 to S3
**
The following cp command copies a single s3 object to a specified bucket and key:

aws s3 cp s3://mybucket/test.txt s3://mybucket/test2.txt
**Output:**

copy: s3://mybucket/test.txt to s3://mybucket/test2.txt

**Copying an S3 object to a local file
**
The following cp command copies a single object to a specified file locally:

aws s3 cp s3://mybucket/test.txt test2.txt

**Output:
**

download: s3://mybucket/test.txt to test2.txt
Copying an S3 object from one bucket to another

The following cp command copies a single object to a specified bucket while retaining its original name:

aws s3 cp s3://mybucket/test.txt s3://mybucket2/
Output:

copy: s3://mybucket/test.txt to s3://mybucket2/test.txt
Recursively copying S3 objects to a local directory

When passed with the parameter --recursive, the following cp command recursively copies all objects under a specified prefix and bucket to a specified directory. In this example, the bucket mybucket has the objects test1.txt and test2.txt:

aws s3 cp s3://mybucket . --recursive
Output:

download: s3://mybucket/test1.txt to test1.txt
download: s3://mybucket/test2.txt to test2.txt
Recursively copying local files to S3

When passed with the parameter --recursive, the following cp command recursively copies all files under a specified directory to a specified bucket and prefix while excluding some files by using an --exclude parameter. In this example, the directory myDir has the files test1.txt and test2.jpg:

aws s3 cp myDir s3://mybucket/ --recursive --exclude "*.jpg"
Output:

upload: myDir/test1.txt to s3://mybucket/test1.txt
Recursively copying S3 objects to another bucket

When passed with the parameter --recursive, the following cp command recursively copies all objects under a specified bucket to another bucket while excluding some objects by using an --exclude parameter. In this example, the bucket mybucket has the objects test1.txt and another/test1.txt:

aws s3 cp s3://mybucket/ s3://mybucket2/ --recursive --exclude "another/*"
Output:

copy: s3://mybucket/test1.txt to s3://mybucket2/test1.txt
You can combine --exclude and --include options to copy only objects that match a pattern, excluding all others:

aws s3 cp s3://mybucket/logs/ s3://mybucket2/logs/ --recursive --exclude "*" --include "*.log"
Output:

copy: s3://mybucket/logs/test/test.log to s3://mybucket2/logs/test/test.log
copy: s3://mybucket/logs/test3.log to s3://mybucket2/logs/test3.log
