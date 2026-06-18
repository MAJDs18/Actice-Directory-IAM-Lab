 # Active Directory Security & Identity and Access Management (IAM) Lab

## Project Overview
This hands-on cybersecurity project demonstrates the deployment, configuration, and hardening of an enterprise environment using Windows Server 2022 inside a virtualized infrastructure. The core focus is establishing a robust Identity and Access Management (IAM) hierarchy and enforcing security baselines through Group Policy Objects (GPOs) following the Principle of Least Privilege (PoLP).

---

## Technical Specifications
* **Hypervisor:** Oracle VirtualBox
* **Operating System:** Windows Server 2022 Standard (Evaluation Edition)
* **Roles Implemented:** Active Directory Domain Services (AD DS), DNS Server

---

## Lab Implementation Phases

### Phase 1: Domain Controller Deployment & Hardening
* Deployed a clean instance of Windows Server 2022.
* Configured static IP networking and promoted the server to a Domain Controller, establishing the root domain forest (`majd.local`).

> *Enterprise Domain Infrastructure successfully provisioned.*

---

### Phase 2: Identity & Access Management (IAM) Hierarchy Design
* Designed a structured Organizational Unit (OU) topology replicating a real-world enterprise architecture (e.g., separating administrative functions from standard business units like HR).
* Provisioned enterprise user accounts (e.g., `Ahmad`) within their designated OUs, establishing role-based access control (RBAC) operational parameters.

---

### Phase 3: Security Policy Enforcement (Group Policy Hardening)
* Formulated targeted Group Policy Objects (GPOs) to minimize the attack surface of endpoint workstations.
* Configured administrative templates to enforce endpoint isolation, specifically enabling the **"Prohibit access to Control Panel and PC settings"** policy.
* Successfully forced enterprise-wide policy distribution and immediate propagation across the domain.

---

## Verification & Key Artifacts

### 1. Active Directory Identity Hierarchy (IAM Blueprint)
![Active Directory Infrastructure](images/iam.png)
*Evidence of structured OU engineering, showcasing administrative container separation and domain account provisioning.*

### 2. GPO Hardening Rule Configuration
![Group Policy Configuration](images/gpo.png)
*Technical proof showing the specific administrative template configuration utilized to restrict system-level changes on endpoints.*

### 3. Server Promotion & Domain Access Control
![Domain Controller Verification](images/domain.png)
*Active administration session verifying successful domain forest registration and secure administrator privileges.*

### 4. Group Policy Security Propagation
![GPO Enforcement Success](images/success.png)
*Command-line validation showing execution of policy synchronization, confirming the endpoint infrastructure has successfully received and applied the hardening rules.*
