# ActiveDirectory-HomeLab

## Objective:
Configuring a Windows Server 2022 virtual machine as a fully functional Active Directory Domain Controller in a virtualized lab environment using VMware Workstation Pro.

## Environment:
- Hypervisor: VMware Workstation Pro
- Server OS: Windows Server 2022 Standard Evaluation
- Domain: corp.local
- Server Name: DC01
- IP Address: 192.168.10.1

## Skills Demonstrated:
- Static IP configuration
- Windows Server administration
- Active Directory Domain Services (AD DS) installation
- Domain Controller promotion
- DNS configuration

## Step 1 - Dashboard & Setting Static IP
<img width="1226" height="878" alt="image" src="https://github.com/user-attachments/assets/d1c103e6-1332-4aa0-8aaa-cfb6a6cd133c" />
<br>
After installing Windows Server 2022 ISO's file and launching from VirtualBox, the System Dashboard immediately pops up after log in. During initial setup, go to the network icon in the bottom right, right-click, and navigate to "Open Network & Internet Settings". Click "Change adapter options", right-click Ethernet then properties, and open "Internet PRotocol Version 4 (TCP/IPv4)". After this, configure the static IP address as shown.

<br>
<br>

<img width="1224" height="879" alt="image" src="https://github.com/user-attachments/assets/af12ea74-a838-4468-8841-00c9f35ef8dd" />

<br>
<br>

We will rename this PC to DC01 (Domain Controller 1).

<br>

<img width="1224" height="875" alt="image" src="https://github.com/user-attachments/assets/316dd523-26c3-4f76-9c99-d316239bc137" />

## Step 2 - Installing the Active Directory Domain Services (AD DS) Role
After restarting, select the #2 option on Server Manager to "Add roles and features" and clicking next will reveal our renamed PC/server DC01.

<img width="1221" height="879" alt="image" src="https://github.com/user-attachments/assets/c65b8a3a-e8ae-467b-a2ca-9cd17578bd2f" />

<br>
<br>

Click next, check "Active Directory Domain Services" in the listed installations and install.

<br>

<img width="1224" height="877" alt="image" src="https://github.com/user-attachments/assets/fb558e69-a77f-4365-8702-f907df5444de" />

## Step 3 - Promote the Server to a Domain Controller
After installing AD DS, a yellow flag icon appears in the top bar of Server Manager.

<img width="1220" height="327" alt="Screenshot 2026-05-19 204932" src="https://github.com/user-attachments/assets/c87f781c-41da-41ad-acac-d88cc24c2217" />

<br>
<br>

After clicking the icon and clicking "Promote this server to a domain controller", select "Add a new forest" and in the Root domain field type: corp.local

<img width="1224" height="877" alt="image" src="https://github.com/user-attachments/assets/6cdee4bd-2e90-4af1-a2e6-58aab31359fd" />

<br>
<br>

Leave settings at default, ensure DNS server is checked, and create a DSRM password (I used the same password as the Administrator login). After setting the password, click through the next prompts by leaving everything at default, including DNS options, Additional Options, and Paths. After reviewing options, the prerequisites are checked and we can install.

<br>

<img width="1227" height="877" alt="image" src="https://github.com/user-attachments/assets/99192318-0d8e-4fd0-8428-e4e2ee4632d0" />

## Step 4 - Take a VMware Snapshot
Following the install and server restart, verify the Domain Controller is working in observing the login showing CORP\Administrator.

<img width="1224" height="879" alt="image" src="https://github.com/user-attachments/assets/09c2f46f-1f86-437e-b3e5-449b6a285cb4" />

<br>
<br>

Observe AD and DNS listed in the left panel of Server Manager. Click to ensure it's working, then take a VMware snapshot to save progress as a 'checkpoint' to then work on other labs.

<br>

<img width="1221" height="877" alt="Screenshot 2026-05-19 210059" src="https://github.com/user-attachments/assets/3b0d190b-aa04-43c5-a147-40e80aa5a924" />
