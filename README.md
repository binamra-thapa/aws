# aws
Flow -> 
1. Terraform -> build vms
2. Ansible -> Configure the vms
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
gateway 
s3
dynamodb  or auroradb
vpc 
subnet 
loadbalancer 


awsConcepts
IAM
