# Lesson 6

### S3 Bucket creation


Feel free to change `pcloudS3Stack` as the stack name and `BucketName` parameter value for your bucket name.

## Create
aws cloudformation create-stack --stack-name pcloudS3Stack --template-body file://infrastructure/capstone-3/main.yml --parameters ParameterKey=BucketName,ParameterValue=pcloudS3 ParameterKey=Email,ParameterValue=test@gmail.com

## Delete
aws cloudformation delete-stack --stack-name pcloudS3Stack