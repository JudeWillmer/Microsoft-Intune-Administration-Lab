# Device Configuration and Compliance

## Overview

This section covers the core **device configuration and compliance** tasks I completed within the **Microsoft Intune Administration Lab**. I created and assigned a **Windows configuration profile**, verified that the configured settings were successfully deployed to a managed endpoint, created a **Windows compliance policy**, and reviewed the device's compliance status within **Microsoft Intune**.

These tasks demonstrate practical **IT Support** skills involving centralised device configuration, policy deployment, endpoint compliance, device monitoring, and verifying that managed Windows devices meet organisational requirements.

---

# Task 1 - Creating a Windows Device Configuration Profile

## Objective

Create and assign a **Windows configuration profile** in **Microsoft Intune** to centrally manage Microsoft Edge settings on managed Windows devices.

---

## Implementation

I created a **Settings Catalog** configuration profile named **Windows 10-11 - User Experience Configuration** for **Windows 10 and later** devices.

Within the **Microsoft Edge** settings, I enabled the **Favorites Bar** and configured a managed favourites folder named **JayTech Resources** containing links to commonly used Microsoft resources.

The managed favourites configuration used was:

```json
[
  {
    "toplevel_name": "JayTech Resources"
  },
  {
    "name": "Microsoft 365",
    "url": "https://www.microsoft365.com/"
  },
  {
    "name": "Microsoft Intune",
    "url": "https://intune.microsoft.com/"
  },
  {
    "name": "Microsoft Entra",
    "url": "https://entra.microsoft.com/"
  }
]
```

The profile was assigned to the **Windows Devices** security group so that the configuration could be centrally applied to the managed Windows endpoint.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Devices
→ Configuration
→ Create
→ New policy
→ Platform: Windows 10 and later
→ Profile type: Settings catalog
→ Microsoft Edge
→ Enable favorites bar: Enabled
→ Configure favorites: Enabled
→ Add managed favourites
→ Assignments
→ Windows Devices
→ Review + create
→ Create
```

---

## Outcome

The **Windows 10-11 - User Experience Configuration** profile was successfully created and assigned to the **Windows Devices** group in Microsoft Intune, providing a centralised method of managing Microsoft Edge settings across targeted Windows endpoints.

---

## Screenshots

**Figure 1:** Configuring the **Microsoft Edge Favorites Bar** and **JayTech Resources** managed favourites within the Windows Settings Catalog profile.

<img width="1919" height="914" alt="01 – Creating a Windows Device Configuration Profile" src="https://github.com/user-attachments/assets/d298f699-bdc9-4277-89ab-7ea87fa33ca7" />

**Figure 2:** The completed **Windows 10-11 - User Experience Configuration** profile displayed in **Microsoft Intune**.

<img width="1919" height="913" alt="02 – Creating a Windows Device Configuration Profile" src="https://github.com/user-attachments/assets/7ff2bcfa-0823-4e86-9cb2-5cea18da32b1" />
