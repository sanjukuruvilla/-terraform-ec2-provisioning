# Provisioning an EC2 Instance using Terraform

This repository provides Terraform scripts for provisioning an EC2 instance on AWS.

## Overview

The Terraform scripts in this repository enable the provisioning of an EC2 instance on Amazon Web Services (AWS). The scripts are designed to create a basic EC2 instance with specified configurations.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Terraform Scripts](#terraform-scripts)
   - [Providers.tf](#providerstf)
   - [Ec2_main.tf](#ec2_maintf)
3. [Usage](#usage)
5. [Contributing](#contributing)
6. [License](#license)

## Prerequisites

Before using these Terraform scripts, ensure you have the following:

- AWS account with appropriate permissions. ([Refer to the Installation Guide Repository](https://github.com/sanjukuruvilla/aws-cli-setup.git))
- Terraform installed on your local machine. ([Refer to the Installation Guide Repository](https://github.com/sanjukuruvilla/terraform-installation-guide.git))

## Terraform Scripts

### Providers.tf

The `providers.tf` file specifies the AWS provider configuration:

```hcl
provider "aws" {
  region = "us-east-1"
}
```

### Ec2_main.tf

The `ec2_main.tf` file defines the EC2 instance resource:

```hcl
resource "aws_instance" "bastion" {
  ami           = "" // Add your AMI ID
  instance_type = "t2.micro"

  tags = {
    name = "Bastion"
  }
}
```

## Usage

To use these Terraform scripts:

1. Ensure you have AWS credentials configured on your local machine.
2. Update the `ami` parameter in the `ec2_main.tf` file with your desired AMI ID.
3. Run `terraform init` to initialize the Terraform configuration.
4. Run `terraform plan` to review the execution plan.
5. Run `terraform apply` to provision the EC2 instance on AWS.

## Contributing

Contributions to this repository are welcome! If you find issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
