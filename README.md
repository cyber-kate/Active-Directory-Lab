# Active Directory Domain Controller Lab 

Deploying an Active Directory domain controller in a virtual lab with VirtualBox, Windows Server 2022, and Windows 11 Pro, then joining a client to the domain and signing in with a domain account.

**Date:** May–June 2026
**Full write-up with screenshots:** [ADDC Lab KS.pdf](ADDC%20Lab%20KS.pdf)

## Objective

Build a small Active Directory environment that simulates a company: a domain controller, organizational units (OUs), and users. Validate it by joining a Windows 11 client to the domain and logging in as a domain user.

## Tools Used

- Oracle VirtualBox
- Windows Server 2022 Standard Evaluation (Desktop Experience)
- Windows 11 Pro (25H2)

## Lab Environment

| | ADDC01 (server) | Windows 11 Pro (client) |
|---|---|---|
| Resources | 4096 MB RAM, 2 CPUs, 60 GB disk | 12000 MB RAM, 4 CPUs, 100 GB disk |
| IP address | 10.0.2.20 / 255.255.255.0 | 10.0.2.15 / 255.255.255.0 |
| Default gateway | 10.0.2.2 | 10.0.2.2 |
| Preferred DNS | 127.0.0.1 (itself) | 10.0.2.20 (ADDC01) |
| Domain | company.local (NetBIOS: COMPANY) | Member of company.local |

## What I Did

1. **Created the server VM** in VirtualBox from the Windows Server 2022 evaluation ISO.
2. **Installed Windows Server 2022** (Standard Evaluation, Desktop Experience).
3. **Configured a static IP** on the server and verified it with `ipconfig` and `ping`.
4. **Renamed the server** to `ADDC01`.
5. **Installed the Active Directory Domain Services (AD DS) role** through Server Manager.
6. **Promoted the server
