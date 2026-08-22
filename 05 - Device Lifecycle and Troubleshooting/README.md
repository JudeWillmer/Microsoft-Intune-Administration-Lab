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
