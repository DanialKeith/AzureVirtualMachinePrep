# Azure Virtual Machine Preparation

![6](https://github.com/DanialKeith/AzureVirtualMachinePrep/assets/154257195/dca1013f-4d93-4f2b-9e43-b67b1e015272)


## Introduction to Azure Honeynet Project
To initiate our Azure Honeynet project, the first task involves setting up virtual machines (VMs), which will serve as the core of our honeynet. Virtual machines operate as cloud-based computers and are vital for this project.

## Step-by-Step VM Setup in Microsoft Azure
### 1. Logging into Azure Portal
-	**Accessing Azure**: The initial step requires logging into your Azure account. If you don't have one, you'll need to create it.
### 2. Creating a Virtual Machine
-	**Navigating in Azure**: In the Azure portal, find the 'Virtual machines' section.
  
![1](https://github.com/DanialKeith/AzureVirtualMachinePrep/assets/154257195/62b8b472-6b5c-4fd2-b4b0-e3544506fb7d)


-	**VM Creation**: Click 'Create', then 'Virtual machine' to start setting up the new VM.
  
![2](https://github.com/DanialKeith/AzureVirtualMachinePrep/assets/154257195/8b99f9ec-6723-497c-8cb5-5ca340d96405)


### 3. Configuring VM Settings
-	**Selecting Subscription and Resource Group**: Choose an Azure subscription and a creat a resource group named RG-Cyber-Lab.
-	**Naming the VM**: Name the VM 'Lab-HoneyNet'.
-	**Choosing the Region**: Select 'East US 2' as the region.
-	**Availability Options**: No infrastructure redundancy required due to the honeypot role.
-	**VM Image**: Opt for Windows 10 Pro, version 21H2 - x64 Gen2.
  
![3](https://github.com/DanialKeith/AzureVirtualMachinePrep/assets/154257195/2b48441b-d0bf-43e5-9792-2e9ef40617b0)


-	**Setting Up Networking**: Use default settings for the virtual network, then make a Lab-VNet virtual network in this lab.
  
![4](https://github.com/DanialKeith/AzureVirtualMachinePrep/assets/154257195/7d73dc63-14ab-4567-9a9e-edd0c8ff9d1a)

  
### 4. NSG/Inbound Security Rule Configuration
-	**Accessing NSG**: In the Azure portal, locate 'Network Security Groups' and select the NSG linked to the VM.
-	**Creating Inbound Rule**: Go to 'Inbound security rules' and add a new rule.
-	**Rule Configuration**:
    -	Source: Set to Any to allow traffic from all locations. 
    -	Source Port Ranges: Allow all ports by setting to *.
    -	Destination: Set to Any to direct traffic to the VM.
    -	Destination Port Ranges: Open all ports by setting to *.
    -	Priority: Set to a low number like 110 to ensure the rule's effectiveness in the honeypot setup.
    -	Action: Set to Allow, permitting traffic matching this rule to the VM.
      
![5](https://github.com/DanialKeith/AzureVirtualMachinePrep/assets/154257195/63c22cc9-fa86-4dc2-b875-d984904cf290)


## Conclusion: The Honeypot Strategy
By creating our VMs with open inbound security rules, we leave the virtual 'front door' wide open. While not advisable in a real production setting due to high vulnerability risks, this approach is precisely what's needed for our honeynet. It enables us to lure potential attackers and monitor their actions in a safe, controlled environment. This setup is key to understanding and mitigating real-world cyber threats.

