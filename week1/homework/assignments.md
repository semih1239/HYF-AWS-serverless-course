## Mandatory assignments

**Assignment 1:**

What is an ARN: Amazon Resource Names (ARNs) uniquely identify AWS resources. We require an ARN when you need to specify a resource unambiguously across all of AWS, such as in IAM policies, Amazon Relational Database Service (Amazon RDS) tags, and API calls.

**ARN formats are like** 
arn:partition:service:region:account-id:resource-id
arn:partition:service:region:account-id:resource-type/resource-id
arn:partition:service:region:account-id:resource-type:resource-id

**Assignment 2:**

Response from the command: 
2022-09-08 14:15:29 cf-templates-1bwydt64uswun-us-east-1
2022-09-08 14:12:11 hyf-week1-cli-asd123asd
2022-09-08 14:11:31 hyf-week1-console-asd123asd


**Assignment 3:**

Command to upload file with the AWS CLI: aws s3 cp \hello-world.txt s3://hyf-week1-cf-hyf-week1/

Command to create a presigned URL: aws s3 presign s3://hyf-week1-cf-hyf-week1/hello-world.txt (gets automatically 1 hour time)

Command to delete your bucket with the AWS CLI: 
aws s3 rb s3://hyf-week1-console-asd123asd --force
aws s3 rb s3://hyf-week1-cli-asd123asd --force

Can you simply delete a CloudFormation bucket? : 
I got "This bucket is not empty" error. I opened to "empty bucket configuration" and I permanently delete all objects.
I was able to delete it after that.

**Assignment 4 (Optional):**

Command to deploy your CloudFormation template using the AWS CLI:
touch assignment4.yaml  => I created file and copied template informations in file

aws cloudformation create-stack --stack-name assigment4 --template-body file://assignment4.yaml ==> for create stack

aws cloudformation describe-stacks --stack-name assigment4 (I checked the stack)

{
    "Stacks": [
        {
            "StackId": "arn:aws:cloudformation:us-east-1:391619197373:stack/assigment4/ea487560-343d-11ed-8deb-0afb579200ad", 
            "DriftInformation": {
                "StackDriftStatus": "NOT_CHECKED"
            }, 
            "Tags": [], 
            "EnableTerminationProtection": false, 
            "CreationTime": "2022-09-14T15:00:04.939Z", 
            "StackName": "assigment4", 
            "NotificationARNs": [], 
            "StackStatus": "CREATE_COMPLETE", 
            "DisableRollback": false, 
            "RollbackConfiguration": {}
        }
    ]
}

aws s3 ls ==> 2022-09-14 15:00:14 hyf-week1-cf-assigment4  (I checked s3 bucket and it is created)