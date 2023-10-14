### Create Lambda Function. IAM role using AWS CLI and Cloudformation

Change the ff placeholders:
* s3-bucket
* stack-name
* pipeline-name
* email
* bucket-name
* repo-name
* branch-name
* codebuild-name
* repo-https-url

## Create
aws cloudformation package --template-file infrastructure/capstone-6/main.yml --output-template-file tmp/capstone-6.yml --s3-bucket `s3-bucket` --s3-prefix deployment-packages 

aws cloudformation deploy --template-file tmp/capstone-6.yml --stack-name `stack-name` --capabilities CAPABILITY_NAMED_IAM CAPABILITY_AUTO_EXPAND CAPABILITY_IAM  --parameter-overrides CodePipelineName=`pipeline-name` Email=`email` BucketName=`bucket-name` RepositoryName=`repo-name` BranchName=`branch-name` CodeBuildName=`codebuild-name` CodeCommitHTTPSUrl=`repo-https-url`

## Delete
aws cloudformation delete-stack --stack-name `stack-name`