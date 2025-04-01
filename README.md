<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Create S3 Buckets with Terraform

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-terraform1)

**Author:** Bheemender Gurram  
**Email:** bheemender123@gmail.com

---

![Image](http://learn.nextwork.org/content_black_noble_hippopotamus/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Introducing Today's Project!

In this project, I will demonstrate how to create an s3 bucket with Terraform. The goal is to learn through the steps and make sure to grasp the concepts behind the flow

### Tools and concepts

Services I used were AWS S3 for creating and managing the storage bucket. Key concepts I learnt include Infrastructure as Code (IaC), which allows the management and provisioning of infrastructure using code, enabling automation and reproducibility. Additionally, I gained hands-on experience with Terraform as a tool for IaC, using it to define, plan, and apply configurations for creating cloud resources.

Other important concepts include:
	•	Terraform Providers: Which allow Terraform to interact with different cloud services like AWS.
	•	Terraform State: The state file that tracks resources created and managed by Terraform.
	•	Version Control: Using Git to manage and share infrastructure configurations.
	•	AWS CLI: A tool for interacting with AWS services from the command line, useful for setting up credentials and managing AWS resources.

This project helped solidify my understanding of cloud automation, resource provisioning, and version-controlled infrastructure management.

### Project reflection

This project took me approximately 1 hour to complete. The most challenging part was configuring the AWS CLI and managing access keys correctly to allow Terraform to interact with my AWS account. It was most rewarding to see the S3 bucket created and successfully upload an object to it using Terraform, as it demonstrated the power of Infrastructure as Code in automating cloud resource provisioning.

I decided to work on this project today because I wanted to deepen my understanding of Terraform and its role in automating infrastructure deployment, particularly in cloud environments like AWS. As I work towards mastering cloud technologies, this project was a perfect way to apply those skills in a hands-on, practical way.

---

## Introducing Terraform

Terraform is an open-source Infrastructure as Code (IaC) tool that allows you to define, provision, and manage cloud resources in a declarative manner. It enables automation of infrastructure deployment across multiple cloud providers like AWS, Azure, and Google Cloud, ensuring consistency, scalability, and repeatability.

Terraform is one of the most popular tools used for Infrastructure as Code (IaC), which is the practice of managing and provisioning computing infrastructure through machine-readable configuration files instead of manual processes. IaC allows developers and operations teams to automate infrastructure deployment, ensuring consistency, scalability, and faster application delivery across cloud environments.

Terraform uses configuration files to define the desired state of infrastructure resources in a declarative way. main.tf is the primary Terraform configuration file where you specify the cloud provider, resource definitions (such as S3 buckets, EC2 instances, and IAM roles), and other infrastructure settings. It serves as the main entry point for Terraform to read and apply configurations.

![Image](http://learn.nextwork.org/content_black_noble_hippopotamus/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Configuration files

The configuration is structured in declarative blocks that define resources, providers, variables, and outputs. These blocks are organized in files like main.tf, variables.tf, and outputs.tf to manage different aspects of infrastructure. Resources are defined with specific attributes, and Terraform automatically handles dependencies and execution order.

The advantage of doing this is clarity and maintainability, as each block serves a specific purpose, making it easier to manage large-scale infrastructure changes, track updates, and ensure consistency across environments. Additionally, this approach enables collaboration, as team members can easily understand and modify configurations without worrying about the underlying infrastructure details.

### My main.tf configuration has three blocks

The first block indicates the provider configuration, specifying the cloud provider (in this case, AWS) and the region where the resources will be provisioned. It tells Terraform which API to communicate with to create and manage resources.

The second block provisions the S3 bucket resource, defining the name and other properties of the S3 bucket that will be created in AWS. This block tells Terraform what the desired state of the bucket should look like.

The third block manages the versioning configuration for the S3 bucket, enabling versioning to ensure that every change to the objects in the bucket is tracked and can be reverted if necessary. It ensures the bucket is configured to retain different versions of the stored objects.

![Image](http://learn.nextwork.org/content_black_noble_hippopotamus/uploads/aws-devops-terraform1_ljvh9876)

---

## Customizing my S3 Bucket

For my project extension, I visited the official Terraform documentation to find detailed information about resource definitions, best practices, and examples for configuring AWS services, such as S3. The documentation shows how to properly structure Terraform code, how to configure providers, and how to manage resources like S3 buckets, IAM roles, and other cloud services. It also provides useful tips on handling state, working with modules, and managing dependencies between resources.

I chose to customize my bucket by adding tags to label my resources because tags help in organizing and managing AWS resources efficiently, making it easier to identify buckets based on their purpose or environment.

When I launch my bucket, I can verify my customization by navigating to the AWS S3 console, selecting my bucket, and checking the “Tags” section under the bucket properties to ensure the assigned tags are correctly applied.

![Image](http://learn.nextwork.org/content_black_noble_hippopotamus/uploads/aws-devops-terraform1_ffe757cd3)

---

## Terraform commands

I ran terraform init to initialize my Terraform project by setting up the working directory, downloading the required provider plugins, and preparing the backend for state management. This command ensures that Terraform has all the necessary dependencies to execute infrastructure changes and allows me to start defining and managing AWS resources.

Next, I ran terraform plan to preview the changes Terraform will make to my AWS environment based on the configuration in main.tf. This command helps me verify that my configuration is correct by showing a detailed list of resources that will be created, modified, or destroyed before I apply the changes.

![Image](http://learn.nextwork.org/content_black_noble_hippopotamus/uploads/aws-devops-terraform1_3g4h5i6j)

---

## AWS CLI and Access Keys

To resolve my error, first, I installed AWS CLI, which is a command-line tool that allows me to manage AWS services directly from my terminal instead of using the AWS Management Console. It enables me to automate tasks, configure resources, and interact with AWS services programmatically. By setting up the AWS CLI, I can authenticate Terraform to deploy and manage my infrastructure seamlessly.

I set up AWS access keys to allow Terraform to authenticate and interact with my AWS account programmatically. These keys enable Terraform to create, modify, and manage cloud resources without requiring manual login to the AWS Management Console. By configuring the access keys in the AWS CLI, I ensure a secure and automated way to deploy infrastructure from my local machine.

---

## Lanching the S3 Bucket

I ran terraform apply to execute the planned infrastructure changes and create my S3 bucket in AWS as defined in my Terraform configuration.

Running terraform apply will affect my AWS account by provisioning the specified resources, applying configurations such as tags and versioning, and making the necessary API calls to AWS to set up the infrastructure automatically. This step ensures that my cloud environment matches the desired state defined in my Terraform files.

The sequence of running terraform init, terraform plan, and terraform apply is crucial because each command serves a specific role in setting up and managing infrastructure in a structured and error-free manner.
	1.	terraform init – This is the first command that initializes the Terraform working directory. It downloads necessary provider plugins and sets up the backend for storing the Terraform state.
	2.	terraform plan – This command creates an execution plan by analyzing the configuration and showing what changes will be made to the AWS environment without actually applying them. It helps prevent unintended modifications.
	3.	terraform apply – After reviewing the plan, this command executes the proposed changes, creating or modifying resources in AWS to match the defined infrastructure.

Following this sequence ensures that Terraform is properly set up, potential errors are identified before deployment, and infrastructure changes are applied systematically.

![Image](http://learn.nextwork.org/content_black_noble_hippopotamus/uploads/aws-devops-terraform1_1q2w3e4r)

---

## Uploading an S3 Object

I created a new resource block to define and manage the upload of an object to my S3 bucket. This allows me to automate the process of adding data to the bucket directly through Terraform, ensuring that the object is uploaded with the necessary settings, such as permissions or metadata, and remains consistent with my infrastructure as code setup.

We need to run terraform apply again because we’ve made changes to the Terraform configuration, such as adding a new resource to upload an object to the S3 bucket. Running terraform apply ensures that the updated configuration is applied, provisioning the new resource and ensuring that the infrastructure matches the desired state as defined in the code.

To validate that I’ve updated my configuration successfully, I logged into the AWS Management Console, navigated to the S3 service, and selected the bucket to check if the object (image.png) was uploaded. I also confirmed that the object had the correct key and was located at the correct path within the bucket. Additionally, I verified the settings for public access block and ensured that the object was uploaded with the appropriate access permissions.

![Image](http://learn.nextwork.org/content_black_noble_hippopotamus/uploads/aws-devops-terraform1_9o0p1a2s)

---

---
