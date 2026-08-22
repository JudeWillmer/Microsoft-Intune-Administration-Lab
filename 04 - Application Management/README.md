# Application Management

## Overview

This section covers the core **application management** tasks I completed within the **Microsoft Intune Administration Lab**. I deployed a **Microsoft Store application** to managed Windows devices and configured **application targeting and assignments** to control how approved software is distributed across enrolled endpoints.

These tasks demonstrate practical **IT Support** skills involving **application deployment**, **Microsoft Store app management**, **device group targeting**, **application assignments**, and monitoring software installation through **Microsoft Intune**.

---

# Task 1 - Deploying Adobe Acrobat Reader to Managed Windows Devices

## Objective

Deploy **Adobe Acrobat Reader DC** to managed Windows devices through **Microsoft Intune** using the **Microsoft Store app (new)** deployment method, assign the application as **Required** to the appropriate Windows device group, and verify successful installation on the targeted endpoint.

---

## Implementation

I added **Adobe Acrobat Reader DC** to Microsoft Intune as a **Microsoft Store app (new)** and reviewed the automatically populated application information, including the publisher, package identifier, and system installation behaviour. This provides a centrally managed method of deploying a standard business application without requiring users to manually locate and install the software.

I configured the application as **Required** for the **Windows Devices** group, causing Intune to automatically deploy the application to targeted managed devices. After creating the deployment, I initiated a manual **Sync** from the **Access work or school** settings on **CLIENT01** to trigger communication with Microsoft Intune and accelerate policy and application retrieval. I then monitored the deployment from the Intune admin center and confirmed that Adobe Acrobat Reader DC successfully installed on the targeted device.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Apps
→ All Apps
→ Create
→ Platform: Windows
→ App type: Microsoft Store app (new)
→ Select
→ Search the Microsoft Store app (new)
→ Search: Adobe Acrobat Reader
→ Select: Adobe Acrobat Reader DC
→ App information
→ Review application information
→ Install behavior: System
→ Next
→ Assignments
→ Required
→ Add group
→ Windows Devices
→ Included
→ Next
→ Review + create
→ Create

CLIENT01
→ Settings
→ Accounts
→ Access work or school
→ Workplace or school account
→ Info
→ Managed by JayTech
→ Sync

Microsoft Intune Admin Center
→ Apps
→ All Apps
→ Adobe Acrobat Reader DC
→ Overview
→ Device status
→ Installed: 1
→ Failed: 0
→ Install Pending: 0
```

---

## Outcome

**Adobe Acrobat Reader DC** was successfully deployed through Microsoft Intune as a **required application** to the **Windows Devices** group. Following a manual Intune sync from **CLIENT01**, the application deployment completed successfully and Intune reported **Installed: 1**, with **0 failed** and **0 pending** installations. This demonstrates centralised Windows application deployment, group-based targeting, endpoint synchronisation, and deployment-status monitoring through Microsoft Intune.

---

## Screenshot

**Figure 1:** Microsoft Intune showing the **Adobe Acrobat Reader DC** Microsoft Store application information used to configure the Windows application deployment.

<img width="1919" height="914" alt="01 – Deploying Adobe Acrobat Reader to Managed Windows Devices" src="https://github.com/user-attachments/assets/de173a65-3851-4392-af0b-3a1da204d0c3" />

**Figure 2:** The application **Assignments** configuration showing **Windows Devices** included under **Required**, ensuring the application is automatically deployed to targeted managed Windows devices.

<img width="1919" height="914" alt="02 – Deploying Adobe Acrobat Reader to Managed Windows Devices" src="https://github.com/user-attachments/assets/686e4417-d49f-4a4d-b80b-8de65519a3f9" />

**Figure 3:** The **Adobe Acrobat Reader DC** Overview showing **Installed: 1**, **Failed: 0**, and **Install Pending: 0**, confirming successful deployment to the targeted managed device.

<img width="1919" height="912" alt="03 – Deploying Adobe Acrobat Reader to Managed Windows Devices" src="https://github.com/user-attachments/assets/f4d389c3-804b-48d0-91d3-7efbb41da5cb" />
