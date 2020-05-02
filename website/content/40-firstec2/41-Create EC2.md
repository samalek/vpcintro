+++
title = "Create EC2 Instance"
chapter = false
weight = 41
+++

## Create EC2 Instance
We will now launch an Linux EC2 Instance into a private subnet. We will attach the IAM role we created so we can access the bash shell using AWS Systems Manager.


1. From the **Amazon EC2** console and from the left menu select **Instances**.

    ![Launch Instance](/images/ec2-launchinstance.png)

1. Click the **Launch instance** button.

    ![Select AMI](/images/ec2-selectami.png)
1. Click the **Select** button to the right of the first AMI in the list, **Amazon Linux 2 AMI**.

    ![Configure details](/images/ec2-details.png)
1. Let's configure the instance to launch in the Private A subnet in your VPC with the IAM role you created using the following settings:
    - **Network**: Select **your_VPC** from the dropdown list.
    - **Subnet**: Select **PrivateA** subnet from the dropdown list.
    - **IAM Role**: Select **your_role** you just created from the dropdown list.
    - Click **Next: Add Storage** button in the bottom right.

    ![Configure storage](/images/ec2-storage.png)
1. Leave Storage at its defaults. Click **Next: Add Tags** button.
 
    ![Configure tags](/images/ec2-tags.png)
1. Let's name the instance using the following settings:
    - Click **new tag** button
    - **Key**: Type **Name** _use upper case 'N', as its case sensitive_
    - **Vaule**: Name your instance something like **myEC2**
    - Click **Next: Configure Security Group** button in the bottom right.

    ![Configure tags](/images/ec2-securitygroup.png)
1. Since we are using Systems Manager to access the server, we do not need TCP port 22 opened on the  Inbound Security Group.
Click the **X** to the right of the SSH rule to delete it.
_Instead Systems Manager uses an agent on the Operating System to initiate the connection to the Systems Manager services. Security is controlled by Systems Manager and IAM._ Click **Review and Launch** button.

    ![Review EC2](/images/ec2-review.png)
1. Review the setting and make sure you are launching in a private subnet. Click the **Launch** button.

    ![Launch without keypair](/images/ec2-keypair.png)
1. We dont need a keypair, since we wont use SSH. Change the **Key Pair** option to **Proceed without a key pair** from the dropdown list.
Check the **_“I acknowledge that I will not be able to connect to this instance unless I already know the password built into this AMI”_**. Click the **Launch Instance** button.


### You have completed the EC2 Launch. ###