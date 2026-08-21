# Endpoint Security

## Overview

This section covers the core **endpoint security** tasks I completed within the **Microsoft Intune Administration Lab**. I created and configured a **Microsoft Defender Antivirus policy**, implemented **BitLocker drive encryption**, and applied **device control restrictions** to protect managed Windows endpoints from malware, unauthorised access, and removable-storage threats.

These tasks demonstrate practical **IT Support** skills involving **endpoint protection**, **antivirus configuration**, **disk encryption**, **device control**, and centrally managing Windows security policies through **Microsoft Intune**.

---

# Task 1 - Creating a Microsoft Defender Antivirus Policy

## Objective

Create a **Microsoft Defender Antivirus policy** in **Microsoft Intune** to centrally configure antivirus protection settings for managed Windows devices and establish a consistent endpoint protection baseline.

---

## Implementation

I navigated to **Endpoint security > Antivirus** within the **Microsoft Intune Admin Center** and created a new endpoint security policy using the **Windows** platform and **Microsoft Defender Antivirus** profile.

I created the policy with the name **Windows - Microsoft Defender Antivirus** and configured key Microsoft Defender protections for managed Windows endpoints.

The policy was configured to enable **archive scanning**, **behaviour monitoring**, **cloud protection**, **email scanning**, **removable-drive scanning**, **downloaded file and attachment scanning**, **real-time monitoring**, and **script scanning**.

Settings that were not required for the endpoint protection baseline, including specialised network, server, threat remediation, and deprecated controls, were left as **Not configured**.

After reviewing the configured settings, I created the **Windows - Microsoft Defender Antivirus** policy within Microsoft Intune.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Endpoint security
→ Antivirus
→ Create Policy
→ Platform: Windows
→ Profile: Microsoft Defender Antivirus
→ Create
→ Basics
→ Name: Windows - Microsoft Defender Antivirus
→ Configuration settings
→ Defender
→ Allow Archive Scanning: Allowed
→ Allow Behavior Monitoring: Allowed
→ Allow Cloud Protection: Allowed
→ Allow Email Scanning: Allowed
→ Allow Full Scan Removable Drive Scanning: Allowed
→ Allow scanning of all downloaded files and attachments: Allowed
→ Allow Realtime Monitoring: Allowed
→ Allow Script Scanning: Allowed
→ Scope tags
→ Assignments
→ Review + create
→ Create
```

---

## Outcome

The **Windows - Microsoft Defender Antivirus** policy was successfully created within **Microsoft Intune**.

The policy establishes centrally managed antivirus protection settings including **real-time monitoring**, **behaviour monitoring**, **cloud protection**, and scanning of potentially malicious content such as **email, archives, removable drives, scripts, downloaded files, and attachments**.

This provides a centralised method of managing **Microsoft Defender Antivirus** protection settings across managed Windows endpoints.

---

## Screenshots

**Figure 1:** Creating a new endpoint security policy using the **Windows** platform and **Microsoft Defender Antivirus** profile.

<img width="1918" height="912" alt="01 – Creating a Microsoft Defender Antivirus Policy" src="https://github.com/user-attachments/assets/23bcb206-277f-4b24-af83-cc8dcc2c4e0a" />

**Figure 2:** Configuring the core **Microsoft Defender Antivirus** protection settings, including **behaviour monitoring**, **cloud protection**, **removable-drive scanning**, **downloaded file scanning**, and **real-time monitoring**.

<img width="1918" height="913" alt="02 – Creating a Microsoft Defender Antivirus Policy" src="https://github.com/user-attachments/assets/1f6ac616-f54a-44c9-830c-6491831ab311" />

**Figure 3:** The completed **Windows - Microsoft Defender Antivirus** policy displayed within the **Microsoft Intune Admin Center**.

<img width="1919" height="912" alt="03 – Creating a Microsoft Defender Antivirus Policy" src="https://github.com/user-attachments/assets/6f1dda89-17fc-4df4-ae67-7bed219799c7" />

# Task 2 - Configuring BitLocker Disk Encryption in Microsoft Intune

## Objective

Create a **BitLocker disk encryption policy** in **Microsoft Intune** to strengthen data protection on managed Windows devices by requiring device encryption, applying **XTS-AES 256-bit** encryption, and enforcing **full encryption** on operating system drives.

---

## Implementation

I created a **Windows BitLocker policy** within Microsoft Intune Endpoint Security to centrally configure disk encryption requirements for managed Windows devices.

The policy was configured to require device encryption and use **XTS-AES 256-bit** as the encryption method for operating system drives, fixed data drives, and removable data drives.

For operating system drives, I enabled enforcement of the drive encryption type and configured **Full encryption**. This ensures that the entire operating system drive is protected rather than encrypting only used disk space.

I also enabled the configuration for recovering BitLocker-protected operating system drives, providing support for recovery scenarios where access to an encrypted device may need to be restored.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Endpoint security
→ Disk encryption
→ Create Policy
→ Platform: Windows
→ Profile: BitLocker
→ Create
→ Basics
→ Name: Windows - BitLocker Disk Encryption
→ Configuration settings
→ BitLocker
→ Require Device Encryption: Enabled
→ Allow Warning For Other Disk Encryption: Disabled
→ Allow Standard User Encryption: Disabled
→ BitLocker Drive Encryption
→ Choose drive encryption method and cipher strength: Enabled
→ Operating system drives: XTS-AES 256-bit
→ Fixed data drives: XTS-AES 256-bit
→ Removable data drives: XTS-AES 256-bit
→ Operating System Drives
→ Enforce drive encryption type on operating system drives: Enabled
→ Encryption type: Full encryption
→ Choose how BitLocker-protected operating system drives can be recovered: Enabled
→ Scope tags
→ Assignments
→ Review + create
→ Create
```

---

## Outcome

The **Windows - BitLocker Disk Encryption** policy was successfully created in Microsoft Intune with strengthened encryption requirements for managed Windows devices.

The policy requires device encryption, configures **XTS-AES 256-bit** encryption for operating system, fixed, and removable data drives, and enforces **Full encryption** for operating system drives.

This demonstrates practical endpoint security administration through the central configuration of **BitLocker encryption controls**, helping protect organisational data stored on managed Windows devices.

---

## Screenshots

**Figure 1:** The BitLocker policy configuration showing **Require Device Encryption: Enabled** and **XTS-AES 256-bit** configured for operating system, fixed data, and removable data drives.

<img width="1919" height="913" alt="04 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/680ad7cb-355b-4241-b880-c3932ad96fe2" />

**Figure 2:** The **Operating System Drives** configuration showing drive encryption enforcement enabled and the encryption type configured as **Full encryption**.

<img width="1919" height="914" alt="05 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/fd89931c-74e8-4697-a8e0-c8fa30a4784e" />

**Figure 3:** The **Review + create** summary confirming the completed **Windows - BitLocker Disk Encryption** policy, including device encryption, **XTS-AES 256-bit** encryption, **Full encryption**, and BitLocker operating system drive recovery settings.

<img width="1919" height="914" alt="06 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/152701a8-68a0-4ef7-81f7-179ead2d8a69" />
