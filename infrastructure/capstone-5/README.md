### Create Lambda Function. IAM role using AWS CLI and Cloudformation

Change the ff placeholders:
* s3-bucket
* stack-name
* fn-name
* https-zip-url
* dynamo-db-table-name

## Create
aws cloudformation package --template-file infrastructure/capstone-5/main.yml --output-template-file tmp/capstone-5.yml --s3-bucket `s3-bucket` --s3-prefix deployment-packages 

aws cloudformation deploy --template-file tmp/capstone-5.yml --stack-name `stack-name` --capabilities CAPABILITY_NAMED_IAM CAPABILITY_AUTO_EXPAND CAPABILITY_IAM  --parameter-overrides LambdaFunctionName=`fn-name` S3ObjectUrl=`https-zip-url` TableName=`dynamo-db-table-name`

## Delete
aws cloudformation delete-stack --stack-name `stack-name`