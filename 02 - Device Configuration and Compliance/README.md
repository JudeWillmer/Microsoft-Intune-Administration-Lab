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

I created the **Windows 10-11 - User Experience Configuration** profile using the **Settings Catalog** in Microsoft Intune and configured Microsoft Edge settings for managed Windows endpoints. The profile enabled the **Favorites Bar** and deployed a centrally managed favourites folder named **JayTech Resources**.

The managed favourites provided users with predefined shortcuts to **Microsoft 365**, **Microsoft Intune**, and **Microsoft Entra**, demonstrating how Intune can standardise browser resources across managed devices. The profile was assigned to the **Windows Devices** security group for deployment to the managed endpoint.

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

## Screenshot

**Figure 1:** Configuring the **Microsoft Edge Favorites Bar** and **JayTech Resources** managed favourites within the Windows Settings Catalog profile.

<img width="1919" height="914" alt="01 – Creating a Windows Device Configuration Profile" src="https://github.com/user-attachments/assets/d298f699-bdc9-4277-89ab-7ea87fa33ca7" />

**Figure 2:** The completed **Windows 10-11 - User Experience Configuration** profile displayed in **Microsoft Intune**.

<img width="1919" height="913" alt="02 – Creating a Windows Device Configuration Profile" src="https://github.com/user-attachments/assets/7ff2bcfa-0823-4e86-9cb2-5cea18da32b1" />

# Task 2 - Verifying Intune Policy Deployment on CLIENT01

## Objective

Verify that the **Windows 10-11 - User Experience Configuration** profile was successfully deployed from **Microsoft Intune** to **CLIENT01**, and confirm that the managed **Microsoft Edge favourites** were applied to the endpoint.

---

## Implementation

After creating and assigning the **Windows 10-11 - User Experience Configuration** profile, I manually synchronised **CLIENT01** with Microsoft Intune and confirmed that the endpoint displayed **Managed by JayTech**. I then opened **Microsoft Edge** and verified that the managed favourites had been deployed successfully, including the **JayTech Resources** folder and Microsoft 365 shortcut.

I reviewed the configuration profile within the **Microsoft Intune Admin Center**, where the deployment reported **Succeeded: 1** with **0 errors** and **0 conflicts**. I also confirmed that **Configure favorites** and **Enable favorites bar** were enabled, verifying that the configuration had been successfully deployed and applied to CLIENT01.

---

## Navigation

```text
CLIENT01
→ Settings
→ Accounts
→ Access work or school
→ Workplace or school account
→ Info
→ Managed by JayTech
→ Sync

Microsoft Edge
→ Verify JayTech Resources managed favourites

Microsoft Intune Admin Center
→ Devices
→ Configuration
→ Windows 10-11 - User Experience Configuration
→ Device and user check-in status
→ Verify Succeeded: 1
→ Configuration settings
→ Microsoft Edge
→ Configure favorites: Enabled
→ Enable favorites bar: Enabled
```

---

## Outcome

The **Windows 10-11 - User Experience Configuration** profile was successfully deployed and applied to **CLIENT01**, with the managed Microsoft Edge favourites appearing on the endpoint and Intune reporting **Succeeded: 1** with **0 errors** and **0 conflicts**. This confirmed the complete configuration workflow from **central policy creation and assignment** through to successful deployment and application on the managed Windows device.

---

## Screenshot

**Figure 1:** CLIENT01 displaying **Managed by JayTech** and confirming that the Microsoft Intune device synchronisation completed successfully.

<img width="1919" height="911" alt="03 – Verifying Intune Policy Deployment on CLIENT01" src="https://github.com/user-attachments/assets/25e04d20-aac9-46c2-a4b3-ba0dbfc3450b" />

**Figure 2:** The **Windows 10-11 - User Experience Configuration** profile reporting **Succeeded: 1**, with **0 errors** and **0 conflicts**. The deployed managed favourites are also visible in Microsoft Edge on CLIENT01.

<img width="1919" height="913" alt="04 – Verifying Intune Policy Deployment on CLIENT01" src="https://github.com/user-attachments/assets/d88f9e33-b3ff-4b4d-9a98-be2386be2f8b" />

**Figure 3:** The deployed Microsoft Edge configuration in Microsoft Intune showing **Configure favorites: Enabled**, the **JayTech Resources** managed favourites configuration, and **Enable favorites bar: Enabled**.

<img width="1919" height="914" alt="05 – Verifying Intune Policy Deployment on CLIENT01" src="https://github.com/user-attachments/assets/d79d055f-24bc-4f56-a704-163d723b0f91" />

# Task 3 - Creating and Verifying a Windows Compliance Policy

## Objective

Create and assign a **Windows 10/11 compliance policy** in **Microsoft Intune**, evaluate **CLIENT01** against the configured security requirements, and verify the device's final **compliance state**.

---

## Implementation

I created the **Windows 10-11 - Compliance Policy** in Microsoft Intune to evaluate managed Windows endpoints against defined **device health** and **system security** requirements. The policy required **Secure Boot**, **code integrity**, **Firewall**, **Antivirus**, **Antispyware**, and key **Microsoft Defender** protections, while storage encryption was left as **Not configured** for compatibility with the virtualised lab endpoint.

I configured noncompliant devices to be marked **Immediately (0 days)** and assigned the policy to the **Windows Devices** group containing **CLIENT01**. After deployment, I synchronised CLIENT01 with Microsoft Intune to trigger policy evaluation and verify its compliance state.

---

## Navigation

```
Microsoft Intune Admin Center
→ Devices
→ Compliance
→ Policies
→ Create policy
→ Platform: Windows 10 and later
→ Profile type: Windows 10/11 compliance policy
→ Create
→ Basics
→ Compliance settings
→ Device Health
→ Secure Boot: Require
→ Code integrity: Require
→ System Security
→ Firewall: Require
→ Antivirus: Require
→ Antispyware: Require
→ Microsoft Defender Antimalware: Require
→ Microsoft Defender Antimalware security intelligence up-to-date: Require
→ Real-time protection: Require
→ Actions for noncompliance
→ Mark device noncompliant: Immediately (0 days)
→ Assignments
→ Windows Devices
→ Review + create
→ Create
```

---

## Outcome

The **Windows 10-11 - Compliance Policy** was successfully created and assigned to the **Windows Devices** group. Following synchronisation and policy evaluation, **CLIENT01 reported a Compliant policy state**, confirming that the device met the configured Windows security and Microsoft Defender compliance requirements.

---

## Screenshot

**Figure 1:** **Device Health** compliance settings requiring **Secure Boot** and **Code integrity**.

<img width="1919" height="913" alt="06 – Creating and Verifying a Windows Compliance Policy" src="https://github.com/user-attachments/assets/013bd6a4-4c9a-4a3d-9f50-79c4a1b9cda0" />

**Figure 2:** **System Security** and **Microsoft Defender** compliance requirements configured for the Windows endpoint.

<img width="1919" height="914" alt="07 – Creating and Verifying a Windows Compliance Policy" src="https://github.com/user-attachments/assets/b57f4a6b-86a6-4af0-9050-7acfa49c534b" />

**Figure 3:** **Windows 10-11 - Compliance Policy** assigned to the **Windows Devices** group containing the managed device.

<img width="1919" height="913" alt="08 – Creating and Verifying a Windows Compliance Policy" src="https://github.com/user-attachments/assets/d4749d92-5ea6-4065-9fb3-70af8616f4e8" />

**Figure 4:** Final Microsoft Intune compliance evaluation showing **CLIENT01** with a green **Compliant** policy state.

<img width="1919" height="915" alt="09 – Creating and Verifying a Windows Compliance Policy" src="https://github.com/user-attachments/assets/e3a0e95c-bc21-426f-895c-41f9bd636085" />
