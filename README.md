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
| **Guest OS (Client)** | Windows 11 Pro | Enterprise corporate endpoint machine (`Windows-11-Client`). |

### Network Topology Mapping
To ensure strict security and prevent interference with home production networks, the virtualization layer relies on a segregated software-defined network:
* **Network Type:** VirtualBox Internal Network (`intnet`)
* **Domain Name:** `mydomain.local`
* **Domain Controller (`DC1`):** Static IP allocation with Active Directory, DNS, and DHCP services active.
* **Client Machine:** DHCP-assigned lease via `DC1`, joined to the `mydomain.local` domain.

---

## Repository Structure
To ensure that your portfolio page displays all visual evidence correctly, arrange your local workspace to mirror the directory tree below before pushing to GitHub:

```text
├── README.md
└── images/
    ├── screenshot_01.png
    ├── screenshot_02.png
    ├── screenshot_03.png
    ├── screenshot_04.png
    ├── screenshot_05.png
    ├── screenshot_06.png
    ├── screenshot_07.png
    ├── screenshot_08.png
    └── screenshot_09.png
