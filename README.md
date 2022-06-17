# Open Search SIEM Sandbox (OS3)

An all-in-one CloudFormation template that will deploy an AWS Native security log analytics playground!

This consists of:
- A Kinesis Firehose for data ingestion
- A small OpenSearch instance to explore the data

Access is only permitted from the same public IP from which you deployed.

## Deploying

With AWS creds in your terminal and the AWS CLI installed, simply:

```
aws cloudformation deploy --template-file template.yaml \
    --stack-name os3 \
    --region us-east-1 \
    --parameter-overrides MyIPAddress=`curl icanhazip.com` \
    --capabilities CAPABILITY_NAMED_IAM
```

## Handy One Liners

Validate the template (if you need to make changes):
`aws cloudformation validate-template --region us-east-1 --template-body file://template.yaml`

Clean up and remove everything:
`aws cloudformation delete-stack --stack-name os3 --region us-east-1`
