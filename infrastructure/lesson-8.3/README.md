# Lesson 7

### Setting up AWS Cognito for Authentication


Feel free to change `lessonEightThreeStack` as the stack name.


## Create
aws cloudformation package --template-file infrastructure/lesson-8.3/main.yml --output-template-file tmp/lesson-8.3.yml --s3-bucket pcloud-lessonsixs3-dev --s3-prefix deployment-packages 

aws cloudformation deploy --template-file tmp/lesson-8.3.yml --stack-name lessonEightThreeStack --capabilities CAPABILITY_NAMED_IAM CAPABILITY_AUTO_EXPAND CAPABILITY_IAM  --parameter-overrides AuthStackName=lessonEightThreeAuthStack

## Delete
aws cloudformation delete-stack --stack-name lessonEightThreeStack