# aws_interactions

**!aws s3 sync . s3://bucket_level1/bucket_level2/testing/**

the above command copies current directory to the s3 bucket. And it keeps in sync with the s3 whenever we run this command. Advantage is no need to copy individual files.

copy file to s3 Bucket:
**!aws s3 cp 'data_processing.ipynb' s3://bucket_level1/bucket_level2/testing/**
