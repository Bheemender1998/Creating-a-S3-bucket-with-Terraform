# Creating an S3 Bucket with Terraform

This repository contains the code and instructions for creating an S3 bucket using Terraform on AWS. The goal of this project is to demonstrate how to provision AWS resources using Terraform, a powerful Infrastructure as Code (IaC) tool.

## Project Overview

In this project, we will:
1. Use Terraform to create an S3 bucket.
2. Customize the S3 bucket with various settings, such as tags.
3. Upload an object to the S3 bucket.

## Prerequisites

Before running the Terraform code, make sure you have the following installed:

- [Terraform](https://www.terraform.io/downloads.html)
- [AWS CLI](https://aws.amazon.com/cli/)
- AWS account with appropriate permissions

### AWS CLI Configuration

Make sure your AWS CLI is configured with access keys. You can configure it by running the following command:

```bash
aws configure
git clone https://github.com/Bheemender1998/Creating-a-S3-bucket-with-Terraform.git
cd Creating-a-S3-bucket-with-Terraform

To initialize: terraform init

Plan your infrastructure changes: terraform plan

Apply the configuration to create the S3 bucket: terraform apply


cleanup: terraform destroy

