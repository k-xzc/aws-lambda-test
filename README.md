# aws-lambda-test

## requirement ##
aws cli
terraform

## How to run ##

aws configure
  AWS Access Key ID : ---your accesskey---
  AWS Secret Access Key : ---your secretkey---
  Default region name= ---your region---

terraform init

zip main.js example.zip

aws s3 cp example.zip s3://---youbucket-name---/v1.0.0/example.zip

aws s3api create-bucket --bucket=---youbucket-name--- --region=---your region--- --create-bucket-configuration LocationConstraint=---your region---

export AWS_ACCESS_KEY_ID="---your accesskey---"
export AWS_SECRET_ACCESS_KEY="---your secretkey---"
export AWS_DEFAULT_REGION="---your region---"
terraform plan
terraform apply -var="app_version=1.0.0"

aws lambda invoke --region=---your region--- --function-name=---function-name--- output.txt

zip Compress-Archive app example.zip
aws s3 cp example.zip s3://kant-lambda/v1.0.1/example.zip
terraform apply -var="app_version=1.0.1"
