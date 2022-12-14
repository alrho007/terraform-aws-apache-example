Terraform module to provision EC2 Instance running an Apache server.

Not intended for production, only to showcase how to create custom modules in Terraform registry.

### Apache Module Example

```hcl
terraform {
  
}

provider "aws" {
  region  = "us-east-1"
}

module "apache" {
    source = ".//terraform-apache-module"
    vpc_id = "vpc_00000000"
    my_ip_cidr = "MY_IP_ADDRESS/32"
    public_key    = "ssh-rsa AAAAB..."
    instance_type = "t2.micro"
    server_name   = "ApacheServer"
}

output "public_ip" {
  value = module.apache.public_ip
}

```
