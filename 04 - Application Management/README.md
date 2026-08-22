# Application Management

## Overview

This section covers the core **application management** tasks I completed within the **Microsoft Intune Administration Lab**. I deployed a **Microsoft Store application** to managed Windows devices and packaged and deployed a traditional **Win32 application** using the **Microsoft Win32 Content Prep Tool**, with application targeting and assignments used to control software distribution across enrolled endpoints.

These tasks demonstrate practical **IT Support** skills involving **application deployment**, **Microsoft Store app management**, **Win32 application packaging**, **device group targeting**, **application assignments**, and monitoring software installation through **Microsoft Intune**.

---

# Task 1 - Deploying Adobe Acrobat Reader to Managed Windows Devices

## Objective

Deploy **Adobe Acrobat Reader DC** to managed Windows devices through **Microsoft Intune** using the **Microsoft Store app (new)** deployment method, assign the application as **Required** to the appropriate Windows device group, and verify successful installation on the targeted endpoint.

---

## Implementation

I added **Adobe Acrobat Reader DC** to **Microsoft Intune** using the **Microsoft Store app (new)** application type. The application was configured as a **Required** deployment and assigned to the **Windows Devices** group, allowing Intune to centrally deploy the application to managed Windows endpoints.

After creating the application assignment, I manually synchronised the managed **CLIENT01** device through **Access work or school** to retrieve the latest Intune configuration. The deployment was then monitored through Intune, confirming that **Adobe Acrobat Reader DC** had been successfully installed on the targeted device.

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

**Adobe Acrobat Reader DC** was successfully deployed through **Microsoft Intune** as a required Microsoft Store application. The deployment reported **Installed: 1** with **0 failed installations**, demonstrating centralised application assignment, device synchronisation, and successful software delivery to a managed Windows endpoint.

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

I packaged **7-Zip 26.02 (x64 edition)** for deployment through **Microsoft Intune** using the **Microsoft Win32 Content Prep Tool**, converting the MSI installation source into the required **`.intunewin`** format. The packaged application was then added to Intune as a **Windows app (Win32)** and configured with an **MSI-based detection rule** so that Intune could reliably determine whether the application was installed.

I assigned the application as **Required** to the **Windows Devices** group and manually synchronised the managed **CLIENT01** device through **Access work or school** to retrieve the new application assignment. Intune monitoring was then used to verify the deployment and confirm successful installation.

---

## Navigation

```text
Prepare Win32 Application Package
→ Create working folders:
   → IntuneApps
      → 7Zip
      → Output
      → Tool
→ Place 7-Zip 26.02 (x64 edition) MSI installer in 7Zip folder
→ Place Microsoft Win32 Content Prep Tool in Tool folder
→ Open Command Prompt
→ Run IntuneWinAppUtil.exe
→ Source folder: 7Zip
→ Setup file: 7z2602-x64.msi
→ Output folder: Output
→ Create 7z2602-x64.intunewin

Microsoft Intune Admin Center
→ Apps
→ All Apps
→ Create
→ App type: Windows app (Win32)
→ Upload: 7z2602-x64.intunewin
→ App information
→ Name: 7-Zip 26.02 (x64 edition)
→ Publisher: Igor Pavlov
→ Category: Business
→ Program
→ Configure installation and uninstall commands
→ Requirements
→ Configure Windows requirements
→ Detection rules
→ Manually configure detection rules
→ Rule type: MSI
→ Assignments
→ Required
→ Windows Devices
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

**7-Zip 26.02 (x64 edition)** was successfully packaged, deployed, and detected as a **Win32 application** through **Microsoft Intune**. The final deployment status reported **Installed: 1** with **0 failed installations**, demonstrating the complete process of packaging a traditional Windows application, configuring detection, assigning it to managed devices, synchronising the endpoint, and verifying successful deployment.

---

## Screenshot

**Figure 1:** Microsoft Intune showing the **7z2602-x64.intunewin** application package successfully recognised as **7-Zip 26.02 (x64 edition)** for deployment as a Windows Win32 application.

<img width="1919" height="915" alt="04 – Deploying a Win32 Application Using Microsoft Intune" src="https://github.com/user-attachments/assets/0c98b9c9-269c-4041-89bd-96ba1823b833" />

**Figure 2:** Microsoft Intune showing **7-Zip 26.02 (x64 edition)** assigned as a **Required** application to the **Windows Devices** group, with availability and installation configured for **as soon as possible**.

<img width="1919" height="913" alt="05 – Deploying a Win32 Application Using Microsoft Intune" src="https://github.com/user-attachments/assets/6b0fe5c3-1149-4a6c-8c1d-6e678b5e2a9d" />

**Figure 3:** Microsoft Intune showing the successfully deployed **7-Zip 26.02 (x64 edition)** Win32 application, with **Assigned: Yes**, the **7z2602-x64.intunewin** application package, and a device installation status of **Installed: 1**, with **0 failed** installations.

<img width="1918" height="914" alt="06 – Deploying a Win32 Application Using Microsoft Intune" src="https://github.com/user-attachments/assets/d06c345c-6209-406a-b5de-f48b30ed61fb" />
