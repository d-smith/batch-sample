# batch-sample

Sample of batch set up for running jobs using fargate.

In flight...

## Stacks

### IAM

aws cloudformation create-stack  \
--stack-name iam4batch \
--capabilities CAPABILITY_NAMED_IAM \
--template-body file://resources/batch-iam.yml

aws cloudformation update-stack  \
--stack-name iam4batch \
--capabilities CAPABILITY_NAMED_IAM \
--template-body file://resources/batch-iam.yml

aws cloudformation describe-stacks \
--stack-name iam4batch \
--query 'Stacks[0].StackStatus'

aws cloudformation delete-stack \
--stack-name iam4batch

### VPC

aws cloudformation create-stack  \
--stack-name vpc4batch \
--template-body file://resources/vpc.yml

aws cloudformation describe-stacks \
--stack-name vpc4batch \
--query 'Stacks[0].StackStatus'


aws cloudformation describe-stacks \
--stack-name vpc4batch \
--query 'Stacks[0].Outputs[*]'


aws cloudformation delete-stack \
--stack-name vpc4batch