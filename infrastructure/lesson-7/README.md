# Lesson 7

### Create Lambda Function. IAM role, API Gateway, DynamoDB using AWS CLI and Cloudformation


Feel free to change `lessonSevenStack` as the stack name and `lessonsevenlambda` parameter value for your lambda function name.

## Create
aws cloudformation package --template-file infrastructure/lesson-7/main.yml --output-template-file tmp/lesson-7.yml --s3-bucket pcloud-lessonsixs3-dev --s3-prefix deployment-packages 

aws cloudformation deploy --template-file tmp/lesson-7.yml --stack-name lessonSevenStack --capabilities CAPABILITY_NAMED_IAM  --parameter-overrides LambdaFunctionName=lessonsevenlambda S3ObjectUrl=https://pcloud-lessonsixs3-dev.s3.amazonaws.com/deployment-packages/api.zip

## Delete
aws cloudformation delete-stack --stack-name lessonSevenStack