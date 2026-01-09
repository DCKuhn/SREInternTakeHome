# SRE Internship Take-Home Project

This repository contains a Terraform configuration that provisions a simple web server on AWS using Infrastructure as Code.

The configuration creates an EC2 instance running Amazon Linux, attaches a security group that allows inbound HTTP traffic on port 80, and uses an EC2 user data script to automatically install and start the Nginx web server. After deployment, Terraform outputs the public IP address of the instance so the web server can be accessed in a browser.

---

## Requirements

To run this configuration, the following are required:

- Terraform installed and available in the system PATH
- An AWS account
- AWS credentials configured in the local environment (for example via `~/.aws/credentials`)
- Network access to AWS APIs

---

## Running the Configuration

The configuration is run from the CLI, in the project directory. Perform terraform init, terraform plan, terraform apply (responding yes where prompted).

After the apply step completes, Terraform outputs the public IP address of the EC2 instance. Visiting this IP address in a web browser (including http:\\ before the IP address) displays the default “Welcome to nginx!” page.

---

## Cleanup

After verification, all AWS resources can be removed by running terraform destroy, which ensures no infrastructure remains running after testing.

---

## Notes

AWS credentials are not included in this repository. Resources are created in the AWS account associated with the credentials used at runtime. The configuration can be safely destroyed and re-created multiple times.
