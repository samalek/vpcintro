+++
title = "Create Transit Gateway"
chapter = false
weight = 70
+++

## Create Transit Gateway

We will use a Transit Gateway to route between the two VPCs. Lets create the Transit Gateway now.


![TGW Console](/images/tgw-list.png)
1. From the **Amazon VPC** console and from the left menu scroll down and select **Transit Gateways**. Click the **Create Transit Gateway** button.

    ![Create TGW](/images/tgw-create.png)
1. Configure the **Transit Gateway** with the following selections:
    - **Name tag**: give the Transit Gateway a name, such as **myTGW**.
    - **Description**: give the Transit Gateway a description, such as **First TGW**
    - **Amazon side ASN**: enter **65000** _best practice for TGWs that you want to peer: set a unique ASN between TGWs_
    - **DNS support**: checked
    - **VPN ECMP support**: checked
    - **Default route table association**: **UN**checked
    - **Default route table propagation**: **UN**checked
    - **Multicast support**: **UN**checked
    - **Auto accept shared attachments**: **check**
    - Click the **Create Transit Gateway** button.

    _Be sure to uncheck the Default route table association and propagation_

    ![TGW Created](/images/tgw-created.png)
1. Click the **Close** button once the TGW has been created.


### You have completed the Create TGW.