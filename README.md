# IT Helpdesk Account Lockout & Recovery Simulation (Jane Doe)

## Project Overview
This project shows how to handle a common IT support scenario from start to finish. I used Jira Service Desk to manage an urgent ticket for a locked-out user (Jane Doe), and used Active Directory on a Windows Server virtual machine to safely unlock her account and reset her password.

## Tools Used
* **Jira Service Desk** (For tracking the ticket and communication)
* **Active Directory (ADUC)** (For managing the user account)
* **VirtualBox** (To run the Windows Server lab environment)

## Step-by-Step Walkthrough

### Part 1: Managing the Ticket in Jira

#### 1. Finding the Ticket
Finding the urgent account lockout ticket for Jane Doe in the Jira service desk queue.
![Finding the Ticket](screenshots/screenshot_1.png)

#### 2. Assigning the Ticket
Assigning the ticket to myself so the team knows I am handling Jane's issue.
![Assigning the Ticket](screenshots/screenshot_2.png)

#### 3. Moving to In Progress
Changing the ticket status to 'In Progress' to officially start the recovery workflow.
![Moving to In Progress](screenshots/screenshot_3.png)

#### 4. Contacting the User
Sending a quick message to Jane Doe letting her know I am actively working on unlocking her account.
![Contacting the User](screenshots/screenshot_4.png)

---

### Part 2: Fixing the Issue in Active Directory

#### 5. Accessing the Lab Environment
Opening the Windows Server lab environment inside VirtualBox and launching Active Directory Users and Computers.
![Accessing the Lab Environment](screenshots/screenshot_5.png)

#### 6. Locating Jane Doe's Account
Locating Jane Doe's locked-out user account profile inside the organizational unit folder.
![Locating Jane Doe's Account](screenshots/screenshot_6.png)

#### 7. Account Reset & Unlock
Unlocking Jane Doe's account, setting a secure temporary password, and checking the box to force her to choose a new password at next logon.
![Account Reset & Unlock](screenshots/screenshot_7.png)

---

### Part 3: Closing and Documenting the Ticket

#### 8. Logging the Internal Note
Adding an internal note to the Jira ticket explaining exactly how the account was unlocked and reset for documentation.
![Logging the Internal Note](screenshots/screenshot_8.png)

#### 9. Resolution Form
Filling out the final resolution form and changing the status to 'Done'.
![Resolution Form](screenshots/screenshot_9.png)

#### 10. Final Ticket Status
The final view of the ticket showing Jane Doe's request is successfully marked as 'Resolved'.
![Final Ticket Status](screenshots/screenshot_10.png)
