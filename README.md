terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "ap-southeast-1"
  access_key = "AKIAVBRYWJEMOWKO6HWT"
  secret_key = "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"
}

resource "aws_instance" "app_server" {
  ami           = "ami-091a58610910a87a9"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}
