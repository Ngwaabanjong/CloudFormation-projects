# Deploy VPC, EC2 with CloudFormation in simple learning steps.
# INTRODUCTION
An AWS CloudFormation template is a JSON or YAML formatted text file that describes your AWS infrastructure. 
- To make it simple I will create a file for every section but the main.yml will have the complete template.

# What will be done
We will create a 2 tier VPC and its components.
We will create a security group
We will create an ec2 instance in the VPC.

# Prerequisites:
Install AWS CLI
Configure IAM access to AWS

# 1 Version - version.yml file
FORMAT VERSION:
	• Optional: but recommended 
	• Defines the version of template we are working on
	• "2010-09-09"

# 2 Description - description.yml
DESCRIPTION:
	• Optional
	• It helps to describe the resources or the workload

# 3 Metadata - metadata.yml
METADATA:
	• Optional
	• It is use to place JSON or YAML objects that provide additional details about the template.
	• Some CloudFormation features use this section to retrieve settings. For example, "AWS::CloudFormation::Interface" key for ordering and grouping parameter.
    • The metadata uses parameter groups to label parameters per resource.
	• After setting parameter group you need to set parameter labels for certain resources like subnets.

# 4 Parameters - parameters.yml
PARAMETERS:
	• Optional
	• It is used to pass values in runtime, while creating and updating stacks.
	• Increase reusability of the template.
	• Parameters can be referenced from "Resources" and "Outputs" sections.
    • Parameters uses Type to define the value type.
    • Different type of values are, String, Number, CommaDelimitedList, Resource Types, etc...

# 5 Mapping - mappings.yml
MAPPINGS:
    • Mappings (optional)
    • A mapping of keys and associated values that you can use to specify conditional parameter values, similar to a lookup table. 
    • You can match a key to a corresponding value by using the Fn::FindInMap intrinsic function in the Resources and Outputs sections.

# 5 Resource - 5a-vpc.yml, 5b-subnets.yml 5c-routetables.yml, 5d-internetgw.yml, 5e-subnetassociations.yml, 5f-ec2.yml, 5g-securitygrp.yml
RESOURCES:
	• Only required section.
	• It is used to define AWS resources and their properties launch by the template.

# 6 Output - 6-output.yml
OUTPUTS:
	• Optional.
	• It is used to define output values for a stack, for instance DNS hostname of an ELB
	• Outputs can be viewed on AWS Management Console or in the response of AWS CLI calls.
	• In advance level, they can be used to create cross-stack reference and pass values between nested stacks.

***************************************************************************************************************

#  Conditions - this will not be used in this template.
CONDITIONS:
	• Optional
	• It used to define the statements which describes conditions under a resource can be created or configured.
    • The conditions evaluate to true or false based on the values of these input on the parameters. 

TRANSFORM:
	• OPTIONAL
	• AWS Serverless Application Model (SAM) is model based on AWS CloudFormation and used to define serverless applications on AWS.
    • Transform sections is used to specify the AWS SAM version used.


