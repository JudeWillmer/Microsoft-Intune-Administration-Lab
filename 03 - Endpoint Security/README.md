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
