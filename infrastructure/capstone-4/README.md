# Lesson 6

### S3 Bucket creation


Feel free to change `pcloudDynamoDBStack` as the stack name and `TableName` parameter value for your table name.

## Create
aws cloudformation create-stack --stack-name pcloudDynamoDBStack --template-body file://infrastructure/capstone-4/main.yml --parameters ParameterKey=TableName,ParameterValue=pcloudDynamoDb ParameterKey=Email,ParameterValue=test@gmail.com

## Delete
aws cloudformation delete-stack --stack-name pcloudDynamoDBStack