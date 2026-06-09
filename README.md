# IT Helpdesk Account Lockout & Recovery Simulation

## Project Overview
This project shows how to handle a common IT support scenario from start to finish. I used Jira Service Desk to manage an urgent ticket for a locked-out user, and used Active Directory on a Windows Server virtual machine to safely unlock the user's account and reset their password.

## Tools Used
* **Jira Service Desk** (For tracking the ticket and communication)
* **Active Directory (ADUC)** (For managing the user account)
* **VirtualBox** (To run the Windows Server lab environment)

## Step-by-Step Walkthrough

### Part 1: Managing the Ticket in Jira

#### 1. Finding the Ticket
Finding the urgent account lockout ticket in the Jira queue.
![Finding the Ticket](screenshots/screenshot_1.png)

#### 2. Assigning the Ticket
Assigning the ticket to myself so the team knows I am handling it.
![Assigning the Ticket](screenshots/screenshot_2.png)

#### 3. Moving to In Progress
Changing the ticket status to 'In Progress' to start working on it.
![Moving to In Progress](screenshots/screenshot_3.png)

#### 4. Contacting the User
Sending a quick message to the user letting them know I am working on their issue.
![Contacting the User](screenshots/screenshot_4.png)

---

### Part 2: Fixing the Issue in Active Directory

#### 5. Lab Environment
Opening the Windows Server lab environment inside VirtualBox.
![Lab Environment](screenshots/screenshot_5.png)

#### 6. Locating the Account
Locating the user's account inside Active Directory Users and Computers.
![Locating the Account](screenshots/screenshot_6.png)

#### 7. Account Reset & Unlock
Unlocking the account and setting a temporary password, forcing the user to choose a new one when they log back in.
![Account Reset & Unlock](screenshots/screenshot_7.png)

---

### Part 3: Closing and Documenting the Ticket

#### 8. Logging the Internal Note
Adding an internal note to the Jira ticket explaining exactly how the issue was fixed.
![Logging the Internal Note](screenshots/screenshot_8.png)

#### 9. Resolution Form
Filling out the final resolution form and changing the status to 'Done'.
![Resolution Form](screenshots/screenshot_9.png)

#### 10. Final Ticket Status
The final view of the ticket showing it is successfully marked as 'Resolved'.
![Final Ticket Status](screenshots/screenshot_10.png)
