# Windows Server 2022: Active Directory & IAM Security Hardening Lab

## Project Overview
This project demonstrates the deployment, configuration, and security hardening of an enterprise Identity and Access Management (IAM) infrastructure using **Windows Server 2022** inside a virtualized environment (**Oracle VirtualBox**). 

The primary objective was to architect a production-ready **Active Directory Domain Services (AD DS)** environment, implement a secure administrative hierarchy, and enforce system-level security restrictions using **Group Policy Objects (GPOs)** based on the Principle of Least Privilege (PoLP).

---

## Technical Specifications & Topology
* **Hypervisor:** Oracle VirtualBox
* **Operating System:** Windows Server 2022 Datacenter (Evaluation Edition)
* **Domain Name:** `cyberlab.local`
* **Core Services:** Active Directory Domain Services (AD DS), DNS, Group Policy Management

---

## Architecture & Implementation Steps

### 1. Active Directory Installation & Domain Promotion
* Configured static IP addressing and internal network settings to isolate the environment.
* Installed the AD DS role via Server Manager and promoted the server to a **Domain Controller (DC)**, establishing the root domain forest.

### 2. Identity & Access Management (IAM) Hierarchy Design
* Designed and engineered a structured **Organizational Unit (OU)** tree to separate administrative boundaries, departments, and assets.
* Provisioned standard domain user accounts (e.g., `Ahmad`) within designated functional OUs to test policy propagation.
* Applied **Role-Based Access Control (RBAC)** to ensure users only have access to resources required for their explicit operational roles.

### 3. Group Policy Security Hardening
* Created and linked custom **Group Policy Objects (GPOs)** to enforce specific baseline security controls across endpoints.
* **Applied Rule:** *Prohibit access to Control Panel and PC settings* to reduce the system's attack surface and prevent unauthorized configuration changes by non-administrative users.
* Validated policy enforcement on target organizational containers using command-line administrative utilities.

---

## Verification & Key Artifacts

### 1. تسلسل هوية Active Directory (مخطط IAM)
![Active Directory Infrastructure](images/iam.jpeg)
*Evidence of structured OU engineering, showcasing administrative container separation and domain account provisioning.*

### 2. تكوين قواعد تقوية GPO
![Group Policy Configuration](images/gpo.jpeg)
*Technical proof showing the specific administrative template configuration utilized to restrict system-level changes on endpoints.*

### 3. الترويج للخوادم والتحكم في الوصول إلى النطاقات
![Domain Controller Verification](images/domain.jpeg)
*Active administration session verifying successful domain forest registration and secure administrator privileges.*

### 4. نشر سياسة المجموعات في أمن
![GPO Enforcement Success](images/success.jpeg)
*Command-line validation showing execution of policy synchronization, confirming the endpoint infrastructure has successfully received and applied the hardening rules.*
