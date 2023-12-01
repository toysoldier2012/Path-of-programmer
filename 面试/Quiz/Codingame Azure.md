
# QCM

### Azure App Service - Accidental deletion
Cloud Fundamentals (40 pts)

You have the following web application hosted with Azure App Service:

- App service name: `MyApp1`
- App service plan: `MyPlan1`
- Resource group: `RG1`

You accidentally deleted `RG1`, which also deleted the app service. You have another resource group `RG2` with an app service plan `MyPlan2`.

How can you restore the app service `MyApp1` under the `RG2` resource group and the `MyPlan2` app service plan?

- Raise a support ticket in the Azure Portal within 30 days of deletion
- Use the following PowerShell command:  
    
    ```powershell
    Restore-AzDeletedWebApp -TargetResourceGroupName RG2 -Name MyApp1 -TargetAppServicePlanName MyPlan2​​
    ```
    
- 
1. Restore `RG1` by raising a support ticket.  
2. Restore `MyApp1` under `RG1` using the following command:  
    
    ```powershell
    Restore-AzDeletedWebApp -TargetResourceGroupName RG1 -Name MyApp1 -TargetAppServicePlanName MyPlan1​
    ```
    
      
3. Move `MyApp1` to `RG2` using PowerShell
- It cannot be recovered

### Azure Data Factory concepts
Data Analytics and AI (20 pts)

To perform ETL operations using Azure Data Factory, which of the following objects do you necessarily have to create?

_Select all correct answers._

- Dataset
- Pipeline
- Linked service
- Cluster

### Azure Storage knowledge
Cloud Storage/Database (40 pts)

Which of the following statements are true about Azure Storage?

_Select all correct answers._

- You can only provide access to a single folder within a blob container
- You can generate a public link of the blob container which is valid for 5 days
- You can host a website in Azure Storage
- You cannot create access policies for a blob container

### Azure VM migration
Cloud Fundamentals (20 pts)

You have a B-series virtual machine with a B2MS size and you notice a high utilization of the VM CPU.

You are planning to change the VM from a B2MS to a D4a v4. During this change, what can be said about the **service hosted on the VM**?

- The service will be temporarily unreachable
- The service will need to be migrated manually with extra development after the transition
- The service will remain reachable during the transition

### Azure Machine Learning - R & Python
Data Analytics and AI (20 pts)

Which programming languages can you use to build models in Azure Machine Learning?

_Select all correct answers._

- .NET
- R
- Python
- Ruby

### DNS record for Azure Web App
Cloud Fundamentals (20 pts)

What type of **DNS record** should you use to map a custom domain name to an Azure Web App? 

- MX
- SRV
- A
- PTR

### Network security group
Cloud Networking & Security (20 pts)

Which feature should you use to control the traffic coming to or from the resources within your Azure VNet? 

- Azure Firewall
- Azure Network Security Group
- Azure Access Control List

### Azure Active Directory - Multi-Tenant Application
Cloud Networking & Security (20 pts)

You have a website hosted with Azure App Service, and you want to implement an **Azure Active Directory authentication**.

This website should be accessible by your company employees and some external vendors.

Which app registration configuration should you choose? 

- Single-Tenant (accounts in this directory only)
- Multi-Tenant (accounts in any Azure AD directory)
- Single-Tenant (accounts in this directory) and B2B collaboration guest users
- Personal Microsoft accounts only

### Azure Load Balancer
Cloud Fundamentals (40 pts)

You are planning to use 4 virtual machines for your web application.

What Azure resource would you use to make sure that the **incoming traffic will be distributed** to all virtual machines?

- Load Balancer
- Virtual Network
- Traffic Manager
- ExpressRoute

### Cost management
DevOps (40 pts)

You deployed 100 Azure VMs. Your organization has defined two cost centers that use those VMs. 

How would you assign each VM to the correct cost center? 

- By editing the VMs' properties
- By moving each VM to a cost center with your ARM
- By assigning tags to VMs
- Through the Azure Cost Management system where it is done automatically

### Traffic between virtual networks
Cloud Fundamentals (40 pts)

You want to allow traffic between two different virtual networks.

What should you do?

- Configure a virtual network peering
- Create a firewall rule to allow traffic between the two virtual networks
- Use Azure Application Gateway

### Storage options - GZRS
Cloud Fundamentals (20 pts)

You have some sensitive and valuable data that you want to protect from hardware failures and natural disasters. 

Which Azure storage option would you choose if your goal is to minimize the risk of data loss? 

- Locally redundant storage (LRS)
- Zone-redundant storage (ZRS)
- Geo-zone-redundant storage (GZRS)

### Azure SQL - Firewall and authorized IP addresses
Cloud Networking & Security (20 pts)

While connecting to an Azure SQL database, you receive the following error message:

![Azure PowerTip 4: Unable to Connect to Azure Sql Database. IP Address is  not allowed to access server. | manuelmeyer.net](https://static.codingame.com/work/servlet/fileservlet?id=37847098774993)

How will you fix this issue?

- Add your IP address to Azure SQL Server Firewall
- Check your SQL username and password
- Check the SQL server name
- Add the `public` tag to your Azure SQL database
