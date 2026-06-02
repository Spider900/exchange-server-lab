# 📬 Home Lab: Microsoft Exchange Server + Active Directory Integration

## Overview
I extended my self-hosted home lab Active Directory environment with Microsoft Exchange Server. This provided email infrastructure for 1,000+ users — secured with an internally issued SSL certificate from my Domain Controller. For further documentation on my AD lab, see it [here](https://github.com/Spider900/ad-windows-server-lab).

![Badge](https://img.shields.io/badge/Windows_Server_2019-blue) ![Badge](https://img.shields.io/badge/Exchange_Server_SE-green) ![Badge](https://img.shields.io/badge/Active_Directory-yellow) ![Badge](https://img.shields.io/badge/VirtualBox-orange) ![Badge](https://img.shields.io/badge/Internal_PKI_Certificate-grey) 

## Architecture
| Component | Details |
| --------- | ------- |
| Exchange Server | Windows Server 2019 + Exchange Server SE |
| Domain Controller | Windows Server 2019 (existing AD lab) |
| Client Machine  | Windows 11 (domain-joined) |
| Domain Name  | mydomain.com |
| Hypervisor | Oracle VirtualBox |
| Network Adapter | Internal Network |
| DNS | 172.16.0.1 |

## Features Implemented

✅ Microsoft Exchange Server deployed on dedicated VM

✅ Exchange integrated with existing Active Directory domain

✅ Internal mailboxes provisioned for 1,000+ AD users

✅ Internal Certificate Authority (CA) configured on Domain Controller

✅ SSL certificate issued by internal CA and bound to OWA site

✅ OWA accessible over HTTPS from domain-joined client (no certificate warnings)

✅ Send/receive internal email between domain accounts

✅ Mail-enabled users and distribution groups

✅ Group Policy Objects (GPOs) 

## Settings and Configuration

### Exchange Server Active Directory Integration

<img width="1918" height="1021" alt="AD-1" src="https://github.com/user-attachments/assets/daaccb6d-aba3-4157-a1dd-1988b6c0e1fa" />

<img width="1918" height="1018" alt="AD-2" src="https://github.com/user-attachments/assets/99965173-8381-40d6-b925-088e9e61dd31" />

1. Successfully installed Exchange SE and connected the machine to "mydomain.com"

### DNS 

<img width="1918" height="992" alt="DNS-1" src="https://github.com/user-attachments/assets/e96ee873-427a-4d0b-9b84-6abecfd22fd9" />

1. DNS settings for Exchange Server

### GPO Settings

<img width="1918" height="1018" alt="GPO-0" src="https://github.com/user-attachments/assets/a8256e17-8f1f-47f8-a651-06904a07e2af" />

1. Added Exchange Server to different OU in order to implement GPO settings

<img width="1918" height="1017" alt="GPO-1" src="https://github.com/user-attachments/assets/fa455743-99e8-4a6f-b34c-17e073e86dd2" />

2. GPO configured for only admin logon

<img width="1918" height="1020" alt="GPO-2" src="https://github.com/user-attachments/assets/3c4101c1-d212-432e-b620-5bed884c18ef" />

3. User Login attempt

<img width="1918" height="1020" alt="GPO-3" src="https://github.com/user-attachments/assets/fd788372-4ae4-4276-842a-c7db8782cae1" />

4. Login failure due to proper GPO settings

<img width="1918" height="988" alt="GPO-4" src="https://github.com/user-attachments/assets/c8d98197-a8ee-4af7-b135-52e1e8ee0504" />

5. Admin login attempt

<img width="1918" height="1021" alt="GPO-5" src="https://github.com/user-attachments/assets/b35780cd-31e6-404f-a7a8-5585a0a8512b" />

6. Login success

### Mailbox Provisioning

<img width="1918" height="1023" alt="MB-1" src="https://github.com/user-attachments/assets/a1da40e8-a19d-4c88-b47b-3045960b7f1e" />

<img width="1918" height="1023" alt="MB-2" src="https://github.com/user-attachments/assets/6ec16436-c049-43c5-a2ce-d5e3f460fbec" />

1. Used command on Exchange Management to generate mailboxes for 1,000+ users

### Internal Certificate Authority Configuration

<img width="1918" height="1021" alt="ICA-1" src="https://github.com/user-attachments/assets/0b42714d-a4f5-4544-a4cb-d9b8b876cb8b" />

1. Successfully created a CA for my DC

### SSL Cert for OWA

<img width="1918" height="991" alt="ICA-2" src="https://github.com/user-attachments/assets/f1f227e6-5aff-473b-8bf8-c136020f64b2" />

1. Generated internally issued certificate for secure browser logins

### Sending Internal Email

<img width="1918" height="1022" alt="MT-1" src="https://github.com/user-attachments/assets/8f084b60-4f08-422b-8d41-e652f49c9ab7" />

1. From the Windows 11 Client Machine, aabrev will send an email to aacre to showcase email functionality

<img width="1918" height="1020" alt="MT-2" src="https://github.com/user-attachments/assets/1900df78-e3ef-49d7-8ab7-88ff95758b56" />

2. User aacre successfully received mail from user aabrev

## What I learned
1. Active Directory Certificate Services (AD CS) — How to configure a Domain Controller as an internal      Certificate Authority and issue SSL certificates to internal services.

2. Exchange certificate binding — How to generate a certificate request in EAC, fulfill it from an internal CA, and bind it to the IIS/OWA service

3. Mailbox provisioning at scale — Bulk-enabling mailboxes for 1,000+ pre-existing AD users using PowerShell rather than the GUI.

4. Internal PKI concepts — Certificate chains, CA trust stores, and how enterprise environments avoid purchasing public certificates for internal services.

