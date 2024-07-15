# Terraform-ALB-EC2-S3

![1](https://github.com/user-attachments/assets/e0126f9f-2c95-42ca-9fee-9b26e23e29cb)

### Install AWS CLI 

First, install the AWS CLI, as it will be required to run the aws configure command to connect Terraform with AWS in next steps.

To Install AWS CLI on Linux.
```
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

### Install Terraform

Next, To Install Terraform on Ubuntu/Debian
```
$ wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```

### Connect Terraform with AWS

Its very easy to connect Terraform with AWS. Run `aws configure` command and provide the AWS Security credentials.

### Initialize Terraform

Clone the repository and execute 
```
$ terraform init
```

This command will initialize the Terraform environment, downloading the necessary providers, modules, and configurations needed for your setup.

### Review the Terraform Configuration

```
$ terraform plan
```

To preview the changes that will be made by the configuration.

### Create the infrastructure

```
$ terraform apply
```

This will apply the configuration and create an AWS infrastructure with a VPC, public subnets, an Application Load Balancer (ALB), two EC2 instances running Apache web servers, and an S3 bucket.

### Verify the Setup

```
    ALB: The Application Load Balancer will distribute traffic between the two EC2 instances.
    EC2 Instances: Two instances will be launched in separate public subnets, with user data scripts to set up Apache servers.
    S3 Bucket: An S3 bucket will be created for storage.
```
