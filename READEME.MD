Project Files
/cloudformation-stacks:
network-params.json: Parameters file for network cloudformation stack.
network.yml: CloudFormation template for creating networking resources for this project.
servers-params.json: Parameters file for servers cloud formation stack.
servers.yml: CloudFormation template for creating servers for this project.
s3-bucket: It contain the main html file of the application and upload status screenshot.
/scripts: This folder contains script to create, delete and update CloudFormation stack
/workflow-screenshots: This folder contain screenshots of whole workflow status
udagram-infrastructure-diagram.png: This shows visual aid to understand the CloudFormation script.
Project Setup
To create networking resources using cloudformation template, run the below command. After exceuting it these are the resources created:
VPC
Subnets
Route Tables
Routes
Internet Gateway
NAT Gateways
$ scripts/create.sh webapp-network-stack network.yml network-params.json
To create servers resources using cloudformation template which pulls source code from S3 bucket automatically while starting, run the below command. After exceuting it these are the resources created:
Security Groups
IAM Role, Policy, Instance Profile
Launch configuration
Auto Scaling Group
Load Balancer
Target Group
$ scripts/create.sh webapp-server-stack server.yml server-params.json
Once the above steps are complete, you can find the URL of application in the outputs section of udagram-servers-stack CloudFormarion stack.