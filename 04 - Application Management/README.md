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

# Task 2 - Deploying a Win32 Application Using Microsoft Intune

## Objective

Package and deploy a traditional **Windows application as a Win32 app** through **Microsoft Intune**, demonstrating the complete application deployment process including `.intunewin` packaging, application configuration, detection rules, device assignment, synchronisation, and successful installation verification.

---

## Implementation

I downloaded the **7-Zip 26.02 (x64 edition)** MSI installer and used the **Microsoft Win32 Content Prep Tool (IntuneWinAppUtil.exe)** to package the installation source into the required **`.intunewin` format**. The resulting **7z2602-x64.intunewin** package was then uploaded to Microsoft Intune as a **Windows app (Win32)**. Within the application configuration, I defined the application information, selected **Business** as the category, configured the installation requirements, and used an **MSI detection rule** based on the application's product code so that Intune could determine whether 7-Zip was successfully installed.

The application was assigned as **Required** to the **Windows Devices** group with installation configured **as soon as possible**. After creating the application, I manually synchronised the managed **CLIENT01** Windows device through **Access work or school** to accelerate retrieval of the new Intune assignment. The deployment was then verified from the 7-Zip application overview in Intune, where the device installation status reported **Installed: 1**, with **0 failed**, **0 pending**, and **0 not applicable** installations.

---

## Navigation

```text
Prepare Win32 Application Package
→ Download 7-Zip 26.02 (x64 edition) MSI installer
→ Download Microsoft Win32 Content Prep Tool
→ Create working folders:
   → IntuneApps
      → 7Zip
      → Output
      → Tool
→ Place 7-Zip MSI installer in 7Zip folder
→ Run IntuneWinAppUtil.exe
→ Source folder: 7Zip
→ Setup file: 7z2602-x64.msi
→ Output folder: Output
→ Create 7z2602-x64.intunewin

Microsoft Intune Admin Center
→ Apps
→ All Apps
→ Create
→ Platform: Windows
→ App type: Windows app (Win32)
→ Select
→ Select app package file
→ Upload: 7z2602-x64.intunewin
→ App information
→ Name: 7-Zip 26.02 (x64 edition)
→ Publisher: Igor Pavlov
→ App Version: 26.02.00.0
→ Category: Business
→ Show this as a featured app: No
→ Next
→ Program
→ Configure installation and uninstall commands
→ Next
→ Requirements
→ Configure Windows requirements
→ Next
→ Detection rules
→ Rules format: Manually configure detection rules
→ Add
→ Rule type: MSI
→ MSI product code: {23170F69-40C1-2702-2602-000001000000}
→ MSI product version check: No
→ OK
→ Dependencies
→ No dependencies configured
→ Supersedence
→ No supersedence configured
→ Assignments
→ Required
→ Included: Windows Devices
→ Status: Active
→ Availability: As soon as possible
→ Installation deadline: As soon as possible
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
→ 7-Zip 26.02 (x64 edition)
→ Overview
→ Device status
→ Installed: 1
→ Not Installed: 0
→ Failed: 0
→ Install Pending: 0
→ Not Applicable: 0
```

---

## Outcome

The **7-Zip 26.02 (x64 edition)** application was successfully packaged into the **`.intunewin` format**, uploaded to Microsoft Intune as a **Windows Win32 application**, configured with an MSI-based detection rule, and assigned as a required application to the **Windows Devices** group. Following a manual synchronisation of **CLIENT01**, Intune successfully deployed and detected the application, with the final monitoring status showing **Installed: 1 and Failed: 0**. This demonstrates an end-to-end enterprise Win32 application deployment workflow using Microsoft Intune, from application packaging and detection configuration through to assignment, device synchronisation, and successful installation verification.

---

## Screenshot

**Figure 1:** Microsoft Intune showing the **7z2602-x64.intunewin** application package successfully recognised as **7-Zip 26.02 (x64 edition)** for deployment as a Windows Win32 application.

<img width="1919" height="915" alt="04 – Deploying a Win32 Application Using Microsoft Intune" src="https://github.com/user-attachments/assets/0c98b9c9-269c-4041-89bd-96ba1823b833" />

**Figure 2:** Microsoft Intune showing **7-Zip 26.02 (x64 edition)** assigned as a **Required** application to the **Windows Devices** group, with availability and installation configured for **as soon as possible**.

<img width="1919" height="913" alt="05 – Deploying a Win32 Application Using Microsoft Intune" src="https://github.com/user-attachments/assets/6b0fe5c3-1149-4a6c-8c1d-6e678b5e2a9d" />

**Figure 3:** Microsoft Intune showing the successfully deployed **7-Zip 26.02 (x64 edition)** Win32 application, with **Assigned: Yes**, the **7z2602-x64.intunewin** application package, and a device installation status of **Installed: 1**, with **0 failed** installations.

<img width="1918" height="914" alt="06 – Deploying a Win32 Application Using Microsoft Intune" src="https://github.com/user-attachments/assets/d06c345c-6209-406a-b5de-f48b30ed61fb" />
