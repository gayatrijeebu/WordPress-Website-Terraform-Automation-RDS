# WordPress-Website-Terraform-Automation

This project demonstrates the use of Terraform to create a robust and scalable infrastructure on AWS. The goal is to host 10 WordPress websites securely using various AWS services.

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/1c1c013b-1eae-45cb-835e-02e65679df73)

Tasks I performed :

1 .Write a Infrastructure as code using terraform, which automatically create a VPC.

In that VPC we have to create 3 subnets:

a) 2 Public subnets [Accessible for Public World!]

b) Private subnet [Restricted for Public World!]

2. Create a public facing internet gateway for connect our VPC/Network to the internet world and attach this gateway to our VPC.

3. Create a routing table for Internet gateway so that instance can connect to outside world, update and associate it with public subnet.

4. Launch an ec2 instance which has Wordpress setup already having the security group allowing port 80 so that our client can connect to our wordpress site.

5. Launch an ec2 instance which has MYSQL setup already with security group allowing port 3306 in private subnet so that our wordpress vm can connect with the same.

6. Below are the steps how I executed my code:

Step1: Configured AWS with the cmd – aws configure

AWS configuration:

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/0a1ca78e-77db-4cc2-b9a6-d6138ba845c4)

Step2: Provider Info

Step3 – create a key-pair if don’t have one.

Step4 – Created VPC, 2public subnets and 1 private subnet.

Step5 – created Internet gateway, Route Table and associated Public subnet with it.

Step6- created security groups for WordPress and RDS Instance

Step7- Created Ec2 instance for WordPress and RDS instance to host our website.

•	After creating all these I initialised Terraform with  - terraform init

•	It installs all the necessary plugins for the code.

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/298a1c06-aac1-4349-8e0e-c009a5fb4193)

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/9420ad3b-1684-441b-84da-23c1b84309cb)

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/1f977af7-92b0-4f6c-8349-66d4afd7cf31)

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/ef3fd96e-f07c-48d6-b1b9-a384fe85313c)

•	Once initialised and applied, we can even verify from your AWS console.

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/34c1178b-864d-4500-886c-7fa8afaf8c18)

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/17cf1cd4-61f4-4661-a6ba-8ce6a34fd061)

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/b38f0837-ceb4-4f7e-98f7-7ea14b2a66d7)

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/2ca63186-5709-42dc-a4d6-70567681aa34)

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/af7ea792-519f-4245-8352-c31c79db02b7)

•	After connecting with the Public IP of WEB instance in EC2 it shows like,
 
![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/ea6d2a58-c4fb-43f1-a60a-396c7a29c83e)

![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/a5818113-8d4c-4be9-b127-c31d87a91408)

 Let’s fill in the database details as mentioned under RDS instance in instance.tf file.
 
Here for the next part, I was not able to configure and install the WordPress. But I have an idea how it goes on after configuration and installation. Where we successfully login into the website Dashboard and publish. 

After this,

•	For removing all the setup I used terraform destroy.

•	Then it prompts us to say yes, enter yes to delete your whole setup in one go.

  ![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/a9f1707a-3e1c-4e15-9b9f-be1a8c885a64)

  ![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/bd707dbf-ed22-4150-9947-c0438685de8a)

•	One of major advantage of AWS RDS is it provides visual metrics for our database and is flexible which is very handy to use.
 
![image](https://github.com/gayatrijeebu/WordPress-Website-Terraform-Automation/assets/97388879/b364d7f3-2c52-4e69-8309-c898df5c6104)

-------------------------------------------------------------------------------------------------------------------------------






















