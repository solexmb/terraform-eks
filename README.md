SELF MANAGE EKS CLUSTER [worker node]

Infrastructure as a code [IaC]

This terraform code is used to provision 3 self managed worker nodes[eks]

Instructions

>> Make sure to have terraform, AWS CLI, and kubectl installed

>> Generate an "ACCESS KEY AND SECRET KEY" on aws

>> Open a terminal and run the following commands
    aws configure # this will prompt for your aws access key and secrete key 

>> Clone the repo

>> change directory into the cloned repo # cd terraform-eks

>> Create a file named terraform.tfvars # touch terraform.tfvars 

>> Declare the following values in the terraform.tfvars
    vpc_cidr_block = "" # VPC block example of vpc block --> 10.0.0.0/16 
    private_subnet_cidr_blocks = ["", "", ""] # 3 private subnet block
    public_subnet_cidr_blocks = ["", "", ""]  # 3 public subnet block

>> terraform init # This will initialise terraform, install the provider and modules used
>> terraform plan # see list of resources to be created
>> terraform apply -auto-approve # This will take about 10 - 15 minutes to complete the provisioning of eks

   # this create the kubeconfig file and set the region to eu-west-2
>> aws eks update-kubeconfig --name myapp-eks-cluster --region eu-west-2

