---
title: "Creating the base AWS Environment"
chapter: false
weight: 31
pre: "<b>4.1 </b>"
---

---

## 1. Creating the base AWS environment using AWS CloudFormation Template

You can use the CloudFormation template launch button below to create the infrastructure in same AZ with the 2 subnets, NAT Gateway, Internet Gateway, and the EC2 instances.

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=Network-Security-Workshop&templateURL=https://aws-workshop-c1as-cft-templates.s3.amazonaws.com/CFT_Network_Security_Workshop.yml)

---

### 2. Uploading the CloudFormation Template

- Click on **Next**

![C1NS1](/images/create_env_3.png) 

---

### 3. Specifying additional stack parameters

{{% notice info %}}
<p style='text-align: left;'>
A Key Pair is required before continuing this CloudFormation deployment. If you need help creating a Key Pair -> <a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#having-ec2-create-your-key-pair" target="_top">Create a key pair</a>
</p>
{{% /notice %}}


<details>
  <summary> -> <code>CLICK HERE</code> to see how to create key pair</summary>

**AWS Console -> EC2 -> Key Pairs -> Create key pair**

![C1NS1](/images/create_env_9.png) 

</details>
<br>

- **Stack Name:**  <code>Network-Security-Workshop</code>

- **InspectionVPCCIDR:** the CIDR that you want to use for the VPC. You don't need to change it, if you don't want to change the default configuration.
    
- **KeyPair:** Your KeyPair name

- **MyPublicIP:** Your public IP in CIDR. (e.g. 191.162.228.91/32 . You can grab it using a few tools or websites (https://ipinfo.io/ip). It will be use to only allow your IP to access the vulnerable application (DVWA))

- **ProtectedPrivateSubnetAZ:** the AZ what you want to use to your Private subnet.

- **ProtectedPrivateSubnetCIDR:** the CIDR that you want to use for the Private. You don't need to change it, if you don't want.

- **ProtectedPublicSubnetAZ:** the AZ what you want to use to your Public subnet.

- **ProtectedPublicSubnetCIDR:** the AZ what you want to use to your Public subnet. You don't need to change it, if you don't want to.

---

### 3.1. Stack details example:

![C1NS1](/images/create_env_4.png) 

---

### 4. Configure stack options

Leave as fields as default and click **Next**, or optionally define tags to the environment if desired.

![C1NS1](/images/create_env_5.png) 

---

### 5. Review the template parameters 
- Mark the checkbox the **"I acknowledge... "**
- Click on **Create Stack**

![C1NS1](/images/create_env_6.png) 

![C1NS1](/images/create_env_7.png) 

![C1NS1](/images/create_env_8.png) 

---

### 6. Follow up the events during creation of the stack.
- Select the **Events** tab
- Click **Refresh**

![C1NS1](/images/create_env_10.png) 

---

### 7. Ensure the stack status has reached **Create_Complete**. 
- Select the **Stack info** tab

![C1NS1](/images/create_env_11.png) 

---

> **Now it's time for us to integrate Cloud One Network Security with AWS :cloud: :laptop: :rocket:**
