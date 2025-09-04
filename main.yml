provider "aws" {
  region = var.region
}

resource "aws_instance" "web" {
  ami           = var.ami_id
  instance_type = var.instance_type

  tags = {
    Name        = "actions-demo"
    Environment = var.region
    Team        = "Group-4"
    Project     = "Sonatype_Nexus"
  }
}

variable "region" {}
variable "ami_id" {}
variable "instance_type" {}

output "public_ip" {
  value = aws_instance.web.public_ip
}

terraform {
  backend "s3" {
    bucket = "kaizen-abigail"
    key    = "terraform.tfstate"
    region = "us-east-1"
  }
}
