Question

The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the AWS cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition. To achieve this, they have segmented large tasks into smaller, more manageable units. This granular approach enables the team to execute the migration in gradual phases, ensuring smoother implementation and minimizing disruption to ongoing operations. By breaking down the migration into smaller tasks, the Nautilus DevOps team can systematically progress through each stage, allowing for better control, risk mitigation, and optimization of resources throughout the migration process.

For this task, create a key pair with the following requirements:

Name of the key pair should be devops-kp

Key pair type must be rsa

Use the given AWS credentials (available via showcreds on the aws-client host).

Notes:

Create the resources only in us-east-1 region.


Solution
aws configure get region
This command shows the default AWS region configured for the CLI.

The task explicitly requires us-east-1.

If the region is wrong, resources will be created in the wrong place.



aws sts get-caller-identity
sts = Security Token Service

This command confirms:

Which AWS account you are connected to

Which user/role you are operating as

It ensures credentials are valid and active.


Command
aws ec2 create-key-pair --key-name devops-kp --key-type rsa --query 'KeyMaterial' --output text > devops-kp.pem

aws ec2 create-key-pair
Creates a new EC2 key pair.

--key-name devops-kp
Specifies the key pair name.

--key-type rsa
Defines the key type as RSA.

--query 'KeyMaterial'
Extracts only the private key from the output.

--output text
Prints the output as plain text.

> devops-kp.pem
Saves the private key into a file.
