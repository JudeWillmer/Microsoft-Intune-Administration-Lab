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

I created the **Windows - Microsoft Defender Antivirus** endpoint security policy in **Microsoft Intune** using the **Windows** platform and **Microsoft Defender Antivirus** profile. The policy was configured to provide centrally managed antivirus protection across managed Windows endpoints.

I enabled **archive scanning**, **behaviour monitoring**, **cloud protection**, **email scanning**, **removable-drive scanning**, **downloaded file and attachment scanning**, **real-time monitoring**, and **script scanning**. Settings outside the required endpoint protection baseline, including specialised network, server, threat remediation, and deprecated controls, were left as **Not configured**.

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

The **Windows - Microsoft Defender Antivirus** policy was successfully created within **Microsoft Intune**, establishing centrally managed antivirus protection across managed Windows endpoints. The policy provides key protections including **real-time monitoring**, **behaviour monitoring**, **cloud protection**, and scanning of potentially malicious content such as **email, archives, removable drives, scripts, downloaded files, and attachments**.

---

## Screenshot

**Figure 1:** Creating a new endpoint security policy using the **Windows** platform and **Microsoft Defender Antivirus** profile.

<img width="1918" height="912" alt="01 – Creating a Microsoft Defender Antivirus Policy" src="https://github.com/user-attachments/assets/11d1b8e2-815b-4075-9e85-d1029bf727de" />

**Figure 2:** Configuring the core **Microsoft Defender Antivirus** protection settings, including **behaviour monitoring**, **cloud protection**, **removable-drive scanning**, **downloaded file scanning**, and **real-time monitoring**.

<img width="1918" height="913" alt="02 – Creating a Microsoft Defender Antivirus Policy" src="https://github.com/user-attachments/assets/5a9a3267-3452-4509-8839-320c831c3cb3" />

**Figure 3:** The completed **Windows - Microsoft Defender Antivirus** policy displayed within the **Microsoft Intune Admin Center**.

<img width="1919" height="912" alt="03 – Creating a Microsoft Defender Antivirus Policy" src="https://github.com/user-attachments/assets/eb7980c7-aa55-47e5-a9ef-9600c20e289f" />

# Task 2 - Configuring BitLocker Disk Encryption in Microsoft Intune

## Objective

Create a **BitLocker disk encryption policy** in **Microsoft Intune** to strengthen data protection on managed Windows devices by requiring device encryption, applying **XTS-AES 256-bit** encryption, and enforcing **full encryption** on operating system drives.

---

## Implementation

I created the **Windows - BitLocker Disk Encryption** policy within **Microsoft Intune Endpoint Security** to centrally configure disk encryption requirements for managed Windows devices. The policy required device encryption and configured **XTS-AES 256-bit** encryption for operating system, fixed data, and removable data drives.

For operating system drives, I enforced **Full encryption** to protect the entire drive rather than only used disk space. I also enabled BitLocker operating system drive recovery configuration to support scenarios where access to an encrypted device may need to be restored.

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

The **Windows - BitLocker Disk Encryption** policy was successfully created in **Microsoft Intune**, requiring device encryption with **XTS-AES 256-bit** and enforcing **Full encryption** for operating system drives. This established centrally managed **BitLocker encryption controls** to strengthen the protection of organisational data stored on managed Windows devices.

---

## Screenshot

**Figure 1:** The BitLocker policy configuration showing **Require Device Encryption: Enabled** and **XTS-AES 256-bit** configured for operating system, fixed data, and removable data drives.

<img width="1919" height="913" alt="04 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/e349b3b9-8c27-4c2d-bd68-d7e80f7f49b1" />

**Figure 2:** The **Operating System Drives** configuration showing drive encryption enforcement enabled and the encryption type configured as **Full encryption**.

<img width="1919" height="914" alt="05 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/babecad1-5788-44b4-88c9-39455f421119" />

**Figure 3:** The **Review + create** summary confirming the completed **Windows - BitLocker Disk Encryption** policy, including device encryption, **XTS-AES 256-bit** encryption, **Full encryption**, and BitLocker operating system drive recovery settings.

<img width="1919" height="914" alt="06 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/7a82e3de-22d9-4202-a8c2-a4d4c522461f" />

# Task 3 - Creating a Removable Storage Device Control Policy

## Objective

Create a **Device Control policy** in **Microsoft Intune** to strengthen endpoint security by controlling removable storage devices, scanning removable drives for threats, and applying a **default deny enforcement** approach to reduce the risk posed by unauthorised removable media.

---

## Implementation

I created a new **Device Control** policy within **Endpoint security > Attack surface reduction**, using the **Windows** platform. The policy was named **Windows - Removable Storage Device Control** and was designed to strengthen the security of managed Windows devices against threats introduced through removable storage.

Within the Defender settings, I enabled **Device Control**, allowed **full scanning of removable drives**, and configured **Default Deny Enforcement**. This provides a restrictive security posture in which removable device access is denied by default unless explicitly permitted, while removable drives can also be scanned for potential malware and other threats.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Endpoint security
→ Attack surface reduction
→ Create Policy
→ Platform: Windows
→ Profile: Device Control
→ Create
→ Basics
→ Name: Windows - Removable Storage Device Control
→ Description: Configures removable storage and USB access restrictions for managed Windows devices.
→ Configuration settings
→ Defender
→ Device Control Enabled: Device Control is enabled
→ Allow Full Scan Removable Drive Scanning: Allowed. Scans removable drives.
→ Default Enforcement: Default Deny Enforcement
→ Secured Devices Configuration: Not configured
→ Scope tags
→ Assignments
→ Review + create
→ Create
```

---

## Outcome

The **Windows - Removable Storage Device Control** policy was successfully created in Microsoft Intune with **Device Control enabled**, removable-drive scanning permitted, and **Default Deny Enforcement** configured. This demonstrates the use of centralised endpoint security controls to reduce exposure to unauthorised removable media and help protect managed Windows devices from malware and other threats that could be introduced through removable storage.

---

## Screenshot

**Figure 1:** Microsoft Intune showing the creation of a new **Windows Device Control** profile under **Endpoint security > Attack surface reduction**.

<img width="1919" height="913" alt="07 – Creating a Removable Storage Device Control Policy" src="https://github.com/user-attachments/assets/0fd77b96-c900-4381-9862-d6e0cd3afea3" />

**Figure 2:** The Device Control policy configuration showing **Device Control is enabled**, **removable-drive scanning allowed**, and **Default Deny Enforcement** configured.

<img width="1919" height="913" alt="08 – Creating a Removable Storage Device Control Policy" src="https://github.com/user-attachments/assets/b0bcce29-b5ff-4eaf-b505-79c9fef52da5" />

**Figure 3:** Microsoft Intune showing the successfully created **Windows - Removable Storage Device Control** policy with the **Device Control** policy type and **Windows** platform.

<img width="1919" height="914" alt="09 – Creating a Removable Storage Device Control Policy" src="https://github.com/user-attachments/assets/10c93881-2656-481f-88ca-e62bf8d841e0" />
