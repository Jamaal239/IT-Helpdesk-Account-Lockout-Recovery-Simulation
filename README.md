# Enterprise IT Support & Identity Management Pipeline: End-to-End Incident Triage & Active Directory Remediation

## Project Overview
This project serves as a comprehensive, production-grade documentation of an enterprise-level IT Support and Systems Administration lifecycle. It simulates a high-pressure, time-sensitive corporate incident: an executive/employee account lockout during a critical business window. 

The objective of this project is to demonstrate the seamless integration between front-end ITSM triage systems and back-end Identity & Access Management (IAM) infrastructure. The entire lifecycle—from customer ingestion, automated SLA tracking, virtualization infrastructure validation, directory service remediation, to formal incident closure—is fully visualized and documented below.

### Target Objectives & Key Results (OKRs)
* **Minimize MTTR (Mean Time to Resolution):** Remediate a business-critical account lockout within a strict 48-hour SLA window (achieved in under 20 minutes simulation time).
* **Maintain Audit Trail Compliance:** Ensure all infrastructure modifications (password resets, policy enforcements) are accurately mirrored inside the ITSM internal audit notes.
* **Enforce Zero-Trust Credentialing:** Guarantee that all administrative overrides force end-user credential rotation upon next authentication.

---

## Technical Stack & Architecture

| Component | Technology | Role / Function |
| :--- | :--- | :--- |
| **ITSM Platform** | Jira Service Management (Cloud) | Ticket ingestion, queue management, SLA enforcement, customer communication hub. |
| **Hypervisor** | Oracle VirtualBox Manager v7.x | Hosts enterprise virtual machine infrastructure locally. |
| **Directory Services** | Active Directory Domain Services (AD DS) | Identity & Access Management provider for the `mydomain.local` forest. |
| **Guest OS (Server)** | Windows Server 2022 Standard | Active Directory Domain Controller (`DC1`). |
| **Guest OS (Client)** Pro | Enterprise corporate endpoint machine (`Windows-11-Client`). |

### Network Topology Mapping
To ensure strict security and prevent interference with home production networks, the virtualization layer relies on a segregated software-defined network:
* **Network Type:** VirtualBox Internal Network (`intnet`)
* **Domain Name:** `mydomain.local`
* **Domain Controller (`DC1`):** Static IP allocation with Active Directory, DNS, and DHCP services active.
* **Client Machine:** DHCP-assigned lease via `DC1`, joined to the `mydomain.local` domain.

---

## Step-by-Step Rollout & Incident Walkthrough

### Phase 1: Incident Ingestion & ITSM Triage
An urgent support request is initialized regarding a corporate account lockout. The user notes an upcoming presentation in 20 minutes, automatically escalating the operational impact of the incident.

![Creating the initial high-priority IT support ticket in Jira Service Management](screenshot_01.png)
*Figure 1: Incident generation within Jira Service Management, specifying the user's critical timeline.*

Once generated, the incident lands inside the centralized Helpdesk queue. The system automatically tags it under the global service catalog and parses relevant tracking metadata.

![Jira Helpdesk queue showing the newly created ticket under 'Waiting for Support'](screenshot_02.png)
*Figure 2: The Enterprise Helpdesk dashboard tracking open workloads. Incident `EH-2` is successfully queued.*

The ticket view provides the responding administrator with granular control over systemic variables, SLA countdown vectors, and real-time ownership assignments.

![Detailed view of the open Jira ticket highlighting description and SLA metrics](screenshot_03.png)
*Figure 3: Open incident diagnostic overview. Note the automated SLA mappings: Time to First Response (12h) and Time to Resolution (48h).*

---

### Phase 2: Virtualization Infrastructure Verification
Before accessing directory tools, the administrator verifies the health and operational availability of the virtualized directory infrastructure.

![Oracle VirtualBox Manager showing the Windows Server 2022 Domain Controller in a running state](screenshot_04.png)
*Figure 4: Oracle VirtualBox Manager environment running the primary Domain Controller (`DC1`) under an isolated internal network (`intnet`).*

---

### Phase 3: Identity & Access Management Remediation
The administrator establishes a secure session into the Domain Controller (`DC1`) and initializes the Active Directory Users and Computers (ADUC) management console to query the target account.

![Active Directory Users and Computers interface showing the _Employees organizational unit](screenshot_05.png)
*Figure 5: Navigating the logical directory structure (`mydomain.local` -> `_Employees` Organizational Unit) to locate the user record for Jane Doe.*

To safely restore user access, the administrator executes a password override. Simultaneously, the system automatically clears the underlying security lockout attribute flags.

![Active Directory password reset dialog box with 'User must change password at next logon' checked](screenshot_06.png)
*Figure 6: Configuring secure temporary credentials. Enforcing 'User must change password at next logon' to maintain compliance with standard zero-trust IAM frameworks.*

---

### Phase 4: Audit Tracking, Resolution, & Closure
Following successful infrastructure changes, the administrator updates internal audit trails to preserve historical change records before notifying the customer.

![Adding an internal note to the Jira ticket outlining the resolution steps taken](screenshot_07.png)
*Figure 7: Recording detailed infrastructure modification actions directly onto the ticket's internal work log layer.*

With documentation satisfied, the administrator initiates the workflow transition state to formally shift the incident out of the active engineering queue.

![The Jira 'Resolve this issue' pop-up screen filled out with resolution comments](screenshot_08.png)
*Figure 8: Closing the ticket workspace loop by specifying the finalized resolution code and pushing the ticket to public-facing closure.*

The ticket lifecycle reaches a terminal status of `Resolved`. All processing clocks halt, and the successful mitigation is stored within the platform index for future knowledge base cross-referencing.

![The finalized Jira Service Management ticket marked as 'Resolved' and 'Done'](screenshot_09.png)
*Figure 9: Finalized view of closed incident `EH-2`. Ticket metrics indicate completion well ahead of target enterprise SLA markers.*

---

## Key Takeaways & Verification
1. **Security Compliance:** By checking the *User must change password at next logon* property, the temporary administrative password remains unexposed, passing ultimate credential ownership back to the user.
2. **System Synchronization:** The project cleanly illustrates how real-world systems engineers use operational ticketing systems as a source of truth to drive back-end infrastructure workflows.
3. **SLA Adherence:** Rapid triage and precise lab execution resulted in a turnaround time of minutes, protecting business continuity during critical events.
