# ActiveDirectory-HomeLab

## Objective:
Configure a Windows Server 2022 virtual machine as a fully functional Active Directory Domain Controller in a virtualized lab environment using VMware Workstation Pro.

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
After logging in the workstation for the first time, the System Dashboard immediately pops up. During initial setup, go to the network icon in the bottom right, right-click, and navigate to "Open Network & Internet Settings". After this, configure the static IP address as shown.

<img width="1224" height="879" alt="image" src="https://github.com/user-attachments/assets/af12ea74-a838-4468-8841-00c9f35ef8dd" />

We will rename this PC to DC01 (Domain Controller 1).
<img width="1224" height="875" alt="image" src="https://github.com/user-attachments/assets/316dd523-26c3-4f76-9c99-d316239bc137" />


