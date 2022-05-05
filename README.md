# aws_interactions

!aws s3 sync . s3://bucket_level1/ncc_scaleup_new/testing/

the above command copies current directory to the s3 bucket. And it keeps in sync with the s3 whenever we run this command. Advantage is no need to copy individual files.
