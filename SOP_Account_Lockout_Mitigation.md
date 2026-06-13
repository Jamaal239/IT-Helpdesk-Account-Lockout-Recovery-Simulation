# Standard Operating Procedure (SOP): Active Directory Account Lockout Mitigation

**Document ID:** SOP-IT-042  
**Target Audience:** Tier 1 Service Desk / IT Support Specialists  
**Objective:** To safely verify user identity, identify the root cause of a Windows domain account lockout, and securely unlock the account within Active Directory Domain Services (AD DS).

---

## 1. Initial Verification & Security Protocol
Before modifying any account status, technician verification is mandatory to prevent social engineering attacks.
* **Action:** Challenge the inbound user for corporate validation (e.g., employee ID, manager verification, or secondary multi-factor challenge).
* **Rule:** Never unlock an account without positive identity confirmation.

---

## 2. Technical Resolution Workflow

### Phase A: Identify the Lockout State
1. Log into the management workstation or Domain Controller.
2. Open **Active Directory Users and Computers (ADUC)** (`dsa.msc`).
3. Navigate to the target user's **Organizational Unit (OU)**.
4. Right-click the user profile, select **Properties**, and navigate to the **Account** tab.
5. Verify if the checkbox text reads: *"This account is currently locked out on this Active Directory Domain Controller."*

### Phase B: Unlocking the Account
1. Check the box next to **Unlock account**.
2. Click **Apply** and then click **OK**.

---

## 3. Diagnostics & Root Cause Analysis
Unlocking the account is only temporary if the underlying issue isn't fixed. If the account locks out again immediately, check the following common failure points:
* **Saved Credentials:** Check the user's secondary devices (phones, tablets) to see if an old corporate password is saved on the corporate Wi-Fi network.
* **Mapped Network Drives:** Ensure disconnected network shares aren't attempting to authenticate with stale credentials.
* **Windows Credential Manager:** Have the user open `Control Panel` -> `Credential Manager` and clear out old cached enterprise password tokens.

---

## 4. Ticket Closure & SLA Documentation
* **Action:** Document the root cause within the active helpdesk ticket (Jira/ServiceNow).
* **SLA Target:** Ensure initial contact-to-resolution falls within the standard 30-minute high-priority window.
