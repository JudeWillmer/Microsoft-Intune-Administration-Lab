# Device Lifecycle and Troubleshooting

## Overview

This section covers the core **device lifecycle and troubleshooting** tasks I completed within the **Microsoft Intune Administration Lab**. I reviewed the **device decommissioning process** for a managed Windows endpoint and performed practical **troubleshooting and diagnostic tasks** across the Intune environment.

These tasks demonstrate practical **IT Support** skills involving **device lifecycle management**, **remote device actions**, **policy and compliance troubleshooting**, **application deployment troubleshooting**, **device synchronisation**, and investigating endpoint management issues through **Microsoft Intune**.

---

# Task 1 - Reviewing the Device Decommissioning Process in Microsoft Intune

## Objective

Review the **device decommissioning process** for the managed Windows endpoint **CLIENT01** using the remote **Wipe** action in **Microsoft Intune**, while preserving the device for the remaining troubleshooting tasks within the lab.

---

## Implementation

I reviewed the **device decommissioning workflow** for the managed Windows endpoint **CLIENT01** within Microsoft Intune. From the device overview, I accessed the remote **Wipe** action and reviewed the available factory reset options and their potential impact on the endpoint.

The final wipe command was intentionally **not executed**, as **CLIENT01** remained required for the troubleshooting and diagnostic tasks within the lab. This allowed the decommissioning procedure to be demonstrated and documented without removing the existing device configuration, applications, or management state.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Devices
→ All devices
→ CLIENT01
→ Overview
→ Wipe
→ Review Wipe device options
→ Cancel without executing the wipe
```

---

## Outcome

The **Microsoft Intune device wipe workflow** was successfully reviewed for **CLIENT01**, demonstrating how an administrator can remotely initiate a factory reset when decommissioning a managed Windows endpoint. The destructive action was intentionally **not executed**, preserving CLIENT01 and its existing configuration for the remaining troubleshooting and validation tasks within the lab.

---

## Screenshot

**Figure 1:** The **CLIENT01** device overview in Microsoft Intune showing the managed Windows endpoint and the available **Wipe** remote device action.

<img width="1919" height="914" alt="01 – Reviewing the Device Decommissioning Process in Microsoft Intune" src="https://github.com/user-attachments/assets/d1598bf7-315d-4a64-8ecf-5e2a65651ab8" />

**Figure 2:** The **Wipe device** confirmation screen showing the available factory reset options before execution. The final wipe command was intentionally not submitted to preserve CLIENT01 for further troubleshooting.

<img width="1919" height="914" alt="02 – Reviewing the Device Decommissioning Process in Microsoft Intune" src="https://github.com/user-attachments/assets/e0959b66-428d-4720-a93e-114e91a83ff8" />

# Task 1 - Troubleshooting an Intune Compliance Policy Error

## Objective

Investigate and resolve a **Microsoft Intune compliance policy error** affecting the managed **CLIENT01** Windows device by identifying the individual policy setting responsible for the failure, applying an appropriate remediation, and verifying that the device successfully returns to a compliant state.

---

## Implementation

I investigated an **Error** affecting **CLIENT01** under the **Windows 10-11 - Compliance Policy** in Microsoft Intune. Using the device compliance details, I reviewed the individual policy settings and isolated the issue to **Encryption of data storage on device**, which reported **2016281112 (Remediation failed)**, while the remaining applicable security controls were reporting as **Compliant**.

Because **CLIENT01** is a VirtualBox-based lab endpoint and device encryption was not required for this scenario, I edited the compliance policy and changed **Require encryption of data storage on device** to **Not configured**. The policy was then reevaluated to confirm whether the configuration change resolved the compliance error.

---

## Navigation

```text
Microsoft Intune Admin Center
→ Devices
→ Compliance
→ Windows 10-11 - Compliance Policy
→ Device status
→ CLIENT01
→ Policy compliance: Error

CLIENT01
→ Device compliance
→ Windows 10-11 - Compliance Policy
→ Review individual compliance settings
→ Encryption of data storage on device: Error
→ 2016281112 (Remediation failed)

Microsoft Intune Admin Center
→ Devices
→ Compliance
→ Windows 10-11 - Compliance Policy
→ Properties
→ Compliance settings
→ System Security
→ Encryption
→ Require encryption of data storage on device: Not configured
→ Review + save

Microsoft Intune Admin Center
→ Devices
→ Compliance
→ Windows 10-11 - Compliance Policy
→ Device status
→ CLIENT01
→ Policy compliance: Compliant
```

---

## Outcome

The **Windows 10-11 - Compliance Policy** error was successfully resolved after isolating the failure to the device encryption requirement and adjusting the setting for the lab environment. Following policy re-evaluation, **CLIENT01** changed from **Error** to **Compliant**, demonstrating the use of Intune's compliance reporting to identify a policy-level issue, apply targeted remediation, and verify successful resolution.

---

## Screenshot

**Figure 1:** Microsoft Intune showing **CLIENT01** reporting an **Error** against the **Windows 10-11 - Compliance Policy**, establishing the initial compliance issue.

<img width="1919" height="913" alt="03 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/9a9aef5a-7a49-4f40-b8dc-cb9fb25c0254" />

**Figure 2:** The **CLIENT01 Device compliance** view showing the **Default Device Compliance Policy** as **Compliant** while the custom **Windows 10-11 - Compliance Policy** reports an **Error**.

<img width="1918" height="916" alt="04 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/076d22fe-954e-4150-867b-091a5960b986" />

**Figure 3:** Detailed compliance results showing the applicable security controls reporting as **Compliant** while **Encryption of data storage on device** reports **Error — 2016281112 (Remediation failed)**, isolating the source of the compliance failure.

<img width="1919" height="913" alt="05 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/bc5893c9-adba-4ce8-82cc-2b71a9558d10" />

**Figure 4:** The **Windows 10/11 compliance policy** configuration showing **Require encryption of data storage on device** changed to **Not configured** as the remediation for the lab environment.

<img width="1919" height="912" alt="06 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/71c44479-fda5-4aa5-8ef0-5a0fc1236888" />

**Figure 5:** Microsoft Intune showing **CLIENT01** reporting **Compliant** against the **Windows 10-11 - Compliance Policy**, confirming successful remediation.

<img width="1919" height="915" alt="07 – Troubleshooting an Intune Compliance Policy Error" src="https://github.com/user-attachments/assets/faa48210-a8a6-4234-853a-9d651b27e581" />
