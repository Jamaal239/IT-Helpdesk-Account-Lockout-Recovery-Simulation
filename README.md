# Enterprise IT Support & Identity Management Pipeline: End-to-End Incident Triage & Active Directory Remediation

## 📋 Project Overview
This project serves as a comprehensive, production-grade documentation of an enterprise-level IT Support and Systems Administration lifecycle updated to modern operational standards. It simulates a high-pressure, time-sensitive corporate incident: an executive/employee account lockout during a critical business window.

The objective of this project is to demonstrate the seamless integration between front-end ITSM triage systems and back-end Identity & Access Management (IAM) infrastructure. The entire lifecycle—from customer ingestion, automated SLA tracking, virtualization infrastructure validation, directory service remediation, to formal incident closure—is fully visualized and documented below.

---

## 🎯 Target Objectives & Key Results (OKRs)
* **Minimize MTTR (Mean Time to Resolution):** Remediate a business-critical account lockout within a strict 48-hour SLA window (achieved in under 20 minutes simulation time).
* **Maintain Audit Trail Compliance:** Ensure all infrastructure modifications (password resets, policy enforcements) are accurately mirrored inside the ITSM internal audit notes.
* **Enforce Zero-Trust Credentialing:** Guarantee that all administrative overrides force end-user credential rotation upon next authentication.

---

## 💻 Technical Stack & Architecture

| Component | Technology | Role / Function |
| :--- | :--- | :--- |
| **ITSM Platform** | Jira Service Management (Cloud) | Ticket ingestion, queue management, SLA enforcement, customer communication hub. |
| **Hypervisor** | Oracle VirtualBox Manager v7.x | Hosts enterprise virtual machine infrastructure locally. |
| **Directory Services** | Active Directory Domain Services (AD DS) | Identity & Access Management provider for the `mydomain.local` forest. |
| **Guest OS (Server)** | Windows Server Standard | Active Directory Domain Controller (`DC-01`). |
| **Guest OS (Client)** | Windows 11 Pro | Enterprise corporate endpoint machine (`W11-CLIENT-01`). |

### Network Topology Mapping
To ensure strict security and prevent interference with home production networks, the virtualization layer relies on a segregated software-defined network:
* **Network Type:** VirtualBox Internal Network (`intnet`)
* **Domain Name:** `mydomain.local`
* **Domain Controller (DC-01):** Static IP allocation with Active Directory, DNS, and DHCP services active.
* **Client Machine:** DHCP-assigned lease via DC-01, joined to the `mydomain.local` domain.

---

## 📜 Step-by-Step Rollout & Incident Walkthrough

### Phase 1: Incident Ingestion & ITSM Triage

#### Step 1: Submitting the Support Request
An urgent support request is initialized regarding a corporate account lockout. The user notes an upcoming presentation in 20 minutes, automatically escalating the operational impact of the incident.

![Incident generation within Jira Service Management](./screenshots/screenshot_01.png)

#### Step 2: Reviewing the Incoming Queue
Once generated, the incident lands inside the centralized Helpdesk queue. The system automatically tags it under the global service catalog and parses relevant tracking metadata.

![The Enterprise Helpdesk dashboard tracking open workloads](./screenshots/screenshot_02.png)

#### Step 3: Assigning and Owning the Ticket
The ticket view provides the responding administrator with granular control over systemic variables, SLA countdown vectors, and real-time ownership assignments.

![Open incident diagnostic overview with SLA mappings](./screenshots/screenshot_03.png)

---

### Phase 2: Virtualization Infrastructure Verification

#### Step 4: Verifying the Directory State
Before accessing directory tools, the administrator verifies the health and operational availability of the virtualized directory infrastructure.

![Oracle VirtualBox Manager environment running the primary Domain Controller](./screenshots/screenshot_04.png)

---

### Phase 3: Identity & Access Management Remediation

#### Step 5: Querying the Target Account
The administrator establishes a secure session into the Domain Controller and initializes the Active Directory Users and Computers (ADUC) management console to query the target account.

![Navigating the logical directory structure to locate the user record](./screenshots/screenshot_05.png)

#### Step 6: Executing the Reset & Account Unlock
To safely restore user access, the administrator executes a password override. Simultaneously, the system automatically clears the underlying security lockout attribute flags.

![Configuring secure temporary credentials and enforcing password rotation](./screenshots/screenshot_06.png)

---

### Phase 4: Audit Tracking, Resolution, & Closure

#### Step 7: Logging the Internal Audit Note
Following successful infrastructure changes, the administrator updates internal audit trails to preserve historical change records before notifying the customer.

![Recording detailed infrastructure modification actions directly onto the ticket](./screenshots/screenshot_07.png)

#### Step 8: Submitting the Resolution Form
With documentation satisfied, the administrator initiates the workflow transition state to formally shift the incident out of the active engineering queue.

![Specifying the finalized resolution code and closing the workspace loop](./screenshots/screenshot_08.png)

#### Step 9: Final Ticket Closure Status
The ticket lifecycle reaches a terminal status of Resolved. All processing clocks halt, and the successful mitigation is stored within the platform index for future knowledge base cross-referencing.

![Finalized view of closed incident under target enterprise SLA markers](./screenshots/screenshot_09.png)

---

## 🔍 Key Takeaways & Verification
* **Security Compliance:** By checking the *User must change password at next logon* property, the temporary administrative password remains unexposed, passing ultimate credential ownership back to the user.
* **System Synchronization:** The project cleanly illustrates how real-world systems engineers use operational ticketing systems as a source of truth to drive back-end infrastructure workflows.
* **SLA Adherence:** Rapid triage and precise lab execution resulted in a turnaround time of minutes, protecting business continuity during critical events.
