# infrastructure

All CloudFormation templates should be in this repository.

## Usage

1. `aws configure`
2. `export AWS_PROFILE=demo`
3. `export AWS_REGION=us-east-1`
4. cloudformation
   + `aws cloudformation create-stack --stack-name=myVPC --template-body=file://vpc.yml`
   + `aws cloudformation create-stack --stack-name=myVPC3 --template-body=file://vpc.yml --parameters ParameterKey=VpcCidrBlock,ParameterValue="10.1.0.0/16" ParameterKey=Subnet1CidrBlock,ParameterValue="10.1.0.0/24" ParameterKey=Subnet2CidrBlock,ParameterValue="10.1.1.0/24" ParameterKey=Subnet3CidrBlock,ParameterValue="10.1.2.0/24"`

## clean up:
`aws cloudformation delete-stack --stack-name myVPC2`
