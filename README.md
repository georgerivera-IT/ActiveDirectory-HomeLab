# Active Directory Home Lab - Configuring a Windows VM for Active Directory

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
After installing Windows Server 2022 ISO's file and launching the VM, I configured a static IP address of 192.168.10.1 through the IPv4 network adapter settings to ensure consistent DNS resolution across the domain.

<br>
<br>

<img width="1224" height="879" alt="image" src="https://github.com/user-attachments/assets/af12ea74-a838-4468-8841-00c9f35ef8dd" />

<br>
<br>

Renamed the server to DC01 to reflect is role as the primary Domain Controller

<br>

<img width="1224" height="875" alt="image" src="https://github.com/user-attachments/assets/316dd523-26c3-4f76-9c99-d316239bc137" />

## Step 2 - Installing the Active Directory Domain Services (AD DS) Role
After restarting, I used Server Manager to add the Active Directory Domain Services role.

<img width="1221" height="879" alt="image" src="https://github.com/user-attachments/assets/c65b8a3a-e8ae-467b-a2ca-9cd17578bd2f" />

<br>
<br>

Confirming the server name DC01 at this stage verified that the rename from Step 1 applied correctly before proceeding with the role installation.

<br>

<img width="1224" height="877" alt="image" src="https://github.com/user-attachments/assets/fb558e69-a77f-4365-8702-f907df5444de" />

## Step 3 - Promote the Server to a Domain Controller
Once AD DS was installed, I promoted DC01 to a Domain Controller by creating a new forest with the root domain corp.local.

<img width="1224" height="877" alt="image" src="https://github.com/user-attachments/assets/6cdee4bd-2e90-4af1-a2e6-58aab31359fd" />

<br>
<br>

I left default settings in place for DNS, Additional Options, and Paths, and set a DSRM recovery password before completing the prerequisites check and finalizing the installation.

<br>

<img width="1227" height="877" alt="image" src="https://github.com/user-attachments/assets/99192318-0d8e-4fd0-8428-e4e2ee4632d0" />

## Step 4 - Take a VMware Snapshot
After the server restarted, I verified the Domain Controller was functioning correctly by confirming the login displayed CORP\Administrator.

<img width="1224" height="879" alt="image" src="https://github.com/user-attachments/assets/09c2f46f-1f86-437e-b3e5-449b6a285cb4" />

<br>
<br>

Observed AD and DNS listed in the left panel appeared as active roles in Server Manager. I then took a VMware snapshot to preserve this working baseline as a checkpoint before building on the environment in future labs.

<br>

<img width="1221" height="877" alt="Screenshot 2026-05-19 210059" src="https://github.com/user-attachments/assets/3b0d190b-aa04-43c5-a147-40e80aa5a924" />
