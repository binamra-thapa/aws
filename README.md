# aws
Flow -> 
1. Terraform -> build vms
2. Ansible -> Configure the vms
    a. Task to install exporters on ec2 instance
3. CodePipeline -> For the ci/cd -> Triggered automatically when a change is pushed.
    a. build. 
    b. run test cases
    c. sonarscan
    d. veracode 
    e. build image
    f. deployment
4. CloudWatch for resource metrics
5. Docker for image and DockerHub or Amazon Elastic Container Registry (ECR)

Includes 
ec2
ebs
elk 
eks or ecs
IAM 
VPC (Virtual Private Cloud) -> Acts as an abstraction from the outside world
    1. Create a vpc. Example: vpc-flask-app
    2. Input a cidr range. Example: 192.168.0.0/16 -> This contains 65536 ip's 
Subnet -> These are subset's of vpc. Usually we create private and public subnets spread across two availability zones
    1. Create a public subnet. Example: public-subnet 
    2. Select the az
    3. Input the cidr range. Example: 192.168.0.1/24 -> This contains 255 ip's 
    4. Create a private subnet. Example: private-subnet
    5. select the az
    6. Input the cidr range. Example: 192.168.0.2/24
Internet Gateway -> provides access from the internet to the subnets(public subnet)
    1. Create a gateway, give it a name. Example gateway-flask-app
    2. Attach the Gateway to the vpc created earlier. Example: vpc-flask-app
Route Tables(Stateless) -> Used for routing traffic after it enters through the internet gateway -> All inbound and outbound traffic is allowed by default
    1. Create route tables. By default there will be a main route table when a vpc is created, that allows access within all the subnets of the vpc
    2. Create a public route table. Exmaple: flask-public-route
    3. Attach the vpc to this route table
    4. Creates rules for the route table ie. From(destination) and To(target)
    5. Since this is a public-route it should be from public-subnet to gateway-flask-app
    6. Associate the public subnets to this route table.
s3
dynamodb  or auroradb

loadbalancer 
network acl's 
fargate 
lambda function
