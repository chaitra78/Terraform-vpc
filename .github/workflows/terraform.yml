provider "aws" {
   region = "ap-south-1"
}

resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}

resource "aws_subnet" "main" {
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.1.0/24"
  availability_zone       = "ap-south-1a"
  map_public_ip_on_launch = true
}

resource "aws_instance" "example" {
  ami           = "ami-0cca134ec43cf708f"
  instance_type = "t2.micro"
  subnet_id     = aws_subnet.main.id
}
