# infrastructure

All CloudFormation templates should be in this repository.

## Usage

1. `aws configure`
2. `export AWS_PROFILE=demo`
3. `export AWS_REGION=us-east-1`
4. cloudformation
   + `aws cloudformation create-stack --stack-name=myVPC --template-body=file://vpc.yml`
   + `aws cloudformation create-stack --stack-name=myVPC3 --template-body=file://vpc.yml --parameters ParameterKey=VpcCidrBlock,ParameterValue="10.1.0.0/16" ParameterKey=Subnet1CidrBlock,ParameterValue="10.1.0.0/24" ParameterKey=Subnet2CidrBlock,ParameterValue="10.1.1.0/24" ParameterKey=Subnet3CidrBlock,ParameterValue="10.1.2.0/24"`
   + `aws cloudformation create-stack --stack-name=myVPC4 --template-body=file://vpc.yml --parameters ParameterKey=VpcCidrBlock,ParameterValue="10.1.0.0/16" ParameterKey=Subnet1CidrBlock,ParameterValue="10.1.0.0/24" ParameterKey=Subnet2CidrBlock,ParameterValue="10.1.1.0/24" ParameterKey=Subnet3CidrBlock,ParameterValue="10.1.2.0/24" ParameterKey=Subnet1AZ,ParameterValue="us-east-1a" ParameterKey=Subnet2AZ,ParameterValue="us-east-1b" ParameterKey=Subnet3AZ,ParameterValue="us-east-1c"`

> : your account may have AZ less than 2 in a region

Show AZ available to you account

`aws ec2 describe-availability-zones --region us-west-2`

## clean up:
`aws cloudformation delete-stack --stack-name myVPC2`
