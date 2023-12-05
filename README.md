# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Set up resources in Azure
- Ensure Connectivity between the client and Domain Controller
- Install Active Directory
- Create an Admin and Normal User Account in AD
- Join Client-1 to your domain
- Setup Remote Desktop for non-administrative users on Client-1
- Create a bunch of additional users and attempt to log into client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>


<p>
  
  ![image](https://github.com/DabneyV/configure-ad/assets/148362429/9ffc3c55-e7ee-4729-874d-59cc4ac6a767)
<p>


![image](https://github.com/DabneyV/configure-ad/assets/148362429/2a9fa049-40c3-40ad-8faf-8f3657a30e87)

![image](https://github.com/DabneyV/configure-ad/assets/148362429/78aca36f-6a92-420a-94cd-569d92dc2ade)


![image](https://github.com/DabneyV/configure-ad/assets/148362429/e977dc29-9d19-4e0e-9d30-4dac08a175cb)



</p>
<p>
I created the Domain Controller VM (Windows Server 2022) named “DC-1”
Then set Domain Controller’s NIC Private IP address to be static
Then create the Client VM (Windows 10) named “Client-1”. Use the same Resource Group and Vnet that was created in Step 1.a
Then ensure that both VMs are in the same Vnet 

</p>
<br />

<p>
  
![image](https://github.com/DabneyV/configure-ad/assets/148362429/cadfb7bd-8f3e-4497-a721-f6e39d094bce)

![image](https://github.com/DabneyV/configure-ad/assets/148362429/06e20bfa-ef5c-425c-8c1c-fc9bfa78a6f4)

![image](https://github.com/DabneyV/configure-ad/assets/148362429/eab1d0f7-83a9-4de8-b8e1-5c757f3be85f)


</p>
<p>
Login to DC-1 and install Active Directory Domain Services
Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)
Restart and then log back into DC-1 as user: mydomain.com\labuser
</p>
<br />

<p>

![image](https://github.com/DabneyV/configure-ad/assets/148362429/99bcc706-8927-4cfd-9a50-23edca6fdc66)

 ![image](https://github.com/DabneyV/configure-ad/assets/148362429/c6b268af-c58f-41b8-bd6c-7a81b0501fec)

![image](https://github.com/DabneyV/configure-ad/assets/148362429/f8b5e1a8-6408-4fcf-b440-0f805c219972)

 ![image](https://github.com/DabneyV/configure-ad/assets/148362429/ddfc996c-54f5-4473-bf3e-a458af385407)

![image](https://github.com/DabneyV/configure-ad/assets/148362429/f113ccbd-3664-413b-a0e6-8f5a9366685c)

![image](https://github.com/DabneyV/configure-ad/assets/148362429/c6047076-2a1d-4b3e-b932-6aeb8e268f8a)

![image](https://github.com/DabneyV/configure-ad/assets/148362429/a974389a-8b33-4cbd-bafb-619d875578e2)

![image](https://github.com/DabneyV/configure-ad/assets/148362429/8685cf87-57c4-4462-90a3-bab099d13db5)

</p>
<p>
From the Azure Portal, set Client-1’s DNS settings to the DC’s Private IP address
From the Azure Portal, restart Client-1
Login to Client-1 (Remote Desktop) as the original local admin (labuser) and join it to the domain (computer will restart)
Login to the Domain Controller (Remote Desktop) and verify Client-1 shows up in Active Directory Users and Computers (ADUC) inside the “Computers” container on the root of the domain
Create a new OU named “_CLIENTS” and drag Client-1 into there (Step is not really necessary, just for organizational purposes. 
</p>
<br />
