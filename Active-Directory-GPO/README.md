# Active Directory: Secondary Domain Controller + Group Policy Hardening

## Overview
In this project, I configured a Windows Server Active Directory domain environment and added a secondary Domain Controller (DC2) for redundancy. I also applied Group Policy security hardening by configuring password policies, lockout policies, and audit policies to strengthen authentication security across the domain.

This project was completed in a Windows Server 2019/2022 environment and followed real-world domain join and DNS requirements.
---
## Requirements
- Configure a secondary Domain Controller (DC2)
- Create a new Windows Server 2019 or 2022 instance (cloud VM environment)
- Join the new server to the existing domain
- Configure basic password policies using:
  - Local Security Policy
  - Group Policy Management (GPMC)
- Verify DNS settings were correct for domain join and replication
- Troubleshoot connectivity (ping between systems)
---
## Tools Used 
- Windows Server 2019 / 2022
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy Management Console (GPMC)
- Local Security Policy
- Virtual machines / cloud VM environment
---
## What I Did 
### 1. Built the Secondary Domain Controller (DC2)
- Created a new Windows Server instance
- Configured networking to match the domain environment

### 2. Configured DNS Correctly
To ensure domain join and replication worked correctly, I set the DNS configuration on DC2 so that:

- **Primary DNS = IP address of DC1**
- **Secondary DNS = external resolver**

This was required so DC2 could correctly locate the domain services hosted by DC1.

### 3. Joined the Server to the Domain
- Verified connectivity between DC1 and DC2
- Joined DC2 to the existing domain using the correct domain credentials format:
  - `DOMAIN\username`

### 4. Configured Group Policy Security Settings
I configured and verified domain security settings including:
- Password policy (password expiration settings)
- Account lockout policy
- Audit policy settings for security monitoring
---
## Screenshots (Proof of Work)
Screenshots for this project are stored in the `screenshots/` folder.
---

## What I Learned
- How Active Directory Domain Controllers support authentication and centralized identity management
- Why a secondary Domain Controller matters (redundancy + availability)
- How DNS configuration directly impacts domain join and replication
- How Group Policy enforces security controls at scale across an enterprise
- Why password + lockout + auditing policies are core security baselines in Windows environments
---

## 
This project reflects real enterprise Windows administration tasks. Domain-level policy enforcement is one of the most important ways organizations reduce risk from weak passwords, brute-force attacks, and untracked authentication activity. Adding a secondary Domain Controller also improves resiliency and reduces the chance of a single point of failure.
---
## Next Improvements
- Add OU-based policy scoping (instead of applying everything domain-wide)
- Add least privilege role separation (admin vs standard accounts)
- Forward Windows security logs into a SIEM for monitoring

