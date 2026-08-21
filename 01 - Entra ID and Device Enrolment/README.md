# Entra ID and Device Enrolment

## Overview

This section covers the core **Microsoft Entra ID** identity and device enrolment tasks I completed within the **Microsoft Intune Administration Lab**. I created and configured a user account, reviewed **sign-in activity**, configured device settings, created security groups for policy targeting, and enrolled a **Windows 10 Pro** device into **Microsoft Intune**.

These tasks demonstrate practical **IT Support** skills involving cloud identity administration, user authentication, group management, device registration, and endpoint enrolment within a Microsoft cloud environment.

---

# Task 1 - Creating and Configuring a Microsoft Entra ID User

## Objective

Create and configure a **Microsoft Entra ID** user account with appropriate organisational information for a new employee within the **JayTech Ltd** environment.

---

## Implementation

I created a new **Microsoft Entra ID** user account for **Hardy Souza**, who was joining the fictional **JayTech Ltd** environment as an **IT Support Technician**.

I configured the account as a **Member** and added the user's job title, company, and department information. The **Department** attribute was set to **IT**, providing organisational information that can later be used for group membership and policy targeting.

---

## Navigation

```text
Microsoft Entra Admin Center
→ Entra ID
→ Users
→ All users
→ New user
→ Create new user
→ Configure User Principal Name and Display Name
→ Properties
→ Configure Identity Information
→ Configure Job Information
→ Review + create
→ Create
```

---

## Outcome

The **Microsoft Entra ID** user account for **Hardy Souza** was successfully created and configured as an **IT Support Technician** within the **IT department** of **JayTech Ltd**.

---

## Screenshot

**Figure 1:** Configuring the **Microsoft Entra ID** user with **IT Support Technician**, **JayTech Ltd**, and **IT department** organisational information.

<img width="1919" height="912" alt="01 – Creating and Configuring a Microsoft Entra ID User" src="https://github.com/user-attachments/assets/3bbe2c6e-ad4e-4ffb-85cb-84d7cac8edd3" />

# Task 2 - Reviewing Microsoft Entra ID Sign-in Logs

## Objective

Review **Microsoft Entra ID sign-in logs** to verify a user's authentication activity and investigate the status of recent sign-in attempts.

---

## Implementation

I signed in using the newly created **Hardy Souza** account and then reviewed the user's **interactive sign-in logs** from the **Microsoft Entra Admin Center**.

The logs recorded an initial **Interrupted** sign-in while the new account completed its required authentication process, followed by a **Successful** sign-in. I then opened the successful event to review its authentication details and confirm that access had been completed successfully.

The event details also showed that **multifactor authentication** was required and that the MFA requirement had been satisfied by a claim in the authentication token.

---

## Navigation

```text
Microsoft Entra Admin Center
→ Entra ID
→ Users
→ All users
→ Hardy Souza
→ Sign-in logs
→ Review User sign-ins (interactive)
→ Select Successful Sign-in Event
→ Activity Details: Sign-ins
→ Basic info
```

---

## Outcome

The **Microsoft Entra ID sign-in logs** confirmed a successful authentication for **Hardy Souza**. Reviewing the individual event provided additional authentication information that could be used by an **IT Support Technician** when investigating user sign-in and access issues.

---

## Screenshot

**Figure 2:** Reviewing **Hardy Souza's interactive sign-in activity**, showing the initial **Interrupted** event followed by a **Successful** authentication.

<img width="1919" height="914" alt="02 – Reviewing User Sign-In Logs" src="https://github.com/user-attachments/assets/1a3bb924-aeda-4219-9b98-3dbdfda58811" />

**Figure 3:** Reviewing the successful sign-in **Activity Details**, confirming **Status: Success** and the associated **multifactor authentication** requirement.

<img width="1919" height="913" alt="03 – Reviewing User Sign-In Logs" src="https://github.com/user-attachments/assets/a2e0386f-78e5-4c6b-b084-f77358e40c19" />

# Task 3 - Configuring Microsoft Entra Device Settings

## Objective

Review and configure **Microsoft Entra ID** device settings to control how users can join devices to the organisation and prepare the environment for future **Microsoft Intune** device enrolment.

---

## Implementation

I reviewed the **Microsoft Entra join and registration settings** within the **Microsoft Entra admin center** to confirm that users are permitted to join devices to the **JayTech Ltd** environment.

Device joining was available to **All users**, while the maximum number of devices permitted per user was set to **50**. I also reviewed the existing **Multifactor Authentication (MFA)** requirement for device registration and joining, which was currently set to **No**.

These settings establish the **Microsoft Entra ID** device join configuration that will support the onboarding and management of Windows devices through **Microsoft Intune** later in the lab.

---

## Navigation

```text
Microsoft Entra Admin Center
→ Entra ID
→ Devices
→ Device settings
→ Microsoft Entra join and registration settings
→ Review Users may join devices to Microsoft Entra
→ Review Multifactor Authentication requirement
→ Review Maximum number of devices per user
```

---

## Outcome

The **Microsoft Entra ID** device settings were successfully reviewed and confirmed, with users permitted to join devices to the **JayTech Ltd** environment. The tenant is now prepared for the later onboarding and management of Windows devices through **Microsoft Intune**.

---

## Screenshot

**Figure 4:** **Microsoft Entra join and registration settings** configured for the **JayTech Ltd** environment.

<img width="1918" height="915" alt="04 – Configuring Microsoft Entra Device Settings" src="https://github.com/user-attachments/assets/dc7ffb9c-17b7-4159-9cff-c23d2df4e3c5" />

# Task 4 - Creating and Managing a Microsoft Entra ID Security Group

## Objective

Create an **assigned security group** in **Microsoft Entra ID** and add the appropriate user as a member to support group-based access and future **Microsoft Intune** policy assignments.

---

## Implementation

I created a new **Security** group named **IT Department** within the **JayTech Ltd** Microsoft Entra ID environment and configured the membership type as **Assigned**.

I assigned **Jude Willmer** as the group owner and manually added **Hardy Souza** as a member of the group. This provides a central method of grouping IT department users rather than managing access and future policy assignments individually.

Using security groups in this way will also allow the **IT Department** group to be used for targeted **Microsoft Intune** configurations and application deployments later in the environment.

---

## Navigation

```text
Microsoft Entra Admin Center
→ Entra ID
→ Groups
→ All groups
→ New group
→ Group type: Security
→ Group name: IT Department
→ Membership type: Assigned
→ Add Owner
→ Select Jude Willmer
→ Add Members
→ Select Hardy Souza
→ Select
→ Create
```

---

## Outcome

The **IT Department** security group was successfully created in **Microsoft Entra ID** with **Assigned** membership. **Jude Willmer** was configured as the group owner and **Hardy Souza** was assigned as a member, establishing a group that can be used for centralised access management and future **Microsoft Intune** targeting.

---

## Screenshot

**Figure 5:** **Hardy Souza** selected as a member of the **IT Department** security group during group creation.

<img width="1919" height="915" alt="05 – Creating and Managing a Microsoft Entra ID Security Group" src="https://github.com/user-attachments/assets/e266a37b-c635-4590-84dd-7874d860fbe5" />

**Figure 6:** The **IT Department** security group successfully created in **Microsoft Entra ID** with the membership type set to **Assigned**.

<img width="1919" height="912" alt="06 – Creating and Managing a Microsoft Entra ID Security Group" src="https://github.com/user-attachments/assets/6268728c-314e-4889-a31a-f65449ba8c0a" />

# Task 5 - Creating a Dynamic Security Group

## Objective

Create a **dynamic security group** in **Microsoft Entra ID** that automatically manages membership based on a user's **department** attribute.

---

## Implementation

I created a **Security** group named **IT Department - Dynamic** and configured the membership type as **Dynamic User**.

I then created a **dynamic membership rule** using the **department** attribute. The rule automatically includes users whose department is set to **IT**, removing the need to manually add eligible users to the group.

The dynamic membership rule used was:

```text
(user.department -eq "IT")
```

This provides a more automated approach to group management, as membership can update based on changes made to user attributes within **Microsoft Entra ID**.

---

## Navigation

```text
Microsoft Entra Admin Center
→ Entra ID
→ Groups
→ All groups
→ New group
→ Group type: Security
→ Group name: IT Department - Dynamic
→ Membership type: Dynamic User
→ Add Owner
→ Select Jude Willmer
→ Edit dynamic query
→ Property: department
→ Operator: Equals
→ Value: IT
→ Save
→ Create
```

---

## Outcome

The **IT Department - Dynamic** security group was successfully created with **Dynamic User** membership. Users whose **department** attribute is set to **IT** can now be automatically included in the group through the configured **dynamic membership rule**, reducing the need for manual membership management.

---

## Screenshot

**Figure 1:** Creating the **IT Department - Dynamic** security group with **Dynamic User** membership in **Microsoft Entra ID**.

<img width="1919" height="912" alt="07 – Creating a Dynamic Security Group" src="https://github.com/user-attachments/assets/04a0d1d0-1c39-429d-814e-372df4f728bb" />

**Figure 2:** Configuring the **dynamic membership rule** to automatically include users whose **department** equals **IT**.

<img width="1918" height="914" alt="08 – Creating a Dynamic Security Group" src="https://github.com/user-attachments/assets/e06245d0-a8cd-4654-a3d0-8d805872316f" />

# Task 6 - Enrolling a Windows 10 Pro Device into Microsoft Intune

## Objective

Enrol a **Windows 10 Pro device** into **Microsoft Intune** using a standard user account and verify that the endpoint is successfully managed through the **Microsoft Intune Admin Center**.

---

## Implementation

I configured **automatic MDM enrolment** in Microsoft Intune for the **IT Department** security group, allowing targeted users to enrol Windows devices for centralised management. On the Windows 10 Pro virtual machine **CLIENT01**, I connected the Microsoft Entra ID account for **Hardy Souza** through **Access work or school**, successfully enrolling the endpoint with Microsoft Intune.

I verified the enrolment through the **Microsoft Intune Admin Center**, where **CLIENT01** appeared as an Intune-managed device with **Hardy Souza** listed as the primary user. The device also reported a **Compliant** status, confirming that the endpoint was successfully enrolled and communicating with Microsoft Intune.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Devices
→ Enrollment
→ Windows
→ Automatic Enrollment
→ MDM user scope: Some
→ Select group: IT Department
→ Save

Windows 10 Pro - CLIENT01
→ Settings
→ Accounts
→ Access work or school
→ Connect
→ Enter Hardy Souza's Microsoft Entra ID account
→ Complete connection

Microsoft Intune Admin Center
→ Devices
→ All devices
→ CLIENT01
→ Verify Intune management and compliance status
```

---

## Outcome

The **CLIENT01** Windows 10 Pro endpoint was successfully enrolled into **Microsoft Intune**, with **Hardy Souza** associated as the primary user and the device reporting a **Compliant** status. This confirmed successful Windows endpoint onboarding and demonstrated that CLIENT01 was communicating with and centrally managed through Microsoft Intune.

---

## Screenshot

**Figure 1:** Windows 10 Pro **Access work or school** showing **Hardy Souza's Microsoft Entra ID work account successfully connected** to CLIENT01.

<img width="1919" height="914" alt="09 – Enrolling a Windows 10 Pro Device into Microsoft Intune" src="https://github.com/user-attachments/assets/1d88a524-8542-441f-beb3-e1e64d8ba544" />

**Figure 2:** **Microsoft Intune Admin Center > Devices > All devices** showing **CLIENT01** successfully enrolled, **managed by Intune**, associated with **Hardy Souza**, and reporting a **Compliant** status.

<img width="1919" height="914" alt="10 – Enrolling a Windows 10 Pro Device into Microsoft Intune" src="https://github.com/user-attachments/assets/f9be9576-e471-4050-958f-0ff070c53a86" />
