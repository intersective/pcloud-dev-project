# Lesson 7

### Create Lambda Function. IAM role, API Gateway, DynamoDB using AWS CLI and Cloudformation


Feel free to change `lessonSevenStack` as the stack name and `lessonsevenlambda` parameter value for your lambda function name.

## Create
aws cloudformation create-stack --stack-name lessonSevenStack --template-body file://infrastructure/lesson-7/main.yml --parameters ParameterKey=LambdaFunctionName,ParameterValue=lessonsevenlambda


## Delete
aws cloudformation delete-stack --stack-name lessonSevenStack