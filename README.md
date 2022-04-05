Notes in running/on-boarding  Windows Based Tomcat services on AWS Infrastructure

AWS

Environment Standup

- Account
	- You will need to have access to an Amazon Web Services (AWS) Account with the appropriate permissions to create the underlying environment. This can be an Amazon Identity and Access Management (IAM) User or IAM Role with the appropriate policies to create the environment. If you do not have an AWS Account, you can either ask the AWS administrator for your organization to create an account for you. 
	- For this guide, we will be administering the AWS environment with AWS Cloud 9, a cloud based development environment that runs in AWS, but this can also be accomplished from a local machine or an  EC2 instance. 
- Tooling 
	- There are a few tools available for setting up and operating container based infrastructure on AWS. I am recommending using the AWS Cloud Development Kit (CDK) for setting up and maintaining and infrastructure as code baseline. In order house AWS CDK, we need to install the AWS CDK CLI
	- https://aws.amazon.com/getting-started/guides/setup-cdk/module-two/
		- npm install -g aws-cdk
		- cdk --version
		- aws sts get-caller-identity
		- cdk bootstrap aws://ACCOUNT-NUMBER/REGION
	- Create a new CDK app
		- https://aws.amazon.com/disaster-recovery/when-to-choose-aws-drs/?cloud-endure-blogs.sort-by=item.additionalFields.createdDate&cloud-endure-blogs.sort-order=desc 
- Docker Registry and ECR
	- When building Docker Images, they are stored locally by default. Storing the container image in a private yet available manner is desirable and therefore we recommend using Amazon ECR private registry.
	- An Amazon ECR private registry hosts your container images in a highly available and scalable architecture. You can use your private registry to manage private image repositories consisting of Docker and Open Container Initiative (OCI) images and artifacts. Each AWS account is provided with a default private Amazon ECR registry
Build
- Docker
