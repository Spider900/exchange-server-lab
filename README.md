# 📬 Home Lab: Microsoft Exchange Server + Active Directory Integration

# Overview
I extended my self-hosted home lab Active Directory environment with Microsoft Exchange Server. This provided email infrastructure for 1,000+ users — secured with an internally issued SSL certificate from my Domain Controller. For further documentation on my AD lab, see it [here](https://github.com/Spider900/ad-windows-server-lab).

![Badge](https://img.shields.io/badge/Windows_Server_2019-blue) ![Badge](https://img.shields.io/badge/Exchange_Server_SE-green) ![Badge](https://img.shields.io/badge/Active_Directory-yellow) ![Badge](https://img.shields.io/badge/VirtualBox-orange) ![Badge](https://img.shields.io/badge/Internal_PKI_Certificate-grey) 

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

# Features Implemented

✅ Microsoft Exchange Server deployed on dedicated VM

✅ Exchange integrated with existing Active Directory domain

✅ Internal mailboxes provisioned for 1,000+ AD users

✅ Internal Certificate Authority (CA) configured on Domain Controller

✅ SSL certificate issued by internal CA and bound to OWA site

✅ OWA accessible over HTTPS from domain-joined client (no certificate warnings)

✅ Send/receive internal email between domain accounts

✅ Mail-enabled users and distribution groups
