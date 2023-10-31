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

- Step 1
- Step 2
- Step 3
- Step 4

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


</p>
<p>
Login to DC-1 and install Active Directory Domain Services
Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)
Restart and then log back into DC-1 as user: mydomain.com\labuser
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
