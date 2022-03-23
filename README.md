# infrastructure

All CloudFormation templates should be in this repository.

## Usage

1. `aws configure`
2. `export AWS_PROFILE=demo`
3. `export AWS_REGION=us-east-1`
4. cloudformation
   + `aws cloudformation create-stack --stack-name=myVPC --template-body=file://vpc.yml --parameters=file://params.json --capabilities CAPABILITY_IAM`

   ``` bash
   aws cloudformation create-stack \
   --stack-name=myVPC \
   --template-body=file://vpc.yml \
   --parameters \
   ParameterKey=KeyPair,ParameterValue="aws"
   ```

> : your account may have AZ less than 2 in a region

Show AZ available to you account

`aws ec2 describe-availability-zones --region us-west-2`

## clean up:

> Need to disable termination protection first!

```
aws ec2 modify-instance-attribute \
   --instance-id=i-0d907d630fa643970 \
   --no-disable-api-termination
```

delete all objects

`aws s3 rm s3://bucket-name --recursive`

`aws cloudformation delete-stack --stack-name myVPC`
