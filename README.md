# EC2 Instance with Elastic IP

This project will be used to create an EC2 Instance using Terraform with Elastic IP associated with it.

## Getting Started
create a .tf file with below instructions 

provider "aws" {
  profile    = "default"
  region     = "us-east-1"
  shared_credentials_file = "/Users/satgaur/.aws/credentials"
}

resource "aws_eip" "ip" {
  instance = "${aws_instance.example.id}"

}
resource "aws_instance" "example" {
  ami           = "ami-b374d5a5"
  instance_type = "t2.micro"
  associate_public_ip_address = true
}

### Creating the Instance by running below command

terraform apply
