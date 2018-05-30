This is a sample project called 'AWS-cloudformation-cloudwatch-lambda-template'. This is to demonstrate using Cloudformation, how to create and configure CloudWatch dashboard to monitor an AWS Lambda function.

# CloudWatch-Lambda
#### This is a sample template which creates a cloudwatch dashboard and add a lambda function trigger


## How to Use

#### Install AWS CLI
[Amazon link for installing AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/installing.html)

#### Configure your CLI
```
[default]
aws_access_key_id = XXXXXXXXXXXXXXXXXXXX
aws_secret_access_key = XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
region = eu-west-2
```

#### Validate your template
``` 
aws cloudformation validate-template --template-body file://./cloudwatch_lambda_sample_config.yaml 
```

#### Create a stack using your template
``` 
aws cloudformation create-stack --stack-name cloudwatch-test-stack --template-body  file://./cloudwatch_lambda_sample_config.yaml 
```

#### Update your stack in-case of any modification on the template
``` 
aws cloudformation update-stack --stack-name cloudwatch-test-stack --template-body  file://./cloudwatch_lambda_sample_config.yaml 
```
___
## Optional way to update stack
#### You can create a change set and execute it for updating the stack from the cloudformation UI.
```
aws cloudformation create-change-set --stack-name cloudwatch-test-stack --template-body file://./cloudwatch_lambda_sample_config.yaml --change-set-name port-update --description "updating the lambda function name"
```
