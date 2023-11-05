# AWS CLOUDFORMATION PROJECTS
Every project has a Readme.md documentation and most projects are on my website and YouTube.

## CLI COMMANDS
Deploying Stack:
```
aws cloudformation create-stack --stack-name C9-test --template-body file://c9-stack.yml --capabilities CAPABILITY_NAMED_IAM
```
Deploying Stack with User profile and parameter file:
```
aws --profile default cloudformation create-stack --stack-name c10-stack --template-body file://C10.yaml --parameters file://C10.parameters --capabilities CAPABILITY_NAMED_IAM
```

