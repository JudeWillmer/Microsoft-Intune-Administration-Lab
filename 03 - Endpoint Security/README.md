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

I created the **Windows - Microsoft Defender Antivirus** endpoint security policy in Microsoft Intune to strengthen malware protection across managed Windows endpoints. The policy enabled key Defender capabilities including archive scanning, behaviour monitoring, cloud protection, email scanning, removable-drive scanning, downloaded file and attachment scanning, real-time monitoring, and script scanning.

Settings outside the requirements of this endpoint protection configuration, including specialised network, server, threat remediation, and deprecated controls, were left as **Not configured**. After reviewing the selected protections, I created the policy within Microsoft Intune.

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

The **Windows - Microsoft Defender Antivirus** policy was successfully created in **Microsoft Intune**, establishing centrally managed protection across Windows endpoints through **real-time monitoring**, **cloud protection**, **behaviour monitoring**, and multiple scanning controls. This provides a consistent antivirus security baseline that can be centrally managed through Microsoft Intune.

---

## Screenshots

**Figure 1:** The BitLocker policy configuration showing **Require Device Encryption: Enabled** and **XTS-AES 256-bit** configured for operating system, fixed data, and removable data drives.

<img width="1919" height="913" alt="04 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/76a1c376-ce51-40a9-9372-e9f79405b78f" />

**Figure 2:** The **Operating System Drives** configuration showing drive encryption enforcement enabled and the encryption type configured as **Full encryption**.

<img width="1919" height="914" alt="05 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/a3319925-a767-437f-bd3e-bbdd075f1255" />

**Figure 3:** The **Review + create** summary confirming the completed **Windows - BitLocker Disk Encryption** policy, including device encryption, **XTS-AES 256-bit** encryption, **Full encryption**, and BitLocker operating system drive recovery settings.

<img width="1919" height="914" alt="06 – Configuring BitLocker Disk Encryption in Microsoft Intune" src="https://github.com/user-attachments/assets/e7e47f0a-c8a2-499b-ad2e-a17602f3d21e" />
