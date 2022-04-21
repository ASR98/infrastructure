# infrastructure

# AWS CLI installation
1. Install AWS-CLI as mentioned here: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
2. Configure profile in aws-cli as mentioned in https://docs.aws.amazon.com/cli/latest/userguide/getting-started-quickstart.html
3. Run aws ec2 describe-vpcs and check vpc properties
4. Clone the git repo and inside infrastructure folder, run
    aws cloudformation create-stack --profile dev --stack-name sample --template-body file://csye6225-infra.yml --parameters ParameterKey=VpcCidrBlock,ParameterValue="10.0.0.0/16" ParameterKey=Subnet1CidrBlock,ParameterValue="10.0.1.0/24" ParameterKey=Subnet2CidrBlock,ParameterValue="10.0.2.0/24" ParameterKey=Subnet3CidrBlock,ParameterValue="10.0.3.0/24"
   To run in a different region,
    aws --region us-east-2  cloudformation create-stack --profile dev --stack-name sample --template-body file://csye6225-infra.yml --parameters ParameterKey=VpcCidrBlock,ParameterValue="10.0.0.0/16" ParameterKey=Subnet1CidrBlock,ParameterValue="10.0.1.0/24" ParameterKey=Subnet2CidrBlock,ParameterValue="10.0.2.0/24" ParameterKey=Subnet3CidrBlock,ParameterValue="10.0.3.0/24"

5. To delete the created stack, run
    aws cloudformation delete-stack --stack-name sample

Note: You can replace 'sample' and Parameter Values with required values.

aws acm --profile demo import-certificate --certificate fileb:///mnt/d/prod_sriratnaakkineni_me/prod_sriratnaakkineni_me.crt --certificate-chain fileb:///mnt/d/prod_sriratnaakkineni_me/prod_sriratnaakkineni_me.ca-bundle --private-key fileb:///mnt/d/prod_sriratnaakkineni_me/server.key\
