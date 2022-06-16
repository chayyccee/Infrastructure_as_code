### Project Title - Deploy a high-availability web app using CloudFormation
This folder provides the code for solution for the "ND9991 - C2- Infrastructure as Code - Deploy a high-availability web app using CloudFormation" project on udacity. This folder contains the following files:

#### final-project-starter.yml
Students have to write the CloudFormation code using this YAML template for building the cloud infrastructure, as required for the project.

#### server-parameters.json
Students may use a JSON file for increasing the generic nature of the YAML code. For example, the JSON file contains a "ParameterKey" as "EnvironmentName" and "ParameterValue" as "UdacityProject". 

In YAML code, the `${EnvironmentName}` would be substituted with `UdacityProject` accordingly.

The app is deployed in this [link](https://s3-12345678-bucket.s3.us-west-2.amazonaws.com/index.html) or
[https://s3-12345678-bucket.s3.us-west-2.amazonaws.com/index.html](https://s3-12345678-bucket.s3.us-west-2.amazonaws.com/index.html)

## Task

### Scenario
Your company is creating an Instagram clone called Udagram.

Developers want to deploy a new application to the AWS infrastructure.

You have been tasked with provisioning the required infrastructure and deploying a dummy application, along with the necessary supporting software.

This needs to be automated so that the infrastructure can be discarded as soon as the testing team finishes their tests and gathers their results.

Optional - To add more challenge to the project, once the project is completed, you can try deploying sample website files located in a public S3 Bucket to the Apache Web Server running on an EC2 instance. Though, it is not the part of the project rubric.
Server specs

### Server specs
You'll need to create a Launch Configuration for your application servers in order to deploy four servers, two located in each of your private subnets. The launch configuration will be used by an auto-scaling group.
You'll need two vCPUs and at least `4GB` of RAM. The Operating System to be used is `Ubuntu 18`. So, choose an Instance size and Machine Image (AMI) that best fits this spec.
Be sure to allocate at least 10GB of disk space so that you don't run into issues. 
Security Groups and Roles

### Security Groups and Roles
Since you will be downloading the application archive from an S3 Bucket, you'll need to create an IAM Role that allows your instances to use the S3 Service.
Udagram communicates on the default HTTP Port: `80`, so your servers will need this inbound port open since you will use it with the Load Balancer and the Load Balancer Health Check. As for outbound, the servers will need unrestricted internet access to be able to download and update their software.
The load balancer should allow all public traffic `(0.0.0.0/0)` on port `80` inbound, which is the default HTTP port. Outbound, it will only be using port `80` to reach the internal servers.
The application needs to be deployed into private subnets with a Load Balancer located in a public subnet.
One of the output exports of the CloudFormation script should be the public URL of the LoadBalancer. Bonus points if you add `http://` in front of the load balancer DNS Name in the output, for convenience.

# N.B

This is rough work for the purpose of this project work. Don't pack up the resources like i did.
ensure u separate the resources(network, s3, server, IAM, etc) in different yml and paramter json files for ease. Then 
each resource example for IAM, you have iam.yml and iam-params.json, for s3, you have s3.yml and s3-prams.json. Then you can update as required.