# AWS Secure Mini Network Infrastructure

## Description

This AWS CloudFormation template sets up a secure, mini network infrastructure on AWS. It provisions a Virtual Private Cloud (VPC), subnets, NAT Gateway, Internet Gateway, Route Tables, Security Groups, and EC2 instances, creating a structured environment for both public and private network segments.

## Features

- **VPC Configuration**: A custom Virtual Private Cloud.
- **Subnetting**: Both public and private subnets.
- **Internet Gateway**: For outbound internet access from instances in public subnets.
- **NAT Gateway**: To allow instances in private subnets to access the internet.
- **Route Tables**: Separate route tables for public and private subnets.
- **Security Groups**: Configured for defining inbound and outbound access rules.
- **EC2 Instances**: Instances in both public and private subnets.

## Prerequisites

- An AWS Account.
- An existing EC2 KeyPair for SSH access (default: 'cloudformation').
- Basic understanding of AWS services like VPC, EC2, and CloudFormation.

## Parameters

- `MyKeyPair`: The name of an existing EC2 KeyPair.
- `MyIP`: Your IP address range for SSH access.

## Resources

- `MyVPC`: The main Virtual Private Cloud.
- `PublicSubnet` and `PrivateSubnet`: Subnets for different access levels.
- `InternetGateway` and `GatewayToInternet`: To connect the VPC to the internet.
- `PublicRouteTable` and `PrivateRouteTable`: Route tables for managing network routes.
- `NATGateway` and `NATGatewayEIP`: NAT Gateway for outbound internet access from private subnets.
- Various `SecurityGroups`: For fine-grained access control.
- EC2 Instances: `JumpBoxInstance`, `PrivateInstance1`, `PrivateInstance2`, `PublicInstance1`, `PublicInstance2`.

## Usage

1. **Upload the Template**: Upload this CloudFormation template to the AWS CloudFormation console.
2. **Set Parameters**: Customize parameters like KeyPair and IP ranges.
3. **Create Stack**: Execute the template to create the stack.
4. **Access Instances**: Use the JumpBoxInstance for accessing private instances.

## Outputs

- `JumpBoxPublicIP`: The public IP address of the jump box instance for SSH access.

## Additional Information

- Modify the template as needed to fit more specific requirements.
- Always ensure your security groups are as restrictive as necessary to maintain a secure environment.

## Disclaimer

It is recommended to test in a non-production environment first.
