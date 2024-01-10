Terraform Module to provision an EC2 Instance that is running Apache 

Not intended for production use. Just showcasing how to create a module on Terraform Registry 

```hcl
terraform {
}

provider "aws" {
  region = "us-east-1"
}
module "apache" {
  source          = ".//terraform-aws-apache-e"
  vpc_id          = "vpc-vpc_id"
  public_key      = "public_key"
  instance_type   = "t2.nano"
  my_ip_with_cidr = "My_own_ip"
  server_name     = "Apache Example Server"
}

output "public_ip-2" {
  value = module.apache.public_ip
}

```