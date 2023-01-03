# Automation-of-Infrastructure-using-Jenkins-and-Terraform

![image](https://user-images.githubusercontent.com/52894481/194755034-59d8c277-350f-46e6-83d4-8ef7b3a4bcce.png)

# Introduction

This document is about how to execute Terraform scripts automatically using Jenkins pipeline.

I created an EC2 instance using Terraform and Jenkins in AWS cloud.

# Prerequisites:
- Jenkins 
- Terraform

# Terraform files
- main.tf
- variable.tf

# Steps: (AWS console)
1. Create an IAM role to provision EC2 instance in AWS.

![image](https://user-images.githubusercontent.com/52894481/194755438-3ae842db-1948-4b62-a8a2-db2ddd067036.png)

2. Choose AmazonEC2FullAccess as policy for that IAM role.
![image](https://user-images.githubusercontent.com/52894481/194755451-7ef18cfb-24ff-47b8-8cc8-9bb120dbb4dc.png)

# Steps: (Jenkins Server)
1. Create a new Jenkins Pipeline job with any job name.
![A](https://user-images.githubusercontent.com/52894481/194755471-2e5d4a5f-c41f-42a3-b024-eeae73d6edc6.JPG)

2. Add parameters to the pipeline

Click checkbox — This project is parameterized, choose Choice Parameter
Enter name as action

type apply and enter and type destroy as choices as it is shown below(it should be in two lines)
apply
destroy

![B](https://user-images.githubusercontent.com/52894481/194755493-1cf658a1-98eb-4e94-b15e-8f9bc6033f8c.JPG)

3. Go to Pipeline section

Add below pipeline code and modify as per GitHub repo configuration.

![C](https://user-images.githubusercontent.com/52894481/194755513-1f5a587a-e0a5-401c-b323-927355217b2b.JPG)

4.Click on Build with Parameters and choose apply to build the infrastructure or choose destroy if you like to destroy the infrastructure you have built.

![D](https://user-images.githubusercontent.com/52894481/194755525-03fe2294-4ee7-435f-b301-f1f4d00b3726.JPG)

5. Now you should see the console output if you choose to apply.

![E](https://user-images.githubusercontent.com/52894481/194755535-34d4067f-190e-4eff-8dc0-8dce7157971f.JPG)
