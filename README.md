https://www.linkedin.com/posts/aditya-chikte-2176a21b5_aws-ec2-cloudcomputing-activity-7206197048923086849-NVnS?utm_source=share&utm_medium=member_desktop

# EC2 Linux Instance Creation Guide

This repository provides a detailed step-by-step guide to creating an Amazon EC2 Linux instance using the AWS Free Tier.

## Prerequisites
- AWS Free Tier account
- Basic understanding of cloud computing and AWS services
- MobaXterm installed on your local machine

## Step-by-Step Instructions

### Step 1: Sign In to AWS Management Console

1. Open the [AWS Management Console](https://aws.amazon.com/console/).
2. Sign in with your AWS account credentials. If you don't have an account, create one.

### Step 2: Navigate to EC2 Dashboard

1. In the AWS Management Console, navigate to the **EC2 Dashboard**.
    - You can find EC2 under "Compute" services, or search for **EC2** in the search bar.

### Step 3: Launch an Instance

1. Click the **Launch Instance** button on the EC2 Dashboard.
2. You will be directed to the **Choose an Amazon Machine Image (AMI)** page.

### Step 4: Choose an Amazon Machine Image (AMI)

1. In the AMI selection screen, select **Amazon Linux 2 AMI** (or any other Linux distribution that is free tier eligible).
2. Ensure the selected AMI is marked as **Free tier eligible**.

### Step 5: Choose an Instance Type

1. Select the **t2.micro** instance type, which is free tier eligible.
2. Click **Next: Configure Instance Details**.

### Step 6: Configure Instance Details

1. On the **Configure Instance Details** page, leave the default settings.
2. Ensure that **Auto-assign Public IP** is enabled.
3. Click **Next: Add Storage**.

### Step 7: Add Storage

1. The default storage configuration (8 GB General Purpose SSD (gp2)) is typically sufficient and free tier eligible.
2. Adjust the storage size if necessary, staying within the free tier limits.
3. Click **Next: Add Tags**.

### Step 8: Add Tags

1. Tags are optional but can help organize your instances. You can add a **Name** tag.
    - Click **Add Tag**, then enter `Key: Name` and `Value: MyLinuxInstance` (or any preferred name).
2. Click **Next: Configure Security Group**.

### Step 9: Configure Security Group

1. Create a new security group or select an existing one.
    - For a new security group, provide a name and description.
2. Add a rule to allow SSH access:
    - Add an SSH rule to allow access from your IP address.
    - In the **Source** field, select **My IP** to limit SSH access to your specific IP address.
3. Click **Review and Launch**.

### Step 10: Review Instance Launch

1. Review all the settings you’ve configured.
2. Click **Launch** to proceed.

### Step 11: Key Pair for Authentication

1. A dialog will prompt you to select an existing key pair or create a new one.
    - Choose **Create a new key pair**.
    - Provide a name for the key pair (e.g., `MyLinuxKeyPair`).
    - Download the key pair file (.pem) and store it securely.
2. Click **Launch Instances**.

### Step 12: Access Your Instance

1. Once the instance is launched, go to the **Instances** page in the EC2 Dashboard.
2. Select your instance, and click **Connect**.
3. Follow the instructions provided to connect to your Linux instance via SSH or MobaXterm.

### Step 13: Connect to the Linux Instance Using MobaXterm

#### Install MobaXterm:
- Download and install MobaXterm from the [official website](https://mobaxterm.mobatek.net/download.html).

#### Steps to Connect:

1. Open **MobaXterm** on your local machine.
2. Click on the **Session** icon in the top-left corner.
3. Select **SSH** as the session type.
4. In the **Remote Host** field, enter the **Public IP** address of your EC2 instance.
5. Ensure the **Port** is set to `22` (default for SSH).
6. In the **Username** field, enter `ec2-user` (for Amazon Linux).
7. Select **Use private key** and browse to the location where your `.pem` key file is stored (the key pair you downloaded during the instance launch process).
8. Click **OK** to initiate the connection.
9. MobaXterm will establish the SSH connection, and you will be logged into your EC2 instance's terminal.

### Step 14: Terminate the Instance

1. When you no longer need the instance, terminate it to avoid charges.
2. Go to the **Instances** page in the EC2 Dashboard.
3. Select the instance you want to terminate.
4. Click the **Actions** button, select **Instance State**, and then choose **Terminate**.
5. Confirm the termination when prompted.

---

## Additional Resources
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)
- [AWS Free Tier](https://aws.amazon.com/free/)
- [MobaXterm Documentation](https://mobaxterm.mobatek.net/documentation.html)
