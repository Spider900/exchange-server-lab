# 📬 Home Lab: Microsoft Exchange Server + Active Directory Integration

# Overview
I extended my existing Active Directory home lab by deploying Microsoft Exchange Server SE on oracle vm, integrating it with my domain controller at mydomain.com. 
This lab demonstrates enterprise-grade internal email infrastructure, including mailbox provisioning for 1,000+ existing AD users. For further documentation on my AD lab, see it [here](https://github.com/Spider900/ad-windows-server-lab).

![Badge](https://img.shields.io/badge/Windows_Server_2019-blue) ![Badge](https://img.shields.io/badge/Exchange_Server_SE-green) ![Badge](https://img.shields.io/badge/Active_Directory-yellow) ![Badge](https://img.shields.io/badge/VirtualBox-orange)

# Architecture
| Component | Details |
| --------- | ------- |
| Exchange Server | Windows Server 2019 + Exchange Server SE |
| Domain Controller | Windows Server 2019 (existing AD lab) |
| Client Machine  | Windows 11 (domain-joined) |
| Domain Name  | mydomain.com |
| Hypervisor | Oracle VirtualBox |
| Network Adapter | Internal Network |
| DNS | 172.16.0.1 |

Features Implemented

✅ Microsoft Exchange Server deployed on dedicated VM

✅ Exchange integrated with existing Active Directory domain

✅ Internal mailboxes provisioned for 1,000+ AD users

✅ Outlook Web App (OWA) accessible from client machine

✅ Send/receive internal email between domain accounts

✅ Exchange Admin Center (EAC) configuration

✅ Configured AD and Exchange Certificate Services for secure web connections to mail server
