# Entra ID and Device Enrolment

## Overview

This section covers the core **Microsoft Entra ID** and **Microsoft Intune** tasks I completed to prepare users and devices for cloud-based management. I created and managed **user accounts**, configured **security groups** for policy targeting, reviewed **sign-in activity**, and enrolled a **Windows 10 Pro** device into Microsoft Intune. These tasks demonstrate fundamental **identity and device management** skills commonly used within an IT Support environment.

---

# Task 1 - Creating and Configuring a Microsoft Entra ID User

## Objective

Create and configure a **Microsoft Entra ID** user account with appropriate organisational information to support **identity management** and future **Microsoft Intune** assignments.

---

## Implementation

I created a new **Microsoft Entra ID** user account for the fictional **JayTech Ltd** environment and configured relevant profile information including the user's **job title**, **company**, and **department**.

The user was assigned to the **IT department**, providing organisational information that can later be used for **group membership**, **Intune policy assignments**, and automated identity management.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Users
→ All users
→ New user
→ Create new user
→ Enter User Principal Name and Display Name
→ Properties
→ Configure Identity Information
→ Configure Job Information
→ Review + create
→ Create
```

---

## Outcome

The **Microsoft Entra ID** user account was successfully created and configured with the appropriate organisational attributes, providing a managed identity that can be used throughout the **Microsoft Intune** environment.

---

## Screenshots

**Figure 1:** Microsoft Entra ID user configured with **IT Support Technician**, **JayTech Ltd**, and **IT department** attributes.

<img width="1919" height="912" alt="01 – Creating and Configuring a Microsoft Entra ID User" src="https://github.com/user-attachments/assets/baec6a2e-cc32-4704-8f95-bf3a357df539" />

# Task 2 - Reviewing Microsoft Entra ID Sign-In Logs

## Objective

Review **Microsoft Entra ID** sign-in activity to verify user authentication and understand how sign-in logs can support the investigation of account access issues.

---

## Implementation

I signed in using the newly created **Hardy D'Souza** account to generate authentication activity within the **JayTech Ltd** environment. The initial sign-in event was recorded as **Interrupted** because the temporary password needed to be changed before the authentication process could continue.

After changing the password, I successfully signed in with the account. I then reviewed the user's **sign-in logs** within Microsoft Entra ID and examined the successful authentication event to confirm the sign-in status and review the available authentication information.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Users
→ All users
→ Hardy D'Souza
→ Sign-in logs
→ Select Sign-In Event
→ Activity Details
```

---

## Outcome

The **Microsoft Entra ID** sign-in logs successfully recorded the user's authentication activity, showing the initial **Interrupted** event followed by a **successful sign-in** after the required password change. The successful event also provided additional authentication information that can assist IT Support when investigating user access and sign-in issues.

---

## Screenshot

**Figure 1:** **Microsoft Entra ID sign-in logs** showing the initial **Interrupted** event followed by the successful sign-in for **Hardy D'Souza**.

<img width="1919" height="912" alt="02 – Reviewing User Sign-In Logs" src="https://github.com/user-attachments/assets/7f278520-7570-4730-b823-70f57c108747" />

**Figure 2:** **Activity Details** confirming the successful authentication event and displaying the associated sign-in information for **Hardy D'Souza**.

<img width="1918" height="913" alt="03 – Reviewing User Sign-In Logs" src="https://github.com/user-attachments/assets/f74cc847-af54-425a-871d-bc8f365f9ee3" />
