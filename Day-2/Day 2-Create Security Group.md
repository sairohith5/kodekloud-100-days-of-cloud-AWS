The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the AWS cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition. To achieve this, they have segmented large tasks into smaller, more manageable units. This granular approach enables the team to execute the migration in gradual phases, ensuring smoother implementation and minimizing disruption to ongoing operations. By breaking down the migration into smaller tasks, the Nautilus DevOps team can systematically progress through each stage, allowing for better control, risk mitigation, and optimization of resources throughout the migration process.

For this task, create a security group under default VPC with the following requirements:

Name of the security group is nautilus-sg.

The description must be Security group for Nautilus App Servers

Add the inbound rule of type HTTP, with port range of 80. Enter the source CIDR range of 0.0.0.0/0.

Add another inbound rule of type SSH, with port range of 22. Enter the source CIDR range of 0.0.0.0/0.




Solution:
Sign in to AWS and go to EC2 Dashboard

In the left menu, click Security Groups

Click Create security group

Fill in the fields:

Security group name: nautilus-sg

Description: Security group for Nautilus App Servers

VPC: (select Default VPC)

Click Add rule twice and configure:

Rule 1 — HTTP

Type: HTTP

Port: 80

Source: 0.0.0.0/0

Rule 2 — SSH

Type: SSH

Port: 22

Source: 0.0.0.0/0

 Final Step

Click Create security group